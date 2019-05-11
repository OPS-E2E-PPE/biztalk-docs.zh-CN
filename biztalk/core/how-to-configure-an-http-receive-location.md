---
title: 如何配置 HTTP 接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, HTTP adapters
- configuring [HTTP adapters], receive locations
- HTTP adapters, receive locations
ms.assetid: 901adfc8-0361-49d9-b992-c27089dfbd3b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d5c6bde11a4e0ca382815842e0eb71794dc422
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341752"
---
# <a name="how-to-configure-an-http-receive-location"></a>如何配置 HTTP 接收位置
您可以设置 HTTP 以编程方式接收位置适配器变量或使用 BizTalk Server 管理控制台。 如果属性未设置接收位置中，使用 BizTalk Server 管理控制台中设置的默认接收处理程序值。  

> [!NOTE]
>  在执行以下过程之前，必须已添加接收端口。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  

 **如何配置 HTTP 接收位置以编程方式**  

 HTTP 适配器将其配置信息存储在 BizTalk 管理数据库 （也称为配置数据库）。 配置存储在自定义的 XML 属性包。  

 BizTalk 浏览器对象模型公开**IReceiveLocation**配置接口，从而**TransportTypeData**读/写属性。 此属性接受 HTTP 接收位置配置属性包中的名称-值对 XML 字符串。  

 设置**TransportTypeData**的属性**IReceiveLocation**不是必需的。 如果未设置该属性，默认值为 HTTP 接收位置配置使用。 下表列出了默认值，并还列出了可在 BizTalk 浏览器对象中设置的配置属性模型中为 HTTP 接收位置。  

|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|**ResponseContentType**|string|HTTP 适配器的发送回客户端从该接收位置的 HTTP 响应消息的内容类型。 此属性才有效，仅对请求-响应接收端口和忽略的单向接收端口。|String<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|默认值：Text/XML|  
|**LoopBack**|Boolean|指定此位置上接收请求消息将路由到发送端口或接收位置以作为响应发送回。 仅对请求-响应接收端口，此属性才有效。 则可忽略单向接收端口。|None|**默认值：** False|  
|**ReturnCorrelationHandle**|Boolean|指定的相关标记已提交的 HTTP 适配器将发送到客户端的 HTTP 响应，如果提交成功的消息。 此属性才有效仅对单向接收端口和请求-响应接收端口将被忽略。|None|**默认值：** True|  
|**SuspendFailedRequests**|Boolean|指定是否将挂起失败的 HTTP 请求。 值为 True 表示将挂起失败的请求并将"已接受"状态代码 (202) 发送到客户端的单向接收端口或"错误"状态代码 (500) 的客户端到双向接收端口。|None|**默认值：** False|  
|**UseSSO**|Boolean|指定 HTTP 适配器是否将向此到达的消息颁发 SSO 票证接收位置。|None|**默认值：** False|  

 若要设置这些属性的 XML 字符串的格式如下所示：  

```  
<CustomProps>  
   <UseSSO vt="11">-1</UseSSO>  
   <SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
   <ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
   <ResponseContentType vt="8">text/xml</ResponseContentType>  
   <LoopBack vt="11">-1</LoopBack>  
</CustomProps>  

```  

 **如何配置 HTTP 接收位置使用 BizTalk Server 管理控制台**  

 若要通过使用 BizTalk Server 管理控制台配置接收位置，请使用以下过程。  

### <a name="to-configure-variables-for-an-http-receive-location"></a>若要配置 http 接收位置的变量  

1. 配置 Internet 信息服务 (IIS) 以使用 HTTP 接收位置。 有关配置 IIS 的说明，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  

2. 在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开要在其中创建接收位置的应用程序。  

3. 在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  

4. 在中**接收端口属性**对话框中，在左窗格中，选择**接收位置**，并在右窗格中，双击现有接收位置或单击**新建**若要创建新的接收位置。  

5. 在中**接收位置属性**对话框中**传输**部分旁边**类型**，选择**HTTP**从下拉列表然后单击**配置**。  

