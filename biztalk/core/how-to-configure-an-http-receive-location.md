---
title: "如何配置 HTTP 接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, HTTP adapters
- configuring [HTTP adapters], receive locations
- HTTP adapters, receive locations
ms.assetid: 901adfc8-0361-49d9-b992-c27089dfbd3b
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4448182792cd6f6f5f7e611cd9a9bd54c75a0d05
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-an-http-receive-location"></a>如何配置 HTTP 接收位置
您可以通过编程方式或使用 BizTalk Server 管理控制台来设置 HTTP 接收位置适配器变量。 如果未设置接收位置的属性，则使用 BizTalk Server 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，您必须已添加接收端口。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
 **如何配置 HTTP 接收位置以编程方式**  
  
 HTTP 适配器 （也称为配置数据库） 中的 BizTalk 管理数据库中存储其配置信息。 配置信息存储在自定义 XML 属性包中。  
  
 BizTalk 资源管理器对象模型公开了**IReceiveLocation**配置界面，具有**TransportTypeData**读/写属性。 此属性以名称-值对 XML 字符串的形式接受 HTTP 接收位置配置属性包。  
  
 设置**TransportTypeData**属性**IReceiveLocation**不是必需的。 如果未设置该属性，则使用 HTTP 接收位置配置的默认值。 下表列出了这些默认值，还列出了可在 BizTalk 浏览器对象模型中为 HTTP 接收位置设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|**ResponseContentType**|string|HTTP 适配器通过此接收位置发回客户端的 HTTP 响应消息的内容类型。 此属性仅对请求响应接收端口有效；对于单向接收端口，会将其忽略。|字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|默认值： Text/XML|  
|**环回**|Boolean|指定此位置上接收的请求消息是路由到发送端口，还是路由回该接收位置以作为响应发送。 此属性仅对请求响应接收端口有效。 对于单向接收端口，会将其忽略。|无|**默认值：** False|  
|**ReturnCorrelationHandle**|Boolean|指定在提交成功时 HTTP 适配器通过 HTTP 响应向客户端发送的已提交消息的相关标记。 此属性仅对单向接收端口有效；对于请求响应接收端口，会将其忽略。|无|**默认值：** True|  
|**SuspendFailedRequests**|Boolean|指定是否挂起失败的 HTTP 请求。 值为 True 指示将挂起失败的请求，并且对于单向接收端口，将向客户端发送“已接受”状态代码 (202)，而对于双向接收端口，将向客户端发送“错误”状态代码 (500)。|无|**默认值：** False|  
|**UseSSO**|Boolean|指定 HTTP 适配器是否会向此接收位置收到的消息颁发 SSO 票证。|无|**默认值：** False|  
  
 用于设置这些属性的 XML 字符串的格式如下所示：  
  
```  
<CustomProps>  
   <UseSSO vt="11">-1</UseSSO>  
   <SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
   <ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
   <ResponseContentType vt="8">text/xml</ResponseContentType>  
   <LoopBack vt="11">-1</LoopBack>  
</CustomProps>  
  
```  
  
 **如何配置 HTTP 接收与 BizTalk Server 管理控制台的位置**  
  
 使用以下过程可以通过 BizTalk Server 管理控制台配置接收位置。  
  
### <a name="to-configure-variables-for-an-http-receive-location"></a>配置 HTTP 接收位置的变量  
  
1.  配置 Internet 信息服务 (IIS) 以使用 HTTP 接收位置。 有关配置 IIS 的说明，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
2.  在 BizTalk Server 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你要在其中创建接收位置的应用程序。  
  
3.  在左窗格中，单击**接收端口**节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
4.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，并且在右窗格中，双击现有接收位置或单击**新建**若要创建一个新接收位置。  
  
5.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**HTTP**从下拉列表然后单击**配置**。  
  
6.  在**HTTP 传输属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**虚拟目录以及 ISAPI 扩展**|指定虚拟目录的名称，在该目录中，可发布 HTTP/HTTPS 接收位置所接收的消息。 虚拟目录包含接收位置 DLL 的名称和可选查询字符串。 虚拟目录名称的示例如下：<br /><br /> /\<虚拟目录\>/BTSHTTPReceive.dll<br /><br /> /\<虚拟目录\>/BTSHTTPReceive.dll？购买 %20order<br /><br /> 此位置不能包含多个 BTSHTTPReceive.dll ISAPI 扩展（包括所有子文件夹）。<br /><br /> **类型：**字符串<br /><br /> **最大长度：** 256**注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**公共地址**|指定此接收位置的完全限定 URI。 此属性的值是服务器名和虚拟目录的组合。 BizTalk 消息引擎将向外部合作伙伴公开此地址。 指定的 URI 应指定在向 BizTalk Server 发送消息时贸易合作伙伴要连接到的公共网站 URL。<br /><br /> 此信息是可选的，BizTalk Server 并不使用。 管理员可使用此参数记录与接收位置相关联的公共 URL。<br /><br /> **类型：**字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|  
    |**返回内容的类型**|指定接收位置发回客户端的 HTTP 响应消息的内容类型。 此属性仅对请求响应接收位置有效。<br /><br /> **默认值：**文本/xml<br /><br /> **类型：**字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|  
    |**Loopback**|定义此位置上接收的请求消息是路由到发送端口，还是路由回此接收位置以作为响应发送。 此属性仅对请求响应接收位置有效。<br /><br /> **默认值：** False<br /><br /> **类型：**布尔|  
    |**成功 （仅一种方法的端口） 返回的相关句柄**|定义在操作成功时，接收位置将向客户端发送已提交消息在 HTTP 响应上的相关标记。 此属性仅对单向接收位置有效。<br /><br /> **默认值：** True<br /><br /> **类型：**布尔|  
    |**在使用单一登录**|表示使用企业单一登录。<br /><br /> **默认值：** False<br /><br /> **类型：**布尔**注意：**如果启用此选项，则还必须启用该选项以**允许票证**在**SSO 系统**级别。 **允许票证**选项是可在配置**选项**选项卡**SSO 系统属性**对话框中提供**SSO 管理**MMC 接口。 如果启用此选项与**允许票证**选项**SSO 系统**级别未启用，则此接收任何消息接收位置将被挂起。|  
    |**挂起失败的请求**|指示是否挂起入站处理失败的 HTTP 请求。<br /><br /> 值为 False 表示将放弃失败的请求并向客户端发送错误状态代码（401 或 500）。<br /><br /> 值为 True 指示挂起失败的请求并将"已接受"状态代码 (200) 发送到的客户端单向接收端口或"错误"状态代码 (500) 的客户端到双向接收端口。<br /><br /> **默认值：** False<br /><br /> **类型：**布尔|  
  
7.  单击**确定**以保存设置。  
  
8.  在“接收位置属性”  对话框中输入相应的值，完成对接收位置的配置，然后单击“确定”  保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。  
  
 当 HTTP 客户端调用 HTTP 位置时，HTTP 适配器将使用匿名、基本、摘要或 Windows 集成身份验证来对 HTTP 客户端进行验证。 如果用户通过验证，则将用户上下文传递到接收处理程序。  
  
> [!NOTE]
>  任何会导致 SOAP 与 HTTP 共享同一进程的 IIS 配置都是无效的。 对于每个进程，只能有一个独立的接收器。