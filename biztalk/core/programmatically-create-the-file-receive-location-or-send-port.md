---
title: 以编程方式创建文件接收位置或发送端口 |Microsoft 文档
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
ms.openlocfilehash: af6365c640cbc51053d02822141915cbd4cad828
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972996"
---
# <a name="programmatically-create-the-file-receive-location-or-send-port"></a>以编程方式创建文件接收位置或发送端口
如何创建一个文件接收端口，并以编程方式发送端口。 若要使用[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，请转到[配置文件适配器](../core/configure-the-file-adapter.md)。

文件适配器将其配置信息存储在 SSO 数据库中。 你可以配置接收位置和发送端口以编程方式使用 BizTalk 资源管理器对象模型。 
 
## <a name="create-the-receive-location"></a>创建接收位置

BizTalk 资源管理器对象模型公开了**IReceiveLocation**包含的配置界面**TransportTypeData**读/写属性。 此属性以名称-值对 XML 字符串的形式接受文件接收位置配置属性包。  
  
**TransportTypeData**属性**IReceiveLocation**接口不需要设置。 如果未设置该属性，则使用文件接收位置配置的默认值。  
  
 下表列出了可通过编程方式为文件接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|**FileNetFailRetryCount**|Long|尝试访问网络共享上的接收位置（如果该位置暂时不可用）的次数。|Integer<br /><br /> 最小值： 0<br /><br /> 最大值： MAX_LONG|如果未指定该属性，则默认值设置为 5 次。|  
|**FileNetFailRetryInterval**|Long|两次尝试访问网络共享上的接收位置（如果该位置暂时不可用）之间的重试间隔（分钟）。|Integer<br /><br /> Minimumvalue: 0<br /><br /> 最大值： MAX_LONG|如果未指定该属性，则默认值设置为 5 分钟。|  
|**BatchSize**|Long|此接收位置一次可提交到服务器的文件数。|Integer<br /><br /> 最小值： 1<br /><br /> 最大值： 256|如果未指定该属性，则默认值设置为 20 个文件。|  
|**FileMask**|字符串|接收位置使用的文件掩码。|字符串<br /><br /> FilePath 和 FileMask 的组合长度不能超过 256 个字符。|如果未指定该属性，则默认值设置为 *.xml。|  
|**文件路径**|字符串|接收位置监视的文件夹的路径。|字符串<br /><br /> 必需<br /><br /> FilePath 和 FileMask 的组合长度不能超过 256 个字符。|必须指定**重要说明：** 创建接收位置必须具有对配置在接收位置上的接收处理程序凭据的写入权限的文件文件夹。|  
|**用户名**|字符串|用于访问文件夹的帐户的用户名。|最小长度： 0<br /><br /> 最大长度： 256|如果未指定用户名或密码，则使用主机凭据。<br /><br /> 如果此项为空 (vt="1")，则使用配置数据库中存储的值。|  
|**密码**|字符串|用于访问文件夹的帐户的密码。|最小长度： 0<br /><br /> 最大长度： 256|如果未指定用户名或密码，则使用主机凭据。<br /><br /> 如果此项为空 (vt="1")，则使用配置数据库中存储的值。|  
  
 下面的代码演示使用设置的属性的 XML 字符串的格式：  
  
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

配置信息存储在自定义的 XML 属性包中。 `bts_file_properties.xsd`文件发送处理程序属性架构定义文件特定于适配器的属性。 使用这些属性可以配置 FILE 发送端口，并在服务器中传递特定于适配器的信息。  
  
BizTalk 资源管理器对象模型公开了**ITransportInfo**适配器的配置界面文件发送端口，其中包含**TransportTypeData**读/写属性。 此属性以名称-值对 XML 字符串的形式接受文件发送处理程序配置属性包。  
  
 设置**TransportTypeData**属性**ITransportInfo**界面不是必需。 如果未设置该属性，则使用文件发送处理程序配置的默认值。  
  
 下表列出了可在 BizTalk 浏览器对象模型中以编程方式为文件发送处理程序位置设置的配置属性：  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**CopyMode**|Long|定义要在一条消息写入到文件时使用的复制模式。 有效值为<br /><br /> **追加 (0)。** 文件发送处理程序打开一个文件（如果该文件存在）并在该文件末尾附加一个消息。 如果文件不存在，则文件发送处理程序将创建一个新文件。<br /><br /> **创建新的 (1)。** 如果文件不存在，该文件发送处理程序创建一个新文件，并将写入到其中。 如果该文件已存在，则文件发送处理程序将报告错误，然后按照发送端口的通用适配器重试逻辑操作。 此模式为文件发送处理程序的默认复制模式。<br /><br /> **覆盖 (2)。** 文件发送处理程序打开一个文件（如果该文件存在）并覆盖其内容。 如果文件不存在，则文件发送处理程序将创建一个新文件。|  
|**AllowCacheOnWrite**|Boolean|定义文件适配器在向文件中写入消息时是否使用文件系统缓存。<br /><br /> 有效值为<br /><br /> **True (-1)** 文件适配器使用文件系统缓存写入输出文件时。<br /><br /> **False (0)** 文件发送处理程序不使用文件系统缓存写入输出文件时。|  
|**在写入时使用临时文件**|Boolean|定义是否首先将输出文件写入临时文件，然后在写入操作完成后重命名该文件。 如果启用此选项，则将创建临时文件，使用扩展**BTS WIP**。<br /><br /> 有效值为<br /><br /> **True (-1)** 文件适配器创建的临时文件写入到目标文件夹时。<br /><br /> **False (0)** 写入到目标文件夹时，文件适配器将不会创建临时文件。 **注意：** 时，此选项才可用**CopyMode**属性设置为值为**创建新的 (1)**。|  
  
 如果有任何配置属性在消息上下文中没有值，则文件发送处理程序将使用其默认值。  
  
 你可以对消息上下文以编程方式设置配置属性。 可以在业务流程或自定义管道组件中设置这些属性。 使用这些属性时，以下规则适用：  
  
-   如果在业务流程中或在接收管道的自定义管道组件中设置配置属性，那么：  
  
    -   如果消息发送到一个静态发送端口，将被覆盖发送端口的值为配置的属性值。  
  
    -   如果一条消息发送到动态发送端口，则属性值不会被覆盖。  
  
-   如果在发送管道的自定义管道组件中设置配置属性，那么：  
  
    -   无论将消息发送到静态发送端口还是动态发送端口，都不会覆盖属性值。  
  
 以下代码显示了可用于设置这些属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
   <CopyMode vt="19">0</CopyMode>  
   <AllowCacheOnWrite vt="11">-1</AllowCacheOnWrite>  
   <UseTempFileOnWrite vt="11">-1</UseTempFileOnWrite>  
</CustomProps>  
```  


