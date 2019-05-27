---
title: 解析程序服务示例的工作原理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33b5f886-ec54-4b2b-b09d-fb4c47ad43a5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d07fbe42cf1253f5976227211f59ff66809fb70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279032"
---
# <a name="how-the-resolver-service-sample-works"></a><span data-ttu-id="d9873-102">解析程序服务示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="d9873-102">How the Resolver Service Sample Works</span></span>
<span data-ttu-id="d9873-103">解析程序服务示例实例化解析程序服务，并将的消息传递您指定对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="d9873-103">The Resolver Service sample instantiates the Resolver service and passes the message you specify to it for processing.</span></span> <span data-ttu-id="d9873-104">解析程序服务示例客户端应用程序使用的第一个参数作为 ResolverList.xml 文件，其中包含多个冲突解决程序请求，并将这些请求发送到解析程序服务的路径。</span><span class="sxs-lookup"><span data-stu-id="d9873-104">The Resolver Service sample client application uses the first parameter as the path to the ResolverList.xml file, which contains multiple resolver requests, and sends these requests to the Resolver service.</span></span> <span data-ttu-id="d9873-105">例如，下面是本示例中使用 XPATH 请求。</span><span class="sxs-lookup"><span data-stu-id="d9873-105">For example, the following is the XPATH request used in the sample.</span></span>  
  
```  
  
//XPATH  
<Resolver>  
  <name>XPATHWithFILE</name>   
  <Content>![CDATA[XPATH:\\TransportLocation=/*[local-name()='OrderDoc'   
    and namespace-uri()='http://globalbank.esb.dynamicresolution.com/  
    northamericanservices/']/*[local-name()='ID' and namespace-  
    uri()='http://globalbank.esb.dynamicresolution.com/  
    northamericanservices/'];TargetNamespace=;  
    MessageExchangePattern=;EndpointConfig=;JaxRpcResponse=;TransportType=;  
    Action=;TransformType=]]  
  </Content>   
  <body>  
    ![CDATA[   
    <ns0:OrderDoc xmlns:ns0="http://globalbank.esb.dynamicresolution.com/northamericanservices/">  
      <ns0:customerName>Microsoft</ns0:customerName>  
  
<ns0:ID>FILE://C:\Projects\Microsoft.Practices.ESB\Source\Samples  
    \DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml</ns0:ID>   
      <ns0:requestType>10</ns0:requestType>   
    </ns0:OrderDoc>  
    ]]   
  </body>  
</Resolver>  
```  
  
> [!NOTE]
>  <span data-ttu-id="d9873-106">实际内容**\<内容\>** 元素不包含用于在上述列表中换行空格字符。</span><span class="sxs-lookup"><span data-stu-id="d9873-106">The actual content of the **\<Content\>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  
  
 <span data-ttu-id="d9873-107">前面的列表显示该请求包含中的冲突解决程序配置连接字符串**\<内容\>** 元素。</span><span class="sxs-lookup"><span data-stu-id="d9873-107">The preceding listing shows that the request contains the resolver configuration connection string within a **\<Content\>** element.</span></span> <span data-ttu-id="d9873-108">**\<正文\>** 元素包含消息正文。</span><span class="sxs-lookup"><span data-stu-id="d9873-108">The **\<body\>** element contains the message body.</span></span>  
  
 <span data-ttu-id="d9873-109">解析程序服务使用**ResolverMgr**要实例化相应冲突解决程序，定义的连接字符串中的冲突解决程序类型的具体实例类。</span><span class="sxs-lookup"><span data-stu-id="d9873-109">The Resolver service uses the **ResolverMgr** class to instantiate a concrete instance of the appropriate resolver, defined by the resolver type in the connection string.</span></span> <span data-ttu-id="d9873-110">如果 XPATH 请求中，这是 XPATH 冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="d9873-110">In the case of the XPATH request, this is the XPATH resolver.</span></span>  
  
 <span data-ttu-id="d9873-111">接下来，框架将创建的实例**ResolveProvider**类名为 ESB。Resolver.XPath 用于处理该请求。</span><span class="sxs-lookup"><span data-stu-id="d9873-111">Next, the framework creates an instance of the **ResolveProvider** class named ESB.Resolver.XPath to process the request.</span></span> <span data-ttu-id="d9873-112">客户端应用程序将从解析程序服务的响应消息写入到名为 \Source\Samples\ResolverService\Output 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d9873-112">The client application writes the response message from the Resolver service into the folder named \Source\Samples\ResolverService\Output.</span></span> <span data-ttu-id="d9873-113">以下列表显示了响应的内容。</span><span class="sxs-lookup"><span data-stu-id="d9873-113">The following listing shows the contents of the response.</span></span>  
  
```  
  
//XPATH  
Resolver.Action =   
Resolver.ActionField =   
Resolver.DocumentSpecName =   
Resolver.DocumentSpecStrongName =   
Resolver.EndpointConfig =   
Resolver.EpmRRCorrelationToken =   
Resolver.FixJaxRpc = False  
Resolver.InboundTransportLocation =   
Resolver.InboundTransportType =   
Resolver.InterchangeId =   
Resolver.IsRequestResponse =   
Resolver.MessageExchangePattern =   
Resolver.MessageType =   
Resolver.MethodName =   
Resolver.OutboundTransportCLSID =   
Resolver.ReceiveLocationName =   
Resolver.ReceivePortName =   
Resolver.Success = False  
Resolver.TargetNamespace =   
Resolver.TransformType =   
Resolver.TransportLocation = FILE://C:\Projects\Microsoft.  
    Practices.ESB\Source\Samples  
\DynamicResolution\Test\Filedrop\OUt\%MessageID%.xml  
Resolver.TransportNamespace =   
Resolver.TransportType = FILE  
Resolver.WindowUserField =  
```