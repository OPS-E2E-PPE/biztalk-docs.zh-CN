---
title: "调用具有集成对象使用 Siebel 适配器的业务服务方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- integration objects
- how to, invoke business service methods with integration objects
- business service methods, invoking with integration objects
ms.assetid: ac0fa80a-3451-436e-8a1a-b6b5e93081e7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 132c269d347f67cbad3038bcbbb8e62d29112b6e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a><span data-ttu-id="b62f4-102">调用具有集成对象使用 Siebel 适配器的业务服务方法</span><span class="sxs-lookup"><span data-stu-id="b62f4-102">Invoke Business Service Methods with Integration Objects using the Siebel adapter</span></span>
<span data-ttu-id="b62f4-103">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端调用使用集成的对象的业务服务方法。</span><span class="sxs-lookup"><span data-stu-id="b62f4-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enables adapter clients to invoke business service methods that work with integration objects.</span></span> <span data-ttu-id="b62f4-104">这些业务服务通常有 IN、 输出、 或的"层次结构"数据 IN OUT 参数键入发送或接收集成对象数据。</span><span class="sxs-lookup"><span data-stu-id="b62f4-104">These business services typically have IN, OUT, or IN OUT parameters of "hierarchy" data type to send or receive integration object data.</span></span>  
  
 <span data-ttu-id="b62f4-105">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开这些分层类型作为字符串。</span><span class="sxs-lookup"><span data-stu-id="b62f4-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes these hierarchical types as strings.</span></span> <span data-ttu-id="b62f4-106">这些字符串值是实质上是封装在一个 XML CDATA 节的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="b62f4-106">These string values are essentially an XML string encapsulated in an XML CDATA section.</span></span> <span data-ttu-id="b62f4-107">符合适配器客户端尝试发送或接收的集成对象的 XML 架构的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="b62f4-107">The XML string is compatible with the XML schema of the integration object the adapter client is trying to send or receive.</span></span>  
  
