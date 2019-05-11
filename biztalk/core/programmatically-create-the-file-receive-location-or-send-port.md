---
title: 以编程方式创建文件接收位置或发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 558a414c-60bc-4f62-9397-a023ed4937fb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c582cbd94f12855acfed963aa70c972cef811b7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255113"
---
# <a name="programmatically-create-the-file-receive-location-or-send-port"></a>以编程方式创建文件接收位置或发送端口
如何创建文件接收端口和发送端口以编程方式。 若要使用[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，请转到[配置文件适配器](../core/configure-the-file-adapter.md)。

文件适配器将其配置信息存储在 SSO 数据库中。 你可以配置接收位置和发送端口以编程方式使用 BizTalk 浏览器对象模型。 
 
## <a name="create-the-receive-location"></a>创建接收位置

BizTalk 浏览器对象模型公开**IReceiveLocation**包含的配置界面**TransportTypeData**读/写属性。 此属性接受文件接收位置配置属性包形式的名称/值对 XML 字符串。  
  
**TransportTypeData**的属性**IReceiveLocation**接口无需设置。 如果未设置该属性，默认值为文件接收位置配置使用。  
  
 下表列出了可以为文件以编程方式设置的配置属性接收位置。  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|**FileNetFailRetryCount**|Long|尝试访问网络共享上的接收位置，如果暂时不可用的次数。|Integer<br /><br /> 最小值：0<br /><br /> 最大值：MAX_LONG|如果未指定，默认值设置为 5 次。|  
|**FileNetFailRetryInterval**|Long|重试间隔以分钟为单位之间尝试访问网络共享上的接收位置，如果它是暂时不可用。|Integer<br /><br /> Minimumvalue:0<br /><br /> 最大值：MAX_LONG|如果未指定，默认值设置为 5 分钟。|  
|**BatchSize**|Long|数量的文件，此接收位置可以向服务器提交一次。|Integer<br /><br /> 最小值：1<br /><br /> 最大值：256|如果未指定，默认值设置为 20 个文件。|  
|**FileMask**|String|接收位置使用的文件掩码。|String<br /><br /> FilePath 和 FileMask 的组合长度不能超过 256 个字符。|如果未指定，默认值设置为 *.xml。|  
|**FilePath**|String|接收位置所监视的文件夹的路径。|String<br /><br /> Required<br /><br /> FilePath 和 FileMask 的组合长度不能超过 256 个字符。|必须指定**重要说明：** 为接收位置创建的文件文件夹必须具有对接收位置上配置的接收处理程序凭据的写入权限。|  
|**用户名**|String|用于访问文件夹的帐户的用户名。|最小长度：0<br /><br /> 最大长度：256|如果指定的用户名或密码既不，使用主机凭据。<br /><br /> 如果为 null (vt ="1") 则使用配置数据库中存储的值。|  
|**密码**|String|用于访问文件夹的帐户的密码。|最小长度：0<br /><br /> 最大长度：256|如果指定的用户名或密码既不，使用主机凭据。<br /><br /> 如果为 null (vt ="1") 则使用配置数据库中存储的值。|  
  
 下面的代码显示了使用设置的属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
   <FilePath vt="8">C:\Temp</FilePath>  
   <BatchSize vt="19">20</BatchSize>  
   <FileMask vt="8">*.xml</FileMask>  
   <FileNetFailRetryCount vt="19">5</FileNetFailRetryCount>  
   <FileNetFailRetryInterval vt="19">5</FileNetFailRetryInterval>  
   <Username vt=”8”>MyDomain\MyUsername</Username>  
   <Password vt=”8”>PASSWORD</Password>  
</CustomProps>  
  
```  

## <a name="create-the-send-port"></a>创建发送端口

配置信息存储在自定义的 XML 属性包中。 `bts_file_properties.xsd`文件发送处理程序属性架构定义文件特定于适配器的属性。 这些属性用于配置 File 发送端口，并传递在服务器内的特定于适配器的信息。  
  
BizTalk 浏览器对象模型公开**ITransportInfo**适配器配置接口 File 发送端口，其中包含**TransportTypeData**读/写属性。 此属性以名称/值对 XML 字符串的形式接受文件发送处理程序配置属性包。  
  
 设置**TransportTypeData**的属性**ITransportInfo**接口不需要。 如果未设置，将发送该文件的默认值，则使用处理程序配置。  
  
 下表列出了配置设置的属性可以以编程方式在 BizTalk 浏览器对象模型中的文件发送处理程序位置。  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**CopyMode**|Long|定义向文件中写入一条消息时要使用的复制模式。 有效值为<br /><br /> **追加 (0)。** 如果它存在并且文件的末尾追加一条消息，该文件发送处理程序打开一个文件。 如果文件不存在，则文件发送处理程序将创建一个新文件。<br /><br /> **创建新的 (1)。** 如果该文件不存在，则文件发送处理程序创建一个新文件，并向其中写入。 如果该文件已存在，文件发送处理程序报告错误，然后按照发送端口的通用适配器重试逻辑。 这是文件发送处理程序的默认复制模式。<br /><br /> **覆盖 (2)。** 如果它存在并且覆盖其内容，该文件发送处理程序打开一个文件。 如果文件不存在，则文件发送处理程序将创建一个新文件。|  
|**AllowCacheOnWrite**|Boolean|定义文件适配器是否使用文件系统缓存到文件中写入消息时。<br /><br /> 有效值为<br /><br /> **True (-1)** 文件适配器时使用文件系统缓存写入输出文件。<br /><br /> **False (0)** 文件发送处理程序不使用文件系统缓存写入输出文件时。|  
|**写入时使用临时文件**|Boolean|定义是否将输出文件写入到临时文件，然后写操作完成后重命名该文件。 如果启用此选项，则将创建临时文件扩展名**BTS WIP**。<br /><br /> 有效值为<br /><br /> **True (-1)** 文件适配器在写入目标文件夹时创建临时文件。<br /><br /> **False (0)** 文件适配器在写入目标文件夹时不会创建临时文件。 **注意：** 此选项才可用**CopyMode**属性设置为值**创建新的 (1)**。|  
  
 如果任何配置属性没有消息上下文的一个值，该文件发送处理程序使用其默认值。  
  
 消息上下文，可以以编程方式设置配置属性。 在业务流程或自定义管道组件中，可以设置这些属性。 使用这些属性时，以下规则适用：  
  
- 如果设置配置属性在业务流程或自定义管道组件在接收管道中，然后：  
  
  -   如果一条消息发送到静态发送端口，属性值将覆盖与该发送端口配置的值。  
  
  -   如果一条消息发送到动态发送端口，则不会覆盖属性值。  
  
- 如果然后在发送管道中，自定义管道组件中设置配置属性：  
  
  -   值不会被覆盖而不考虑是否将消息发送到静态或动态发送端口。  
  
  下面的代码显示了可用于设置属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
   <CopyMode vt="19">0</CopyMode>  
   <AllowCacheOnWrite vt="11">-1</AllowCacheOnWrite>  
   <UseTempFileOnWrite vt="11">-1</UseTempFileOnWrite>  
</CustomProps>  
```  


