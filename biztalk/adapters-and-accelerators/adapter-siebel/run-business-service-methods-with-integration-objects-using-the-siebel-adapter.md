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
# <a name="invoke-business-service-methods-with-integration-objects-using-the-siebel-adapter"></a>调用具有集成对象使用 Siebel 适配器的业务服务方法
[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端调用使用集成的对象的业务服务方法。 这些业务服务通常有 IN、 输出、 或的"层次结构"数据 IN OUT 参数键入发送或接收集成对象数据。  
  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开这些分层类型作为字符串。 这些字符串值是实质上是封装在一个 XML CDATA 节的 XML 字符串。 符合适配器客户端尝试发送或接收的集成对象的 XML 架构的 XML 字符串。  
  
## <a name="sample-based-on-this-topic"></a>基于本主题的示例  
 示例中，SiebelAdapterIntegrationObjects，基于本主题还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[Siebel 适配器的示例](../../adapters-and-accelerators/adapter-siebel/samples-for-the-siebel-adapter.md)。
  
## <a name="creating-an-orchestration-to-invoke-business-service-methods-with-integration-objects"></a>创建业务流程调用具有集成对象的业务服务方法  
 中所述创建业务流程来调用采用对象参数的集成的业务服务方法是类似于业务流程来调用任何其他业务服务，[调用业务服务方法使用 BizTalk Server 和Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)。  
  
 区别在于删除业务流程的请求消息。 这种差异是由于下列原因：  
  
-   请求消息的架构是不同的因为调用不同的业务服务。  
  
-   请求消息包含集成对象的 XML 字符串。 此 XML 将封装在 CDATA 节。 你必须首先生成集成对象的架构，然后创建符合架构的 XML。 必须在请求消息发送到适配器的 CDATA 节内传递此 XML。  
  
 生成的 XML，符合集成对象架构并包含在请求消息之后，你必须在文件位置，像你那样适用于任何其他业务流程删除请求消息。 寻找响应消息中的其他文件位置。  
  
## <a name="request-and-response-messages-for-invoking-business-service-with-integration-objects"></a>请求和响应消息，用于调用具有集成对象的业务服务  
 如前文所述，调用采用对象参数的集成的业务服务的唯一区别是请求消息发送到适配器。 此部分提供有关创建请求消息时必须执行的步骤的说明。  
  
 为便于理解，例如需要 Siebel 业务服务 EAI Siebel 适配器。 EAI Siebel 适配器业务服务进行 Siebel 集成对象，' 示例帐户 ' 操作。 你必须执行以下任务来创建要调用 EAI Siebel 适配器业务服务所公开的方法的请求消息：  
  
-   **生成 EAI Siebel 适配器业务服务的架构**。 必须使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。 后生成架构时，都会生成符合架构的 XML。  
  
-   **生成集成对象的架构**。 使用 Siebel 工具来生成集成对象的架构。 从 Siebel 工具界面中，选择集成对象，例如，示例帐户，然后单击**生成架构**。 生成时的架构，请确保：  
  
    -   **从列表中选择一种业务服务**下拉列表具有"EAI XML XSD Generator"的值。  
  
    -   **从列表中选择信封类型**下拉列表具有"Siebel 消息信封"的值。  
  
     有关详细信息，请参阅 Siebel 文档。  
  
-   **创建一个与集成对象的架构一致的 XML 消息**。 为示例帐户集成对象生成的示例 XML 消息如下所示：  
  
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
  
-   **将此 XML 消息作为业务服务方法的请求消息中的 CDATA 元素的值传递**。 包含在 CDATA 元素中的前一个 XML 消息的示例请求消息如下所示。 此示例请求是调用 Insert 方法 EAI Siebel 适配器业务服务。  
  
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
  
     Siebel 上面的请求消息的响应如下所示：  
  
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
  
 使用 BizTalk 功能，适配器客户端还可以执行其他验证的集成对象 IN 和扩展参数针对集成对象架构 （从获取 Siebel 工具。）  
  
## <a name="see-also"></a>另请参阅  
[开发使用 Siebel 适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)    
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)