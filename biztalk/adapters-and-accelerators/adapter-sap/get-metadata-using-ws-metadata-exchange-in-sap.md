---
title: 获取在 SAP 中使用 Ws-metadata Exchange 的元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange
- how to, retrieve metadata
- retrieving metadata
ms.assetid: 29f85963-ac7f-4e13-96b8-bc2c94a9fcae
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae33fd76725abf15f12d95be39997fc29e67403e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216877"
---
# <a name="get-metadata-using-ws-metadata-exchange-in-sap"></a>获取在 SAP 中使用 Ws-metadata Exchange 的元数据
作为[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定，[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开可用于检索元数据中的特定操作的 WS 元数据交换 (MEX) 终结点[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
 WCF 提供了丰富的基础结构，用于导出、 发布、 检索和导入有关服务的元数据。 WCF 服务，例如适配器，使用元数据来描述如何与服务终结点进行交互，以便像 svcutil.exe，这样的工具，可以自动生成使用服务的客户端代码。 WCF 服务的元数据表示实例的形式**MetadataSet**类型，被强附加到定义中 WS 元数据交换 (MEX) 元数据序列化格式。 你可以创建**MetadataSet**目标上的操作使用的适配器**MetadataExchangeClient**。  
  
 WCF 支持元数据交换是广泛主题超出了本文档的范围。 有关在 WCF 中的元数据支持的详细信息，请参见"元数据"中的 WCF 文档[http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634)。 有关体系结构的特别好说明，类和命名空间中 WCF 公开的元数据，请参阅"元数据体系结构概述"在[http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635)。 你应该熟悉与从之前这些 WCF 主题中的 WCF 服务检索元数据相关的内容。  
  
 以下主题包含有关如何使用信息**MetadataExchangeClient**以检索元数据从[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a>使用 MetadataExchangeClient 检索元数据  
 若要使用**MetadataExchangeClient**必须指定连接 URI 和绑定 (**SAPBinding**)。 连接 URI 标识你想要检索元数据的操作。  
  
 以下各节提供有关如何指定连接 URI，重要的绑定属性，以及如何使用信息**MetadataExchangeClient**从适配器中检索元数据。  
  
### <a name="the-connection-uri"></a>连接 URI  
 若要使用**MetadataExchangeClient**必须提供 SAP 连接 URI，指定 MEX 终结点的操作或你想要检索元数据的操作。 按以下方式，可以在连接 URI 中指定 MEX 终结点和目标操作：  
  
-   你必须查询字符串中包含"wsdl"参数。 如果是查询字符串中的第一个参数，其指定为问号 （？） 之后。 如果它不是第一个参数，它应在它前面加一个与号 (&)。  
  
-   你必须执行一个或多个"op"参数"wsdl"的参数。 每个"op"参数前面是一个与号 (&)，并指定目标操作的消息操作 (节点 ID)。  
  
 例如，以下连接 URI 面向 SALESORDER_CREATEFROMDAT201 IDOC 和 SALESORDER_CREATEFROMDAT202 IDOC 的发送操作。 突出显示的"wsdl"和"op"参数。  
  
```  
"sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"  
```  
  
> [!NOTE]
>  不需要在入站操作连接 URI 中包含侦听器参数。 适配器将连接作为客户端从 SAP 系统中检索元数据。  
  
 你还可以使用在定义的常量`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`来帮助你创建一个连接 URI 时指定的操作。 在本主题末尾的代码示例说明了这一点。  
  
 你将此连接 URI 的传递到**MetadataExchangeClient**取决于你用于创建客户端并从适配器检索元数据的重载方法。  
  
 有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
### <a name="binding-properties"></a>绑定属性  
 当你创建**MetadataExchangeClient**，必须指定**SAPBinding**。  
  
 有几个绑定属性影响如何适配器生成元数据。 这些属性包括：  
  
-   **GenerateFlatfileCompatibleIdocSchema**  
  
-   **ReceiveIDocFormat**  
  
-   **EnableSafeTyping**  
  
-   **FlatFileSegmentIndicator**  
  
 你应确保这些绑定属性被设置为之前调用你的应用程序所需的值**GetMetadata**方法**MetadataExchangeClient**。 有关 SAP 适配器绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
### <a name="example"></a>示例  
 下面的示例使用**MetadataExchangeClient** BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK 操作创建的服务说明 （WSDL 文档）。  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Collections.ObjectModel;  
  
// Needed for WCF and SAP adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.SAP;  
  
// Needed for MetadataExchangeClient class  
using System.ServiceModel.Description;  
// Needed for ServiceDescription class  
using System.Web.Services;  
  
namespace SapMetadataExchangeClient  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            //Create a binding  
            SAPBinding binding = new SAPBinding();  
  
            //Create a metadata exchange client that will retrieve metadata according to the WS-MEX standard.  
            MetadataExchangeClient client = new MetadataExchangeClient(binding);  
            client.SoapCredentials.UserName.UserName = "YourUserName";  
            client.SoapCredentials.UserName.Password = "YourPassword";  
  
            //Set up an endpoint address and specify the operation for which we want metadata.  
            string connectionUri = "sap://Client=800;lang=EN@A/YourSAPHost/00?wsdl&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_COMMIT"  
                + "&op="  
                + Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix  
                + "BAPI_TRANSACTION_ROLLBACK";  
  
            EndpointAddress address = new EndpointAddress(connectionUri);  
  
            //Get the metadata.  
            MetadataSet ms = client.GetMetadata(address);  
  
            // Check for the metadata set size.   
            Collection<MetadataSection> documentCollection = ms.MetadataSections;  
            if (documentCollection != null && documentCollection.Count > 0)  
            {  
                //Get the WSDL from the metadata set  
                System.Web.Services.Description.ServiceDescription wsdl = (System.Web.Services.Description.ServiceDescription)documentCollection[0].Metadata;  
  
                //Save the WSDL to a file.  
                wsdl.Write("BapiTx.wsdl");    
  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [从 SAP 以编程方式检索元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)   
 [SAP 使用 IMetadataRetrievalContract 中检索元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)