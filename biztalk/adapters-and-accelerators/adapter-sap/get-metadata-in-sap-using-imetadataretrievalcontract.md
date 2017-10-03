---
title: "SAP 使用 IMetadataRetrievalContract 中获取元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, search metadata
- searching metadata
- how to, browse metadata
- browsing metadata
ms.assetid: 0944fc39-9ee5-4702-8b52-e0bc87f202c6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efa36eee26dd9467a71f7e8dd4d28d2e37e26606
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-in-sap-using-imetadataretrievalcontract"></a><span data-ttu-id="e5d2b-102">SAP 使用 IMetadataRetrievalContract 中获取元数据</span><span class="sxs-lookup"><span data-stu-id="e5d2b-102">Get Metadata in SAP using IMetadataRetrievalContract</span></span>
<span data-ttu-id="e5d2b-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开**IMetadataRetrievalContract**可用来浏览和搜索个 SAP 系统的项目，并以检索 Web 服务描述语言 (WSDL) 文档形式的元数据的终结点操作。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] exposes an **IMetadataRetrievalContract**endpoint that you can use to browse and search for SAP system artifacts and to retrieve metadata in the form of a Web Services Description Language (WSDL) document for operations.</span></span>  
  
 <span data-ttu-id="e5d2b-104">**IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]和浏览、 搜索和检索功能可提供元数据。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-104">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and provides metadata browse, search, and retrieval capabilities.</span></span> <span data-ttu-id="e5d2b-105">除了**IMetadataRetrievalContract**接口，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公开**MetadataRetrievalClient**类，该类实现接口。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-105">In addition to the **IMetadataRetrievalContract** interface, the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] exposes the **MetadataRetrievalClient** class, which implements the interface.</span></span> <span data-ttu-id="e5d2b-106">你可以使用**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**要使用元数据; 公开给浏览、 搜索和检索元数据的方法是在每个用例中相同。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-106">You can use either an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with metadata; the methods exposed to browse, search, and retrieve metadata are the same in each case.</span></span>  
  
 <span data-ttu-id="e5d2b-107">以下各节提供有关如何使用信息**IMetadataRetrievalContract**接口。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-107">The following sections provide information about how to use the **IMetadataRetrievalContract** interface.</span></span>  
  
## <a name="the-imetadataretrievalcontract-interface"></a><span data-ttu-id="e5d2b-108">IMetadataRetrievalContract 接口</span><span class="sxs-lookup"><span data-stu-id="e5d2b-108">The IMetadataRetrievalContract Interface</span></span>  
 <span data-ttu-id="e5d2b-109">下表提供了有关在处理时使用的重要类的信息**IMetadataRetrievalContract**接口。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-109">The following table provides information about important classes that are used when you work with the **IMetadataRetrievalContract** interface.</span></span>  
  
