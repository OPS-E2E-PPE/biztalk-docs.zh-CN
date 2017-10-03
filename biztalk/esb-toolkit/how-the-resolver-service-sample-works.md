---
title: "解析程序服务示例的工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33b5f886-ec54-4b2b-b09d-fb4c47ad43a5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c44677d4d488a4770c540ef94c0922579be3184
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-resolver-service-sample-works"></a><span data-ttu-id="fcd95-102">解析程序服务示例的工作原理</span><span class="sxs-lookup"><span data-stu-id="fcd95-102">How the Resolver Service Sample Works</span></span>
<span data-ttu-id="fcd95-103">解析程序服务示例实例化解析程序服务，并将该消息传递指定向其进行处理。</span><span class="sxs-lookup"><span data-stu-id="fcd95-103">The Resolver Service sample instantiates the Resolver service and passes the message you specify to it for processing.</span></span> <span data-ttu-id="fcd95-104">解析程序服务示例客户端应用程序使用的第一个参数作为 ResolverList.xml 文件，以包含多个冲突解决程序请求，并将这些请求发送到解析程序服务的路径。</span><span class="sxs-lookup"><span data-stu-id="fcd95-104">The Resolver Service sample client application uses the first parameter as the path to the ResolverList.xml file, which contains multiple resolver requests, and sends these requests to the Resolver service.</span></span> <span data-ttu-id="fcd95-105">例如，下面是示例中使用 XPATH 请求。</span><span class="sxs-lookup"><span data-stu-id="fcd95-105">For example, the following is the XPATH request used in the sample.</span></span>  
  
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
>  <span data-ttu-id="fcd95-106">实际内容**\<内容 >**元素不包含使用在前面的列表中将行的空白字符。</span><span class="sxs-lookup"><span data-stu-id="fcd95-106">The actual content of the **\<Content>** element does not contain the white space characters used to wrap the lines in the preceding listing.</span></span>  
  
 <span data-ttu-id="fcd95-107">前面的列表显示该请求包含中的解析程序配置连接字符串**\<内容 >**元素。</span><span class="sxs-lookup"><span data-stu-id="fcd95-107">The preceding listing shows that the request contains the resolver configuration connection string within a **\<Content>** element.</span></span> <span data-ttu-id="fcd95-108">**\<正文 >**元素包含消息正文。</span><span class="sxs-lookup"><span data-stu-id="fcd95-108">The **\<body>** element contains the message body.</span></span>  
  
 <span data-ttu-id="fcd95-109">解析程序服务使用**ResolverMgr**要实例化相应的解析程序，连接字符串中的冲突解决程序类型所定义的具体实例类。</span><span class="sxs-lookup"><span data-stu-id="fcd95-109">The Resolver service uses the **ResolverMgr** class to instantiate a concrete instance of the appropriate resolver, defined by the resolver type in the connection string.</span></span> <span data-ttu-id="fcd95-110">如果 XPATH 请求中，这是由 XPATH 冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="fcd95-110">In the case of the XPATH request, this is the XPATH resolver.</span></span>  
  
 <span data-ttu-id="fcd95-111">接下来，框架将创建的实例**ResolveProvider**名为 ESB 类。Resolver.XPath 用于处理该请求。</span><span class="sxs-lookup"><span data-stu-id="fcd95-111">Next, the framework creates an instance of the **ResolveProvider** class named ESB.Resolver.XPath to process the request.</span></span> <span data-ttu-id="fcd95-112">客户端应用程序将从解析程序服务的响应消息写入到名为 \Source\Samples\ResolverService\Output 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="fcd95-112">The client application writes the response message from the Resolver service into the folder named \Source\Samples\ResolverService\Output.</span></span> <span data-ttu-id="fcd95-113">以下列表显示响应的内容。</span><span class="sxs-lookup"><span data-stu-id="fcd95-113">The following listing shows the contents of the response.</span></span>  
  
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