6. 在中**HTTP 传输属性**对话框框中，执行以下操作：  


   |                           使用此选项                           |                                                                                                                                                                                                                                                                                                                                执行的操作                                                                                                                                                                                                                                                                                                                                |
   |--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |          **虚拟目录和 ISAPI 扩展**          | 指定名称的虚拟目录，可发布 HTTP/HTTPS 接收的消息的接收位置。 虚拟目录包含接收位置 DLL 的名称和可选查询字符串。 虚拟目录名称的示例包括：<br /><br /> /\<虚拟目录\>/BTSHTTPReceive.dll<br /><br /> /\<虚拟目录\>/BTSHTTPReceive.dll？购买 %20order<br /><br /> 此位置不能包含多个 BTSHTTPReceive.dll ISAPI 扩展，包括所有子文件夹。<br /><br /> **类型：** String<br /><br /> **最大长度：** 256**注意：** URI 发送端口或接收位置不能超过 256 个字符。  |
   |                      **公用地址**                      | 指定此接收位置的完全限定 URI。 此属性的值是服务器名称和虚拟目录的组合。 BizTalk 消息引擎公开此地址与外部合作伙伴。 指定的 URI 应指定贸易合作伙伴要向 BizTalk Server 发送消息时连接到的公共网站 URL。<br /><br /> 此信息是可选的不由 BizTalk Server。 此参数，可允许管理员文档的接收位置绑定到的公共 URL。<br /><br /> **类型：** String<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256 |
   |                   **返回内容类型**                    |                                                                                                                                                                            指定接收位置发回客户端的 HTTP 响应消息的内容类型。 此属性仅对请求响应接收位置有效。<br /><br /> **默认值：** text/xml<br /><br /> **类型：** String<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256                                                                                                                                                                            |
   |                         **Loopback**                         |                                                                                                                                                                                       定义此位置上接收的请求消息路由到发送端口或回此接收位置以作为响应发送。 此属性仅对请求响应接收位置有效。<br /><br /> **默认值：** False<br /><br /> **类型：** Boolean                                                                                                                                                                                        |
   | **返回相关句柄成功 （仅用于单向端口）** |                                                                                                                                                                                                  定义，如果成功，接收位置发送已提交消息的相关标记向客户端在 HTTP 响应上。 此属性才有效仅对单向接收位置。<br /><br /> **默认值：** True<br /><br /> **类型：** Boolean                                                                                                                                                                                                   |
   |                    **使用单一登录**                    |                                   指示使用是企业单一登录。<br /><br /> **默认值：** False<br /><br /> **类型：** 布尔**注意：** 如果启用此选项，则还必须启用选项**允许使用票证**处**SSO 系统**级别。 **允许使用票证**是可在配置选项**选项**选项卡**SSO 系统属性**对话框中提供**SSO 管理**MMC 界面。 如果启用此选项和**允许使用票证**选项在**SSO 系统**级别未启用，则此接收任何消息的接收位置将被挂起。                                    |
   |                 **挂起失败的请求**                  |                                                                              指示挂起入站的处理失败的 HTTP 请求。<br /><br /> 值为 False 表示将放弃失败的请求并向客户端发送错误状态代码 （401 或 500）。<br /><br /> 值为 True 表示将挂起失败的请求并将"已接受"状态代码 (200) 发送到客户端的单向接收端口或"错误"状态代码 (500) 的客户端到双向接收端口。<br /><br /> **默认值：** False<br /><br /> **类型：** Boolean                                                                              |


7. 单击**确定**以保存设置。  

8. 在“接收位置属性”  对话框中输入相应的值，完成对接收位置的配置，然后单击“确定”  保存设置。 有关“接收位置属性”  对话框的信息，请参阅 [如何创建接收位置](../core/how-to-create-a-receive-location.md)。  

   当 HTTP 客户端调用 HTTP 位置时，HTTP 适配器进行 HTTP 客户端身份验证通过使用匿名、 基本、 摘要式、 或 Windows 集成身份验证。 如果用户通过验证，用户上下文传递到接收处理程序。  

> [!NOTE]
>  会导致 SOAP 与 HTTP 共享同一进程的任何 IIS 配置不是有效的。 您可以每个进程只有一个独立的接收器。