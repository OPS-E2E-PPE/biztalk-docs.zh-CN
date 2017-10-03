---
title: "获取在 SAP 中使用 Ws-metadata Exchange 的元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange
- how to, retrieve metadata
- retrieving metadata
ms.assetid: 29f85963-ac7f-4e13-96b8-bc2c94a9fcae
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae33fd76725abf15f12d95be39997fc29e67403e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-using-ws-metadata-exchange-in-sap"></a><span data-ttu-id="cca8a-102">获取在 SAP 中使用 Ws-metadata Exchange 的元数据</span><span class="sxs-lookup"><span data-stu-id="cca8a-102">Get Metadata Using WS-Metadata Exchange in SAP</span></span>
<span data-ttu-id="cca8a-103">作为[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定，[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开可用于检索元数据中的特定操作的 WS 元数据交换 (MEX) 终结点[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cca8a-103">As a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding, the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes a WS-Metadata Exchange (MEX) endpoint that you can use to retrieve metadata for specific operations from the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
 <span data-ttu-id="cca8a-104">WCF 提供了丰富的基础结构，用于导出、 发布、 检索和导入有关服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="cca8a-104">WCF provides a rich infrastructure for exporting, publishing, retrieving and importing metadata about a service.</span></span> <span data-ttu-id="cca8a-105">WCF 服务，例如适配器，使用元数据来描述如何与服务终结点进行交互，以便像 svcutil.exe，这样的工具，可以自动生成使用服务的客户端代码。</span><span class="sxs-lookup"><span data-stu-id="cca8a-105">WCF services, like the adapter, use metadata to describe how to interact with the service endpoints so that tools, like svcutil.exe, can automatically generate client code for consuming the service.</span></span> <span data-ttu-id="cca8a-106">WCF 服务的元数据表示实例的形式**MetadataSet**类型，被强附加到定义中 WS 元数据交换 (MEX) 元数据序列化格式。</span><span class="sxs-lookup"><span data-stu-id="cca8a-106">WCF represents the metadata for a service as an instance of the **MetadataSet** type, which is strongly tied to the metadata serialization format defined in WS-Metadata Exchange (MEX).</span></span> <span data-ttu-id="cca8a-107">你可以创建**MetadataSet**目标上的操作使用的适配器**MetadataExchangeClient**。</span><span class="sxs-lookup"><span data-stu-id="cca8a-107">You can create a **MetadataSet** for targeted operations on the adapter by using a **MetadataExchangeClient**.</span></span>  
  
 <span data-ttu-id="cca8a-108">WCF 支持元数据交换是广泛主题超出了本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="cca8a-108">WCF support for metadata exchange is an expansive topic and beyond the scope of this documentation.</span></span> <span data-ttu-id="cca8a-109">有关在 WCF 中的元数据支持的详细信息，请参见"元数据"中的 WCF 文档[http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634)。</span><span class="sxs-lookup"><span data-stu-id="cca8a-109">For more information about support for metadata in WCF, see "Metadata" in the WCF documentation at [http://go.microsoft.com/fwlink/?LinkId=105634](http://go.microsoft.com/fwlink/?LinkId=105634).</span></span> <span data-ttu-id="cca8a-110">有关体系结构的特别好说明，类和命名空间中 WCF 公开的元数据，请参阅"元数据体系结构概述"在[http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635)。</span><span class="sxs-lookup"><span data-stu-id="cca8a-110">For a particularly good description of the architecture, classes, and namespaces that WCF exposes for metadata, see "Metadata Architecture Overview" at [http://go.microsoft.com/fwlink/?LinkId=105635](http://go.microsoft.com/fwlink/?LinkId=105635).</span></span> <span data-ttu-id="cca8a-111">你应该熟悉与从之前这些 WCF 主题中的 WCF 服务检索元数据相关的内容。</span><span class="sxs-lookup"><span data-stu-id="cca8a-111">You should familiarize yourself with the content related to retrieving metadata from a WCF service in these WCF topics before proceeding.</span></span>  
  
 <span data-ttu-id="cca8a-112">以下主题包含有关如何使用信息**MetadataExchangeClient**以检索元数据从[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cca8a-112">The following topics contain information about how to use a **MetadataExchangeClient** to retrieve metadata from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="using-a-metadataexchangeclient-to-retrieve-metadata"></a><span data-ttu-id="cca8a-113">使用 MetadataExchangeClient 检索元数据</span><span class="sxs-lookup"><span data-stu-id="cca8a-113">Using a MetadataExchangeClient to Retrieve Metadata</span></span>  
 <span data-ttu-id="cca8a-114">若要使用**MetadataExchangeClient**必须指定连接 URI 和绑定 (**SAPBinding**)。</span><span class="sxs-lookup"><span data-stu-id="cca8a-114">To use a **MetadataExchangeClient** you must specify a connection URI and a binding (**SAPBinding**).</span></span> <span data-ttu-id="cca8a-115">连接 URI 标识你想要检索元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="cca8a-115">The connection URI identifies the operations for which you want to retrieve metadata.</span></span>  
  
 <span data-ttu-id="cca8a-116">以下各节提供有关如何指定连接 URI，重要的绑定属性，以及如何使用信息**MetadataExchangeClient**从适配器中检索元数据。</span><span class="sxs-lookup"><span data-stu-id="cca8a-116">The following sections contain information about how to specify the connection URI, important binding properties, and how to use a **MetadataExchangeClient** to retrieve metadata from the adapter.</span></span>  
  
### <a name="the-connection-uri"></a><span data-ttu-id="cca8a-117">连接 URI</span><span class="sxs-lookup"><span data-stu-id="cca8a-117">The Connection URI</span></span>  
 <span data-ttu-id="cca8a-118">若要使用**MetadataExchangeClient**必须提供 SAP 连接 URI，指定 MEX 终结点的操作或你想要检索元数据的操作。</span><span class="sxs-lookup"><span data-stu-id="cca8a-118">To use the **MetadataExchangeClient** you must supply a SAP connection URI that specifies a MEX endpoint and the operation or operations for which you want to retrieve metadata.</span></span> <span data-ttu-id="cca8a-119">按以下方式，可以在连接 URI 中指定 MEX 终结点和目标操作：</span><span class="sxs-lookup"><span data-stu-id="cca8a-119">You specify a MEX endpoint and target operations in the connection URI in the following manner:</span></span>  
  
-   <span data-ttu-id="cca8a-120">你必须查询字符串中包含"wsdl"参数。</span><span class="sxs-lookup"><span data-stu-id="cca8a-120">You must include the "wsdl" parameter in the query string.</span></span> <span data-ttu-id="cca8a-121">如果是查询字符串中的第一个参数，其指定为问号 （？） 之后。</span><span class="sxs-lookup"><span data-stu-id="cca8a-121">If it is the first parameter in the query string, it is specified just after the question mark (?).</span></span> <span data-ttu-id="cca8a-122">如果它不是第一个参数，它应在它前面加一个与号 (&)。</span><span class="sxs-lookup"><span data-stu-id="cca8a-122">If it is not the first parameter, it should be preceded with an ampersand (&).</span></span>  
  
-   <span data-ttu-id="cca8a-123">你必须执行一个或多个"op"参数"wsdl"的参数。</span><span class="sxs-lookup"><span data-stu-id="cca8a-123">You must follow the "wsdl" parameter by one or more "op" parameters.</span></span> <span data-ttu-id="cca8a-124">每个"op"参数前面是一个与号 (&)，并指定目标操作的消息操作 (节点 ID)。</span><span class="sxs-lookup"><span data-stu-id="cca8a-124">Each "op" parameter is preceded by an ampersand (&) and specifies the message action (node ID) of a target operation.</span></span>  
  
 <span data-ttu-id="cca8a-125">例如，以下连接 URI 面向 SALESORDER_CREATEFROMDAT201 IDOC 和 SALESORDER_CREATEFROMDAT202 IDOC 的发送操作。</span><span class="sxs-lookup"><span data-stu-id="cca8a-125">For example, the following connection URI targets the Send operation for the SALESORDER_CREATEFROMDAT201 IDOC and the SALESORDER_CREATEFROMDAT202 IDOC.</span></span> <span data-ttu-id="cca8a-126">突出显示的"wsdl"和"op"参数。</span><span class="sxs-lookup"><span data-stu-id="cca8a-126">The "wsdl" and "op" parameters are highlighted.</span></span>  
  
```  
"sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"  
```  
  
> [!NOTE]
>  <span data-ttu-id="cca8a-127">不需要在入站操作连接 URI 中包含侦听器参数。</span><span class="sxs-lookup"><span data-stu-id="cca8a-127">It is not necessary to include listener parameters in the connection URI for inbound operations.</span></span> <span data-ttu-id="cca8a-128">适配器将连接作为客户端从 SAP 系统中检索元数据。</span><span class="sxs-lookup"><span data-stu-id="cca8a-128">The adapter connects as a client to retrieve metadata from the SAP system.</span></span>  
  
 <span data-ttu-id="cca8a-129">你还可以使用在定义的常量`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`来帮助你创建一个连接 URI 时指定的操作。</span><span class="sxs-lookup"><span data-stu-id="cca8a-129">You can also use the constants defined at `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` to help you specify operations when you create a connection URI.</span></span> <span data-ttu-id="cca8a-130">在本主题末尾的代码示例说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="cca8a-130">This is demonstrated in the code example at the end of this topic.</span></span>  
  
 <span data-ttu-id="cca8a-131">你将此连接 URI 的传递到**MetadataExchangeClient**取决于你用于创建客户端并从适配器检索元数据的重载方法。</span><span class="sxs-lookup"><span data-stu-id="cca8a-131">How you pass this connection URI to the **MetadataExchangeClient** depends on which of the overloaded methods you use to create the client and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="cca8a-132">有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="cca8a-132">For more information about the SAP connection URI, see [Create the SAP System Connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="cca8a-133">绑定属性</span><span class="sxs-lookup"><span data-stu-id="cca8a-133">Binding Properties</span></span>  
 <span data-ttu-id="cca8a-134">当你创建**MetadataExchangeClient**，必须指定**SAPBinding**。</span><span class="sxs-lookup"><span data-stu-id="cca8a-134">When you create the **MetadataExchangeClient**, you must specify an **SAPBinding**.</span></span>  
  
 <span data-ttu-id="cca8a-135">有几个绑定属性影响如何适配器生成元数据。</span><span class="sxs-lookup"><span data-stu-id="cca8a-135">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="cca8a-136">这些属性包括：</span><span class="sxs-lookup"><span data-stu-id="cca8a-136">These properties are:</span></span>  
  
-   <span data-ttu-id="cca8a-137">**GenerateFlatfileCompatibleIdocSchema**</span><span class="sxs-lookup"><span data-stu-id="cca8a-137">**GenerateFlatfileCompatibleIdocSchema**</span></span>  
  
-   <span data-ttu-id="cca8a-138">**ReceiveIDocFormat**</span><span class="sxs-lookup"><span data-stu-id="cca8a-138">**ReceiveIDocFormat**</span></span>  
  
-   <span data-ttu-id="cca8a-139">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="cca8a-139">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="cca8a-140">**FlatFileSegmentIndicator**</span><span class="sxs-lookup"><span data-stu-id="cca8a-140">**FlatFileSegmentIndicator**</span></span>  
  
 <span data-ttu-id="cca8a-141">你应确保这些绑定属性被设置为之前调用你的应用程序所需的值**GetMetadata**方法**MetadataExchangeClient**。</span><span class="sxs-lookup"><span data-stu-id="cca8a-141">You should ensure that these binding properties are set to the values required for your application before you invoke the **GetMetadata** method on the **MetadataExchangeClient**.</span></span> <span data-ttu-id="cca8a-142">有关 SAP 适配器绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="cca8a-142">For more information about the SAP adapter binding properties, see [Read about BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
### <a name="example"></a><span data-ttu-id="cca8a-143">示例</span><span class="sxs-lookup"><span data-stu-id="cca8a-143">Example</span></span>  
 <span data-ttu-id="cca8a-144">下面的示例使用**MetadataExchangeClient** BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK 操作创建的服务说明 （WSDL 文档）。</span><span class="sxs-lookup"><span data-stu-id="cca8a-144">The following example uses a **MetadataExchangeClient** to create a service description (WSDL document) for the BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK operations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cca8a-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cca8a-145">See Also</span></span>  
 <span data-ttu-id="cca8a-146">[从 SAP 以编程方式检索元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md) </span><span class="sxs-lookup"><span data-stu-id="cca8a-146">[Retrieving Metadata Programmatically from SAP](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md) </span></span>  
 [<span data-ttu-id="cca8a-147">SAP 使用 IMetadataRetrievalContract 中检索元数据</span><span class="sxs-lookup"><span data-stu-id="cca8a-147">Retrieving Metadata in SAP using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)