## <a name="sample-based-on-this-topic"></a><span data-ttu-id="b62f4-108">基于本主题的示例</span><span class="sxs-lookup"><span data-stu-id="b62f4-108">Sample Based On This Topic</span></span>  
 <span data-ttu-id="b62f4-109">示例中，SiebelAdapterIntegrationObjects，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b62f4-109">A sample, SiebelAdapterIntegrationObjects, based on this topic is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b62f4-110">有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b62f4-110">For more information, see [Samples for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md).</span></span>
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a><span data-ttu-id="b62f4-111">创建业务流程调用具有集成对象的业务服务方法</span><span class="sxs-lookup"><span data-stu-id="b62f4-111">Creating an Orchestration to Invoke Business Service Methods with Integration Objects</span></span>  
 <span data-ttu-id="b62f4-112">中所述创建业务流程来调用采用对象参数的集成的业务服务方法是类似于业务流程来调用任何其他业务服务，[调用业务服务方法使用 BizTalk Server 和Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b62f4-112">Creating an orchestration to invoke a business service method that takes integration object parameters is similar to the orchestration to invoke any other business service, as described in [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
 <span data-ttu-id="b62f4-113">区别在于删除业务流程的请求消息。</span><span class="sxs-lookup"><span data-stu-id="b62f4-113">The difference lies in the request message that you drop for the orchestration.</span></span> <span data-ttu-id="b62f4-114">这种差异是由于下列原因：</span><span class="sxs-lookup"><span data-stu-id="b62f4-114">This difference is because of the following:</span></span>  
  
-   <span data-ttu-id="b62f4-115">请求消息的架构是不同的因为调用不同的业务服务。</span><span class="sxs-lookup"><span data-stu-id="b62f4-115">The schema for the request message is different because you invoke a different business service.</span></span>  
  
-   <span data-ttu-id="b62f4-116">请求消息包含集成对象的 XML 字符串。</span><span class="sxs-lookup"><span data-stu-id="b62f4-116">The request message contains the XML string for the integration object.</span></span> <span data-ttu-id="b62f4-117">此 XML 将封装在 CDATA 节。</span><span class="sxs-lookup"><span data-stu-id="b62f4-117">This XML is encapsulated in a CDATA section.</span></span> <span data-ttu-id="b62f4-118">你必须首先生成集成对象的架构，然后创建符合架构的 XML。</span><span class="sxs-lookup"><span data-stu-id="b62f4-118">You must first generate the schema for the integration object and then create an XML that conforms to the schema.</span></span> <span data-ttu-id="b62f4-119">必须在请求消息发送到适配器的 CDATA 节内传递此 XML。</span><span class="sxs-lookup"><span data-stu-id="b62f4-119">This XML must be passed within the CDATA section of the request message sent to the adapter.</span></span>  
  
 <span data-ttu-id="b62f4-120">生成的 XML，符合集成对象架构并包含在请求消息之后，你必须在文件位置，像你那样适用于任何其他业务流程删除请求消息。</span><span class="sxs-lookup"><span data-stu-id="b62f4-120">After you have generated the XML that conforms to the integration object schema and included it in the request message, you must drop the request message at a FILE location, just like you do for any other orchestration.</span></span> <span data-ttu-id="b62f4-121">寻找响应消息中的其他文件位置。</span><span class="sxs-lookup"><span data-stu-id="b62f4-121">Look for the response message in the other FILE location.</span></span>  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a><span data-ttu-id="b62f4-122">请求和响应消息，用于调用具有集成对象的业务服务</span><span class="sxs-lookup"><span data-stu-id="b62f4-122">Request and Response Messages for Invoking Business Service with Integration Objects</span></span>  
 <span data-ttu-id="b62f4-123">如前文所述，调用采用对象参数的集成的业务服务的唯一区别是请求消息发送到适配器。</span><span class="sxs-lookup"><span data-stu-id="b62f4-123">As mentioned before, the only difference for invoking a business service that takes integration object parameters is the request message sent to the adapter.</span></span> <span data-ttu-id="b62f4-124">此部分提供有关创建请求消息时必须执行的步骤的说明。</span><span class="sxs-lookup"><span data-stu-id="b62f4-124">This section provides instructions on the steps you must perform to create the request message.</span></span>  
  
 <span data-ttu-id="b62f4-125">为便于理解，例如需要 Siebel 业务服务 EAI Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="b62f4-125">For better understanding, take a Siebel business service 'EAI Siebel Adapter' as an example.</span></span> <span data-ttu-id="b62f4-126">EAI Siebel 适配器业务服务进行 Siebel 集成对象，' 示例帐户 ' 操作。</span><span class="sxs-lookup"><span data-stu-id="b62f4-126">The 'EAI Siebel Adapter' business service operates on a Siebel integration object, 'Sample Account'.</span></span> <span data-ttu-id="b62f4-127">你必须执行以下任务来创建要调用 EAI Siebel 适配器业务服务所公开的方法的请求消息：</span><span class="sxs-lookup"><span data-stu-id="b62f4-127">You must perform the following tasks to create the request message to invoke a method exposed by the 'EAI Siebel Adapter' business service:</span></span>  
  
-   <span data-ttu-id="b62f4-128">**生成 EAI Siebel 适配器业务服务的架构**。</span><span class="sxs-lookup"><span data-stu-id="b62f4-128">**Generate the schema for the EAI Siebel Adapter business service**.</span></span> <span data-ttu-id="b62f4-129">必须使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。</span><span class="sxs-lookup"><span data-stu-id="b62f4-129">You must use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate the schema.</span></span> <span data-ttu-id="b62f4-130">后生成架构时，都会生成符合架构的 XML。</span><span class="sxs-lookup"><span data-stu-id="b62f4-130">Once you generate the schema, generate the XML that conforms to the schema.</span></span>  
  
-   <span data-ttu-id="b62f4-131">**生成集成对象的架构**。</span><span class="sxs-lookup"><span data-stu-id="b62f4-131">**Generate the schema for the integration object**.</span></span> <span data-ttu-id="b62f4-132">使用 Siebel 工具来生成集成对象的架构。</span><span class="sxs-lookup"><span data-stu-id="b62f4-132">Use Siebel Tools to generate schema for an integration object.</span></span> <span data-ttu-id="b62f4-133">从 Siebel 工具界面中，选择集成对象，例如，示例帐户，然后单击**生成架构**。</span><span class="sxs-lookup"><span data-stu-id="b62f4-133">From the Siebel Tools interface, select the integration object, for example, Sample Account, and click **Generate Schema**.</span></span> <span data-ttu-id="b62f4-134">生成时的架构，请确保：</span><span class="sxs-lookup"><span data-stu-id="b62f4-134">While generating the schema, make sure:</span></span>  
  
    -   <span data-ttu-id="b62f4-135">**从列表中选择一种业务服务**下拉列表具有"EAI XML XSD Generator"的值。</span><span class="sxs-lookup"><span data-stu-id="b62f4-135">The **Select a Business Service from the list** drop-down has the value "EAI XML XSD Generator".</span></span>  
  
    -   <span data-ttu-id="b62f4-136">**从列表中选择信封类型**下拉列表具有"Siebel 消息信封"的值。</span><span class="sxs-lookup"><span data-stu-id="b62f4-136">The **Select an envelope type from the list** drop-down has the value "Siebel Message Envelope".</span></span>  
  
     <span data-ttu-id="b62f4-137">有关详细信息，请参阅 Siebel 文档。</span><span class="sxs-lookup"><span data-stu-id="b62f4-137">For more information, see the Siebel documentation.</span></span>  
  
-   <span data-ttu-id="b62f4-138">**创建一个与集成对象的架构一致的 XML 消息**。</span><span class="sxs-lookup"><span data-stu-id="b62f4-138">**Create an XML message that conforms to schema of the integration object**.</span></span> <span data-ttu-id="b62f4-139">为示例帐户集成对象生成的示例 XML 消息如下所示：</span><span class="sxs-lookup"><span data-stu-id="b62f4-139">A sample XML message generated for the 'Sample Account' integration object looks like:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="UTF-16"?>  
    <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
      <ListOfSampleAccount>  
        <Account>  
          <CurrencyCode>USD</CurrencyCode>  
          <Location>Redmond</Location>  
          <Name>IntegrationObjectTest</Name>  
        </Account>  
      </ListOfSampleAccount>  
    </SiebelMessage>  
    ```  
  
-   <span data-ttu-id="b62f4-140">**将此 XML 消息作为业务服务方法的请求消息中的 CDATA 元素的值传递**。</span><span class="sxs-lookup"><span data-stu-id="b62f4-140">**Pass this XML message as the value for the CDATA element in the request message for the business service method**.</span></span> <span data-ttu-id="b62f4-141">包含在 CDATA 元素中的前一个 XML 消息的示例请求消息如下所示。</span><span class="sxs-lookup"><span data-stu-id="b62f4-141">A sample request message that contains the preceding XML message within a CDATA element looks like the following.</span></span> <span data-ttu-id="b62f4-142">此示例请求是调用 Insert 方法 EAI Siebel 适配器业务服务。</span><span class="sxs-lookup"><span data-stu-id="b62f4-142">This sample request is to invoke the Insert method for the 'EAI Siebel Adapter' business service.</span></span>  
  
    ```  
    <Insert xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
      <InsertRequestRecord />   
      <InsertInOutRecord>  
        <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
          <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
            <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
              <ListOfSampleAccount>  
                <Account>  
                  <CurrencyCode>USD</CurrencyCode>  
                  <Location>Redmond</Location>  
                  <Name>IntegrationObjectTest</Name>  
                </Account>  
              </ListOfSampleAccount>  
            </SiebelMessage>  
          ]]>   
         </SiebelMessage>  
      </InsertInOutRecord>  
    </Insert>  
    ```  
  
     <span data-ttu-id="b62f4-143">Siebel 上面的请求消息的响应如下所示：</span><span class="sxs-lookup"><span data-stu-id="b62f4-143">The response from Siebel for the above request message resembles the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <InsertResponse xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter/Operation">  
      <InsertResult>  
        <ErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">0x0</ErrorCode>   
        <ErrorContextIntComp xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <ErrorContextSearchSpec xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <ErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <OMErrorCode xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <OMErrorSymbol xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter" />   
        <PrimaryRowId xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">1-6SPSJ</PrimaryRowId>   
      </InsertResult>  
      <InsertInOutRecord>  
        <SiebelMessage xmlns="http://Microsoft.LobServices.Siebel/2007/03/BusinessServices/EAI_x0020_Siebel_x0020_Adapter">  
          <![CDATA[ <?xml version="1.0" encoding="UTF-16"?>  
            <SiebelMessage  MessageId="" IntObjectName="Sample Account" MessageType="Integration Object" IntObjectFormat="Siebel Hierarchical">  
              <ListOfSampleAccount>  
                <Account>  
                  <CurrencyCode>USD</CurrencyCode>  
                  <Location>Redmond</Location>  
                  <Name>IntegrationObjectTest</Name>  
                </Account>  
              </ListOfSampleAccount>  
            </SiebelMessage>  
          ]]>   
         </SiebelMessage>  
      </InsertInOutRecord>  
    </InsertResponse>  
    ```  
  
 <span data-ttu-id="b62f4-144">使用 BizTalk 功能，适配器客户端还可以执行其他验证的集成对象 IN 和扩展参数针对集成对象架构 （从获取 Siebel 工具。）</span><span class="sxs-lookup"><span data-stu-id="b62f4-144">Using BizTalk features, adapter clients can also perform additional validation of the integration object IN and OUT parameter against the integration object schema (obtained from Siebel Tools.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b62f4-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b62f4-145">See Also</span></span>  
<span data-ttu-id="b62f4-146">[开发使用 Siebel 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span><span class="sxs-lookup"><span data-stu-id="b62f4-146">[Develop BizTalk Applications using the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)  </span></span>  
[<span data-ttu-id="b62f4-147">开发 Siebel 应用程序</span><span class="sxs-lookup"><span data-stu-id="b62f4-147">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)