|<span data-ttu-id="e5d2b-110">类或接口</span><span class="sxs-lookup"><span data-stu-id="e5d2b-110">Class or Interface</span></span>|<span data-ttu-id="e5d2b-111">Description</span><span class="sxs-lookup"><span data-stu-id="e5d2b-111">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="e5d2b-112">**IMetadataRetrievalContract**接口</span><span class="sxs-lookup"><span data-stu-id="e5d2b-112">**IMetadataRetrievalContract** interface</span></span><br /><br /> <span data-ttu-id="e5d2b-113">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="e5d2b-113">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="e5d2b-114">定义**浏览**，**搜索**，和**GetMetadata**方法。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-114">Defines the **Browse**, **Search**, and **GetMetadata** methods.</span></span> <span data-ttu-id="e5d2b-115">你可以通过调用这些方法**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**用于适配器元数据。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-115">You invoke these methods either by using an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with adapter metadata.</span></span>|  
|<span data-ttu-id="e5d2b-116">**MetadataRetrievalClient**类</span><span class="sxs-lookup"><span data-stu-id="e5d2b-116">**MetadataRetrievalClient** class</span></span><br /><br /> <span data-ttu-id="e5d2b-117">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="e5d2b-117">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="e5d2b-118">实现**IMetadataRetrievalContract**接口。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-118">Implements the **IMetadataRetrievalContract** interface.</span></span> <span data-ttu-id="e5d2b-119">你可以创建此类的实例并将其配置为您的 SAP 系统，通过提供**SAPBinding**和**EndpointAddress**。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-119">You can create an instance of this class and configure it for your SAP system by providing an **SAPBinding** and an **EndpointAddress**.</span></span> <span data-ttu-id="e5d2b-120">然后，你可以调用其方法来处理元数据。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-120">Then you can invoke its methods to work with metadata.</span></span>|  
|<span data-ttu-id="e5d2b-121">**MetadataRetrievalNode**类</span><span class="sxs-lookup"><span data-stu-id="e5d2b-121">**MetadataRetrievalNode** class</span></span><br /><br /> <span data-ttu-id="e5d2b-122">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="e5d2b-122">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="e5d2b-123">表示在适配器上的元数据节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-123">Represents a metadata node on the adapter.</span></span> <span data-ttu-id="e5d2b-124">**浏览**和**搜索**方法返回此类型的节点和**GetMetadata**方法采用这种类型作为参数的节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-124">The **Browse** and **Search** methods return nodes of this type, and the **GetMetadata** method takes nodes of this type as a parameter.</span></span>|  
|<span data-ttu-id="e5d2b-125">**ServiceDescription**类</span><span class="sxs-lookup"><span data-stu-id="e5d2b-125">**ServiceDescription** class</span></span><br /><br /> <span data-ttu-id="e5d2b-126">(System.Web.Services.Description)</span><span class="sxs-lookup"><span data-stu-id="e5d2b-126">(System.Web.Services.Description)</span></span>|<span data-ttu-id="e5d2b-127">提供一种创建和格式设置有效的 WSDL 文档文件。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-127">Provides a means of creating and formatting a valid WSDL document file.</span></span> <span data-ttu-id="e5d2b-128">**GetMetadata**方法返回**ServiceDescription**对象。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-128">The **GetMetadata** method returns a **ServiceDescription** object.</span></span>|  
  
 <span data-ttu-id="e5d2b-129">有关详细信息**IMetadataRetrievalContract**接口， **MetadataRetrievalClient**类，与**MetadataRetrievalNode**类; 请参阅**Microsoft.ServiceModel.Channels**的托管引用在[http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566)。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-129">For more information about the **IMetadataRetrievalContract** interface, the **MetadataRetrievalClient** class, and the **MetadataRetrievalNode** class; see the **Microsoft.ServiceModel.Channels** managed reference at [http://go.microsoft.com/fwlink/?LinkId=105566](http://go.microsoft.com/fwlink/?LinkId=105566).</span></span>  
  
### <a name="metadata-node-ids"></a><span data-ttu-id="e5d2b-130">元数据节点 Id</span><span class="sxs-lookup"><span data-stu-id="e5d2b-130">Metadata Node IDs</span></span>  
 <span data-ttu-id="e5d2b-131">适配器将其元数据组织为节点的分层树。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-131">The adapter organizes its metadata as a hierarchical tree of nodes.</span></span> <span data-ttu-id="e5d2b-132">在此树状结构中有两种类型的元数据节点：</span><span class="sxs-lookup"><span data-stu-id="e5d2b-132">Within this tree structure there are two types of metadata nodes:</span></span>  
  
-   <span data-ttu-id="e5d2b-133">**操作节点**表示适配器显示在 SAP 项目的操作。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-133">**Operation nodes** represent operations that the adapter surfaces on SAP artifacts.</span></span> <span data-ttu-id="e5d2b-134">操作的节点的树的叶。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-134">Operation nodes are the leaves of the tree.</span></span>  
  
-   <span data-ttu-id="e5d2b-135">**类别节点**表示适配器上的操作的 SAP 项目并不直接对应的 SAP 项目的分组。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-135">**Category nodes** represent SAP artifacts and groupings of SAP artifacts that do not directly correspond to an operation on the adapter.</span></span> <span data-ttu-id="e5d2b-136">类别节点是树的分支它们包含其他类别节点和/或操作节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-136">Category nodes are the branches of the tree; they contain other category nodes and/or operation nodes.</span></span> <span data-ttu-id="e5d2b-137">例如，RFC 功能组或 SAP 业务对象表示为类别节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-137">For example, RFC functional groups or SAP business objects are represented as category nodes.</span></span>  
  
 <span data-ttu-id="e5d2b-138">每个适配器中加以表示的元数据节点标识的唯一节点 id。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-138">Each metadata node surfaced by the adapter is identified by a unique node ID.</span></span> <span data-ttu-id="e5d2b-139">有关元数据节点 Id 显示适配器的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-139">For more information about the metadata node IDs surfaced by the adapter, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span> <span data-ttu-id="e5d2b-140">这些节点 Id 用于使用时，指定目标 SAP 项目**IMetadataRetrievalContract**接口来浏览、 搜索和检索元数据。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-140">You use these node IDs to specify target SAP artifacts when you use the **IMetadataRetrievalContract** interface to browse, search, and retrieve metadata.</span></span> <span data-ttu-id="e5d2b-141">你可以使用中定义的常量`Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants`和`Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants`可帮助你构造元数据节点 Id。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-141">You can use the constants defined in `Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants` and `Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants` to help you construct metadata node IDs.</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="e5d2b-142">绑定属性</span><span class="sxs-lookup"><span data-stu-id="e5d2b-142">Binding Properties</span></span>  
 <span data-ttu-id="e5d2b-143">是否使用**IMetadataRetrievalContract**通道或**IMetadataRetrievalClient**若要使用元数据，必须指定**SAPBinding**创建时实例。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-143">Whether you use an **IMetadataRetrievalContract** channel or an **IMetadataRetrievalClient** to work with metadata, you must specify an **SAPBinding** when you create the instance.</span></span>  
  
 <span data-ttu-id="e5d2b-144">有几个绑定属性影响如何适配器生成元数据。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-144">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="e5d2b-145">这些属性包括：</span><span class="sxs-lookup"><span data-stu-id="e5d2b-145">These properties are:</span></span>  
  
-   <span data-ttu-id="e5d2b-146">**GenerateFlatfileCompatibleIdocSchema**</span><span class="sxs-lookup"><span data-stu-id="e5d2b-146">**GenerateFlatfileCompatibleIdocSchema**</span></span>  
  
-   <span data-ttu-id="e5d2b-147">**ReceiveIDocFormat**</span><span class="sxs-lookup"><span data-stu-id="e5d2b-147">**ReceiveIDocFormat**</span></span>  
  
-   <span data-ttu-id="e5d2b-148">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="e5d2b-148">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="e5d2b-149">**FlatFileSegmentIndicator**</span><span class="sxs-lookup"><span data-stu-id="e5d2b-149">**FlatFileSegmentIndicator**</span></span>  
  
 <span data-ttu-id="e5d2b-150">你应确保这些绑定属性都设置为在打开元数据检索对象之前，你的应用程序所需的值。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-150">You should ensure that these binding properties are set to the values required for your application before you open the metadata retrieval object.</span></span> <span data-ttu-id="e5d2b-151">有关 SAP 适配器绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-151">For more information about the SAP adapter binding properties, see [Read about  BizTalk Adapter for mySAP Business Suite Binding Properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
### <a name="browsing-metadata-nodes"></a><span data-ttu-id="e5d2b-152">浏览元数据节点</span><span class="sxs-lookup"><span data-stu-id="e5d2b-152">Browsing Metadata Nodes</span></span>  
 <span data-ttu-id="e5d2b-153">你使用**浏览**方法以返回中的父节点包含的所有元数据节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-153">You use the **Browse** method to return all the metadata nodes that are contained in a parent node.</span></span> <span data-ttu-id="e5d2b-154">下面的示例浏览 SAP 系统上的前三个 RFC 功能组。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-154">The following example browses for the first three RFC functional groups on the SAP system.</span></span> <span data-ttu-id="e5d2b-155">在此示例中，**客户端**是的一个实例**MetadataRetrievalClient**。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-155">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="e5d2b-156">只能浏览类别节点，则您无法浏览操作节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-156">You can only browse category nodes; you cannot browse operation nodes.</span></span>  
  
### <a name="searching-for-metadata-nodes"></a><span data-ttu-id="e5d2b-157">搜索元数据节点</span><span class="sxs-lookup"><span data-stu-id="e5d2b-157">Searching for Metadata Nodes</span></span>  
 <span data-ttu-id="e5d2b-158">你使用**搜索**方法来执行搜索包含父节点的节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-158">You use the **Search** method to perform a search for nodes contained by a parent node.</span></span> <span data-ttu-id="e5d2b-159">你可以指定星号 (\*) 通配符。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-159">You can specify the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="e5d2b-160">此字符匹配零个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-160">This character matches zero or more characters.</span></span> <span data-ttu-id="e5d2b-161">下面的示例演示搜索包含字符串"BAPI"的所有 Rfc。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-161">The following example shows a search for all RFCs that contain the string "BAPI".</span></span> <span data-ttu-id="e5d2b-162">在此示例中，**客户端**是的一个实例**MetadataRetrievalClient**。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-162">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Search for all nodes that contain "BAPI" under the RFC node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI*", int.MaxValue);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="e5d2b-163">仅支持有限的一组节点上进行搜索。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-163">Searching is only supported on a limited set of nodes.</span></span> <span data-ttu-id="e5d2b-164">有关在其支持搜索的节点以及在搜索表达式中支持的通配符字符的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-164">For more information about the nodes on which search is supported and about the wildcard character supported in search expressions, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md).</span></span>  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a><span data-ttu-id="e5d2b-165">检索操作的元数据 (WSDL)</span><span class="sxs-lookup"><span data-stu-id="e5d2b-165">Retrieving Metadata (WSDL) for Operations</span></span>  
 <span data-ttu-id="e5d2b-166">你使用**GetMetadata**方法来检索服务说明 （WSDL 文档） 的一组的操作节点。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-166">You use the **GetMetadata** method to retrieve a service description (WSDL document) for a group of operation nodes.</span></span> <span data-ttu-id="e5d2b-167">下面的示例检索 BAPI_TRANSACTION_COMMIT RFC 服务说明。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-167">The following example retrieves a service description for the BAPI_TRANSACTION_COMMIT RFC.</span></span> <span data-ttu-id="e5d2b-168">在此示例中，**客户端**是的一个实例**MetadataRetrievalClient**。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-168">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span> <span data-ttu-id="e5d2b-169">请注意，等效于该操作的消息操作的操作节点的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-169">Note that the node ID for an operation node is equivalent to the message action for that operation.</span></span>  
  
```  
// Get a WSDL document that specifies a contract that contains the  
// BAPI_TRANSACTION_COMMIT operation.  
MetadataRetrievalNode[] nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
nodes[0].IsOperation = true;  
  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="e5d2b-170">只应指定操作中的节点**GetMetadata**方法。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-170">You should only specify operation nodes in the **GetMetadata** method.</span></span>  
  
### <a name="using-a-metadataretrievalclient"></a><span data-ttu-id="e5d2b-171">使用 MetadataRetrievalClient</span><span class="sxs-lookup"><span data-stu-id="e5d2b-171">Using a MetadataRetrievalClient</span></span>  
 <span data-ttu-id="e5d2b-172">创建和使用**MetadataRetrievalClient**是任何其他 WCF 客户端，大致相同。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-172">Creating and using a **MetadataRetrievalClient** is much the same as any other WCF client.</span></span> <span data-ttu-id="e5d2b-173">通过指定终结点和的实例来创建客户端**SAPBinding**。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-173">You create the client by specifying an endpoint and an instance of **SAPBinding**.</span></span> <span data-ttu-id="e5d2b-174">可以以声明方式在配置中或在代码中以强制方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-174">You can do this either declaratively in configuration or imperatively in your code.</span></span> <span data-ttu-id="e5d2b-175">然后，可以调用的方法**MetadataRetrievalClient**若要浏览，搜索，并从适配器中检索元数据。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-175">You then invoke the methods of the **MetadataRetrievalClient** to browse, search, and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="e5d2b-176">下面的示例演示如何使用**MetadataRetrievalClient**若要浏览，搜索和检索元数据从[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-176">The following example shows how to use a **MetadataRetrievalClient** to browse, search, and retrieve metadata from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace SapMetaDataBrowseClient  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console.  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //Write all the nodes returned to the console.  
            foreach (MetadataRetrievalNode node in nodes)  
            {  
                Console.WriteLine("NodeId = " + node.NodeId);  
                Console.WriteLine("\tDirection   = " + node.Direction.ToString());  
                Console.WriteLine("\tIsOperation = " + node.IsOperation.ToString());  
                Console.WriteLine("\tDisplayName = " + node.DisplayName);  
                Console.WriteLine("\tDescription = " + node.Description);  
            }  
            Console.WriteLine();  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            MetadataRetrievalClient browser = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // Create a binding  
                SAPBinding binding = new SAPBinding();  
  
                EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
                browser = new MetadataRetrievalClient(binding, address);  
                browser.ClientCredentials.UserName.UserName = "YourUserName";  
                browser.ClientCredentials.UserName.Password = "YourPassword";  
                browser.Open();  
  
                // Return the nodes directly under the root.  
                // The parameters are the parent node ID, the start index, and the maximum number  
                // of nodes to return.  
                MetadataRetrievalNode[] nodes = browser.Browse(MetadataRetrievalNode.Root.NodeId, 0, int.MaxValue);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Return first 3 RFC group nodes.  
                nodes = browser.Browse(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, 0, 3);  
                nodeWriter.Write(String.Format("Browse results for the first {1} nodes of {0}:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, nodes.Length), nodes);  
  
                // Search for first 3 nodes that begin with "BAPI_TRANSACTION" under the RFC node.  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return.  
                nodes = browser.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "*BAPI_TRANSACTION*", 3);  
                nodeWriter.Write(String.Format("Search results for \"*BAPI_TRANSACTION*\" under {0} node:", Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // found in the search and write it to a file.  
                // You could explicitly specify operations as in the following:  
                //    nodes[0] = new MetadataRetrievalNode();  
                //    nodes[0].NodeId = Microsoft.Adapters.SAP.SAPAdapterConstants.ActionConstants.RfcActionPrefix + "BAPI_TRANSACTION_COMMIT";  
                //    nodes[0].IsOperation = true;  
                // Note that the operation NodeId is equivalent to the message action.  
                System.Web.Services.Description.ServiceDescription description = browser.GetMetadata(nodes);  
                description.Write("SampleContract.wsdl");  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (browser != null)  
                {  
                    if (browser.State == CommunicationState.Opened)  
                        browser.Close();  
                    else  
                        browser.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="e5d2b-177">以下在控制台上显示此程序的输出。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-177">The following shows the output of this program on the console.</span></span> <span data-ttu-id="e5d2b-178">你可以看到每个方法返回的元数据检索节点的结构。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-178">You can see the structure of the metadata retrieval nodes returned for each method.</span></span> <span data-ttu-id="e5d2b-179">该程序还将写入描述包含文件由搜索返回的节点的服务协定以 WSDL 文档。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-179">The program also writes a WSDL document that describes a service contract consisting of the nodes returned by the search to a file.</span></span> <span data-ttu-id="e5d2b-180">（对于大多数的 SAP 安装服务说明将包含在 BAPI_TRANSACTION_COMMIT 和 BAPI_TRANSACTION_ROLLBACK 操作。）</span><span class="sxs-lookup"><span data-stu-id="e5d2b-180">(For most SAP installations, the service description will contain the BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK operations.)</span></span>  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/BAPISECTION/000001  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = BAPI  
        Description = BAPI  
NodeId = http://Microsoft.LobServices.Sap/2007/03/IDOCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = IDOC  
        Description = IDOC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = RFC  
        Description = RFC  
NodeId = http://Microsoft.LobServices.Sap/2007/03/TRFCSECTION/  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = TRFC  
        Description = TRFC  
  
Browse results for the first 3 nodes of http://Microsoft.LobServices.Sap/2007/03  
/RFCSECTION/:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/A  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Asset Accounting  
        Description = Asset Accounting  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/S  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Basis  
        Description = Basis  
NodeId = http://Microsoft.LobServices.Sap/2007/03/RFCGROUP/B  
        Direction   = Inbound, Outbound  
        IsOperation = False  
        DisplayName = Business Information Warehouse  
        Description = Business Information Warehouse  
  
Search results for "*BAPI_TRANSACTION*" under http://Microsoft.LobServices.Sap/2  
007/03/RFCSECTION/ node:  
  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_COMMIT  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_COMMIT  
        Description = Execute external Commit when using BAPIs  
NodeId = http://Microsoft.LobServices.Sap/2007/03/Rfc/BAPI_TRANSACTION_ROLLBACK  
        Direction   = Inbound, Outbound  
        IsOperation = True  
        DisplayName = BAPI_TRANSACTION_ROLLBACK  
        Description = Execute external Rollback when using BAPIs  
  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a><span data-ttu-id="e5d2b-181">使用 IMetadataRetrievalContract 通道</span><span class="sxs-lookup"><span data-stu-id="e5d2b-181">Using an IMetadataRetrievalContract Channel</span></span>  
 <span data-ttu-id="e5d2b-182">你还可以创建**IMetadataRetrievalContract**通道，然后使用此通道浏览、 搜索和检索元数据的适配器。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-182">You can also create an **IMetadataRetrievalContract** channel and then use this channel to browse, search, and retrieve metadata from the adapter.</span></span> <span data-ttu-id="e5d2b-183">(方法签名为相同**MetadataRetrievalClient**类。)下面的示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e5d2b-183">(The method signatures are the same as for the **MetadataRetrievalClient** class.) The following example shows how to do this.</span></span>  
  
```  
…  
//Create a binding and endpoint address.  
SAPBinding binding = new SAPBinding();  
EndpointAddress address = new EndpointAddress("sap://Client=800;lang=EN@A/YourSAPHost/00");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "YourUserName";  
factory.Credentials.UserName.Password = "YourPassword";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search(Microsoft.Adapters.SAP.SAPAdapterConstants.MetadataConstants.RfcSection, "BAPI_TRANSACTION*", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5d2b-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5d2b-184">See Also</span></span>  
 [<span data-ttu-id="e5d2b-185">从 SAP 以编程方式检索元数据</span><span class="sxs-lookup"><span data-stu-id="e5d2b-185">Retrieving Metadata Programmatically from SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-programmatically-from-sap.md)