---
title: 使用 IMetadataRetrievalContract 的 Oracle 数据库中获取元数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving using IMetadataRetrievalContract
ms.assetid: 7d32694f-4384-4c2f-be72-ac52c7b2e9f5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 132ad3f64d377a3bfcbf7b1b2303e1c0de0c612f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218197"
---
# <a name="get-metadata-in-oracle-database-using-imetadataretrievalcontract"></a><span data-ttu-id="f7153-102">使用 IMetadataRetrievalContract 的 Oracle 数据库中获取元数据</span><span class="sxs-lookup"><span data-stu-id="f7153-102">Get Metadata in Oracle Database Using IMetadataRetrievalContract</span></span>
<span data-ttu-id="f7153-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开**IMetadataRetrievalContract**可用来浏览和搜索 Oracle 数据库项目，并以检索窗体的 Web 服务描述语言 (WSDL 中的操作的元数据的终结点) 文档。</span><span class="sxs-lookup"><span data-stu-id="f7153-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes an **IMetadataRetrievalContract**endpoint that you can use to browse and search for Oracle database artifacts and to retrieve metadata for operations in the form of a Web Services Description Language (WSDL) document.</span></span>  
  
 <span data-ttu-id="f7153-104">**IMetadataRetrievalContract**接口由实现[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]和浏览、 搜索和检索功能可提供元数据。</span><span class="sxs-lookup"><span data-stu-id="f7153-104">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and provides metadata browse, search, and retrieval capabilities.</span></span> <span data-ttu-id="f7153-105">除了**IMetadataRetrievalContract**接口，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]公开**MetadataRetrievalClient**类，该类实现接口。</span><span class="sxs-lookup"><span data-stu-id="f7153-105">In addition to the **IMetadataRetrievalContract** interface, the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] exposes the **MetadataRetrievalClient** class, which implements the interface.</span></span> <span data-ttu-id="f7153-106">你可以使用**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**要使用元数据; 公开给浏览、 搜索和检索元数据的方法是在每个用例中相同。</span><span class="sxs-lookup"><span data-stu-id="f7153-106">You can use either an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with metadata; the methods exposed to browse, search, and retrieve metadata are the same in each case.</span></span>  
  
 <span data-ttu-id="f7153-107">以下各节提供有关如何使用信息**IMetadataRetrievalContract**接口。</span><span class="sxs-lookup"><span data-stu-id="f7153-107">The following sections provide information about how to use the **IMetadataRetrievalContract** interface.</span></span>  
  
## <a name="the-imetadataretrievalcontract-interface"></a><span data-ttu-id="f7153-108">IMetadataRetrievalContract 接口</span><span class="sxs-lookup"><span data-stu-id="f7153-108">The IMetadataRetrievalContract Interface</span></span>  
 <span data-ttu-id="f7153-109">下表提供了有关在处理时使用的重要类的信息**IMetadataRetrievalContract**接口。</span><span class="sxs-lookup"><span data-stu-id="f7153-109">The following table provides information about important classes that are used when you work with the **IMetadataRetrievalContract** interface.</span></span>  
  
|<span data-ttu-id="f7153-110">类或接口</span><span class="sxs-lookup"><span data-stu-id="f7153-110">Class or Interface</span></span>|<span data-ttu-id="f7153-111">Description</span><span class="sxs-lookup"><span data-stu-id="f7153-111">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="f7153-112">**IMetadataRetrievalContract**接口</span><span class="sxs-lookup"><span data-stu-id="f7153-112">**IMetadataRetrievalContract** interface</span></span><br /><br /> <span data-ttu-id="f7153-113">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="f7153-113">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="f7153-114">定义**浏览**，**搜索**，和**GetMetadata**方法。</span><span class="sxs-lookup"><span data-stu-id="f7153-114">Defines the **Browse**, **Search**, and **GetMetadata** methods.</span></span> <span data-ttu-id="f7153-115">你可以通过调用这些方法**IMetadataRetrievalContract**通道或**MetadataRetrievalClient**用于适配器元数据。</span><span class="sxs-lookup"><span data-stu-id="f7153-115">You invoke these methods either by using an **IMetadataRetrievalContract** channel or a **MetadataRetrievalClient** to work with adapter metadata.</span></span>|  
|<span data-ttu-id="f7153-116">**MetadataRetrievalClient**类</span><span class="sxs-lookup"><span data-stu-id="f7153-116">**MetadataRetrievalClient** class</span></span><br /><br /> <span data-ttu-id="f7153-117">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="f7153-117">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="f7153-118">实现**IMetadataRetrievalContract**接口。</span><span class="sxs-lookup"><span data-stu-id="f7153-118">Implements the **IMetadataRetrievalContract** interface.</span></span> <span data-ttu-id="f7153-119">你可以创建此类的实例并将其用于 Oracle 数据库配置通过提供**OracleDBBinding**和**EndpointAddress**。</span><span class="sxs-lookup"><span data-stu-id="f7153-119">You can create an instance of this class and configure it for your Oracle database by providing an **OracleDBBinding** and an **EndpointAddress**.</span></span> <span data-ttu-id="f7153-120">然后，你可以调用其方法来处理元数据。</span><span class="sxs-lookup"><span data-stu-id="f7153-120">Then you can invoke its methods to work with metadata.</span></span>|  
|<span data-ttu-id="f7153-121">**MetadataRetrievalNode**类</span><span class="sxs-lookup"><span data-stu-id="f7153-121">**MetadataRetrievalNode** class</span></span><br /><br /> <span data-ttu-id="f7153-122">(Microsoft.ServiceModel.Channels)</span><span class="sxs-lookup"><span data-stu-id="f7153-122">(Microsoft.ServiceModel.Channels)</span></span>|<span data-ttu-id="f7153-123">表示在适配器上的元数据节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-123">Represents a metadata node on the adapter.</span></span> <span data-ttu-id="f7153-124">**浏览**和**搜索**方法返回此类型的节点和**GetMetadata**方法采用这种类型作为参数的节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-124">The **Browse** and **Search** methods return nodes of this type, and the **GetMetadata** method takes nodes of this type as a parameter.</span></span>|  
|<span data-ttu-id="f7153-125">**ServiceDescription**类</span><span class="sxs-lookup"><span data-stu-id="f7153-125">**ServiceDescription** class</span></span><br /><br /> <span data-ttu-id="f7153-126">(System.Web.Services.Description)</span><span class="sxs-lookup"><span data-stu-id="f7153-126">(System.Web.Services.Description)</span></span>|<span data-ttu-id="f7153-127">提供一种创建和格式设置有效的 WSDL 文档文件。</span><span class="sxs-lookup"><span data-stu-id="f7153-127">Provides a means of creating and formatting a valid WSDL document file.</span></span> <span data-ttu-id="f7153-128">**GetMetadata**方法返回**ServiceDescription**对象。</span><span class="sxs-lookup"><span data-stu-id="f7153-128">The **GetMetadata** method returns a **ServiceDescription** object.</span></span>|  
  
 
### <a name="metadata-node-ids"></a><span data-ttu-id="f7153-129">元数据节点 Id</span><span class="sxs-lookup"><span data-stu-id="f7153-129">Metadata Node IDs</span></span>  
 <span data-ttu-id="f7153-130">适配器将其元数据组织为节点的分层树。</span><span class="sxs-lookup"><span data-stu-id="f7153-130">The adapter organizes its metadata as a hierarchical tree of nodes.</span></span> <span data-ttu-id="f7153-131">在此树状结构中有两种类型的元数据节点：</span><span class="sxs-lookup"><span data-stu-id="f7153-131">Within this tree structure there are two types of metadata nodes:</span></span>  
  
-   <span data-ttu-id="f7153-132">**操作节点**表示适配器呈现在 Oracle 数据库项目的操作。</span><span class="sxs-lookup"><span data-stu-id="f7153-132">**Operation nodes** represent operations that the adapter surfaces on Oracle database artifacts.</span></span> <span data-ttu-id="f7153-133">操作的节点的树的叶。</span><span class="sxs-lookup"><span data-stu-id="f7153-133">Operation nodes are the leaves of the tree.</span></span>  
  
-   <span data-ttu-id="f7153-134">**类别节点**表示 Oracle 数据库项目并不直接对应的 Oracle 数据库项目的分组在适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="f7153-134">**Category nodes** represent Oracle database artifacts and groupings of Oracle database artifacts that do not directly correspond to an operation on the adapter.</span></span> <span data-ttu-id="f7153-135">类别节点是树的分支它们包含其他类别节点和/或操作节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-135">Category nodes are the branches of the tree; they contain other category nodes and/or operation nodes.</span></span> <span data-ttu-id="f7153-136">例如，Oracle 表和包都表示为类别节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-136">For example, Oracle tables and packages are represented as category nodes.</span></span>  
  
 <span data-ttu-id="f7153-137">每个适配器中加以表示的元数据节点标识的唯一节点 id。</span><span class="sxs-lookup"><span data-stu-id="f7153-137">Each metadata node surfaced by the adapter is identified by a unique node ID.</span></span> <span data-ttu-id="f7153-138">有关元数据节点 Id 显示适配器的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。</span><span class="sxs-lookup"><span data-stu-id="f7153-138">For more information about the metadata node IDs surfaced by the adapter, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span> <span data-ttu-id="f7153-139">这些节点 Id 用于指定目标 Oracle 数据库项目，当你使用时**IMetadataRetrievalContract**接口来浏览、 搜索和检索元数据。</span><span class="sxs-lookup"><span data-stu-id="f7153-139">You use these node IDs to specify target Oracle database artifacts when you use the **IMetadataRetrievalContract** interface to browse, search, and retrieve metadata.</span></span>  
  
### <a name="binding-properties"></a><span data-ttu-id="f7153-140">绑定属性</span><span class="sxs-lookup"><span data-stu-id="f7153-140">Binding Properties</span></span>  
 <span data-ttu-id="f7153-141">是否使用**IMetadataRetrievalContract**通道或**IMetadataRetrievalClient**若要使用元数据，必须指定**OracleDBBinding**时你创建实例。</span><span class="sxs-lookup"><span data-stu-id="f7153-141">Whether you use an **IMetadataRetrievalContract** channel or an **IMetadataRetrievalClient** to work with metadata, you must specify an **OracleDBBinding** when you create the instance.</span></span>  
  
 <span data-ttu-id="f7153-142">有几个绑定属性影响如何适配器生成元数据。</span><span class="sxs-lookup"><span data-stu-id="f7153-142">There are several binding properties that affect how the adapter generates metadata.</span></span> <span data-ttu-id="f7153-143">这些属性包括：</span><span class="sxs-lookup"><span data-stu-id="f7153-143">These properties are:</span></span>  
  
-   <span data-ttu-id="f7153-144">**EnableSafeTyping**</span><span class="sxs-lookup"><span data-stu-id="f7153-144">**EnableSafeTyping**</span></span>  
  
-   <span data-ttu-id="f7153-145">**UseSchemaInNamespace**</span><span class="sxs-lookup"><span data-stu-id="f7153-145">**UseSchemaInNamespace**</span></span>  
  
-   <span data-ttu-id="f7153-146">**PollingStatement**</span><span class="sxs-lookup"><span data-stu-id="f7153-146">**PollingStatement**</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7153-147">如果你想要检索 POLLINGSTMT 操作元数据必须设置**PollingStatement**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="f7153-147">If you want to retrieve metadata for the POLLINGSTMT operation you must set the **PollingStatement** binding property.</span></span>  
  
 <span data-ttu-id="f7153-148">你应确保这些绑定属性都设置为在打开元数据检索对象之前，你的应用程序所需的值。</span><span class="sxs-lookup"><span data-stu-id="f7153-148">You should ensure that these binding properties are set to the values required for your application before you open the metadata retrieval object.</span></span> <span data-ttu-id="f7153-149">有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，请参阅[阅读有关 Oracle 数据库适配器绑定属性](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f7153-149">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  
  
### <a name="browsing-metadata-nodes"></a><span data-ttu-id="f7153-150">浏览元数据节点</span><span class="sxs-lookup"><span data-stu-id="f7153-150">Browsing Metadata Nodes</span></span>  
 <span data-ttu-id="f7153-151">你使用**浏览**方法以返回中的父节点包含的所有元数据节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-151">You use the **Browse** method to return all the metadata nodes that are contained in a parent node.</span></span> <span data-ttu-id="f7153-152">下面的示例浏览对 Oracle 数据库的前三个架构。</span><span class="sxs-lookup"><span data-stu-id="f7153-152">The following example browses for the first three schemas on the Oracle database.</span></span> <span data-ttu-id="f7153-153">在此示例中，**客户端**是的一个实例**MetadataRetrievalClient**。</span><span class="sxs-lookup"><span data-stu-id="f7153-153">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// The first parameter is the node ID.   
// The second parameter is the start index.  
// The third parameter is the maximum number of nodes to return.  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7153-154">只能浏览类别节点，则您无法浏览操作节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-154">You can only browse category nodes; you cannot browse operation nodes.</span></span>  
  
### <a name="searching-for-metadata-nodes"></a><span data-ttu-id="f7153-155">搜索元数据节点</span><span class="sxs-lookup"><span data-stu-id="f7153-155">Searching for Metadata Nodes</span></span>  
 <span data-ttu-id="f7153-156">你使用**搜索**方法来执行搜索包含父节点的节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-156">You use the **Search** method to perform a search for nodes contained by a parent node.</span></span> <span data-ttu-id="f7153-157">适配器支持通配符搜索表达式; 中例如，你可以指定在百分号 （%） 通配符来匹配零个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="f7153-157">The adapter supports wildcard characters in search expressions; for example you can specify the percent (%) wildcard character to match zero or more characters.</span></span> <span data-ttu-id="f7153-158">下面的示例演示 SCOTT 架构中包含字符串"EMP"搜索所有表。</span><span class="sxs-lookup"><span data-stu-id="f7153-158">The following example shows a search for all the tables in the SCOTT schema that contain the string "EMP".</span></span> <span data-ttu-id="f7153-159">在此示例中，**客户端**是的一个实例**MetadataRetrievalClient**。</span><span class="sxs-lookup"><span data-stu-id="f7153-159">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Search for all nodes that contain "EMP" under the SCOTT.Table node.  
// The parameters are the parent node ID, the search expression, and   
// the maximum number of nodes to return.  
IMetadataRetrievalNode[] nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7153-160">仅支持有限的一组节点上进行搜索。</span><span class="sxs-lookup"><span data-stu-id="f7153-160">Searching is only supported on a limited set of nodes.</span></span> <span data-ttu-id="f7153-161">有关在其支持搜索的节点以及在搜索表达式中支持的通配符字符的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。</span><span class="sxs-lookup"><span data-stu-id="f7153-161">For more information about the nodes on which search is supported and about the wildcard characters supported in search expressions, see [Metadata Node IDs](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md).</span></span>  
  
### <a name="retrieving-metadata-wsdl-for-operations"></a><span data-ttu-id="f7153-162">检索操作的元数据 (WSDL)</span><span class="sxs-lookup"><span data-stu-id="f7153-162">Retrieving Metadata (WSDL) for Operations</span></span>  
 <span data-ttu-id="f7153-163">你使用**GetMetadata**方法来检索服务说明 （WSDL 文档） 的一组的操作节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-163">You use the **GetMetadata** method to retrieve a service description (WSDL document) for a group of operation nodes.</span></span> <span data-ttu-id="f7153-164">下面的示例检索包含所有适配器显示为 SCOTT 的操作的服务说明。EMP 表通过指定其节点 id。</span><span class="sxs-lookup"><span data-stu-id="f7153-164">The following example retrieves a service description that contains all of the operations that the adapter surfaces for the SCOTT.EMP table by specifying its node ID.</span></span> <span data-ttu-id="f7153-165">在此示例中，**客户端**是的一个实例**MetadataRetrievalClient**。</span><span class="sxs-lookup"><span data-stu-id="f7153-165">In this example, **client** is an instance of **MetadataRetrievalClient**.</span></span>  
  
```  
// Get a service description that contains all of the operations   
// surfaced for the SCOTT.EMP table. The IsOperation  
// property is set false because this is a category node.  
nodes = new MetadataRetrievalNode[1];  
nodes[0] = new MetadataRetrievalNode();  
nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
nodes[0].IsOperation = false;  
System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7153-166">**IsOperation**属性应为 false 的类别节点和操作节点的 true。</span><span class="sxs-lookup"><span data-stu-id="f7153-166">The **IsOperation** property should be false for category nodes and true for operation nodes.</span></span>  
  
### <a name="using-a-metadataretrievalclient"></a><span data-ttu-id="f7153-167">使用 MetadataRetrievalClient</span><span class="sxs-lookup"><span data-stu-id="f7153-167">Using a MetadataRetrievalClient</span></span>  
 <span data-ttu-id="f7153-168">创建和使用**MetadataRetrievalClient**是任何其他 WCF 客户端，大致相同。</span><span class="sxs-lookup"><span data-stu-id="f7153-168">Creating and using a **MetadataRetrievalClient** is much the same as any other WCF client.</span></span> <span data-ttu-id="f7153-169">通过指定终结点和的实例来创建客户端**OracleDBBinding**。</span><span class="sxs-lookup"><span data-stu-id="f7153-169">You create the client by specifying an endpoint and an instance of **OracleDBBinding**.</span></span> <span data-ttu-id="f7153-170">可以以声明方式在配置中或在代码中以强制方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f7153-170">You can do this either declaratively in configuration or imperatively in your code.</span></span> <span data-ttu-id="f7153-171">然后，可以调用的方法**MetadataRetrievalClient**若要浏览，搜索，并从适配器中检索元数据。</span><span class="sxs-lookup"><span data-stu-id="f7153-171">You then invoke the methods of the **MetadataRetrievalClient** to browse, search, and retrieve metadata from the adapter.</span></span>  
  
 <span data-ttu-id="f7153-172">下面的示例演示如何使用**MetadataRetrievalClient**若要浏览，搜索和检索元数据从[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f7153-172">The following example shows how to use a **MetadataRetrievalClient** to browse, search, and retrieve metadata from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="f7153-173">此示例演示：</span><span class="sxs-lookup"><span data-stu-id="f7153-173">The example demonstrates:</span></span>  
  
-   <span data-ttu-id="f7153-174">浏览 Oracle 数据库架构的元数据树的根节点。</span><span class="sxs-lookup"><span data-stu-id="f7153-174">Browsing the root node of the metadata tree for Oracle Database schemas.</span></span>  
  
-   <span data-ttu-id="f7153-175">搜索名称中包含字符串"EMP"SCOTT 架构中的表。</span><span class="sxs-lookup"><span data-stu-id="f7153-175">Searching for the tables in the SCOTT schema with names that contain the string "EMP".</span></span>  
  
-   <span data-ttu-id="f7153-176">检索所有为 SCOTT 支持的操作的元数据。通过将传递到类别节点的 EMP 表**GetMetadata**方法。</span><span class="sxs-lookup"><span data-stu-id="f7153-176">Retrieving metadata for all of the operations supported for the SCOTT.EMP table by passing a category node to the **GetMetadata** method.</span></span>  
  
-   <span data-ttu-id="f7153-177">通过将传递到 POLLINGSTMT 操作节点检索 POLLINGSTMT 操作元数据**GetMetadata**方法...</span><span class="sxs-lookup"><span data-stu-id="f7153-177">Retrieving metadata for the POLLINGSTMT operation by passing the POLLINGSTMT operation node to the **GetMetadata** method..</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
using System.ServiceModel;  
using Microsoft.Adapters.OracleDB;  
using Microsoft.ServiceModel.Channels;  
  
using System.Web.Services.Description;  
  
namespace OracleMetadataRetrieval  
{  
    class NodeWriter  
    {  
        // This method writes the value of a collection of metadata retrieval nodes  
        // to the console  
        public void Write(string title, MetadataRetrievalNode[] nodes)  
        {  
            Console.WriteLine(title);  
            Console.WriteLine();  
  
            //write all the nodes returned to the console.  
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
            MetadataRetrievalClient client = null;  
            NodeWriter nodeWriter = new NodeWriter();  
  
            try  
            {  
                // create a binding and   
                // set the PollingStatement binding property if you want to  
                // return metadata for the POLLINGSTMT operation  
                OracleDBBinding binding = new OracleDBBinding();  
                binding.PollingStatement = "SELECT * FROM EMP";  
  
                // Set PollingId parameter if you want to alter the namespace of the POLLINGSTMT operation  
                EndpointAddress address = new EndpointAddress("oracledb://ADAPTER?PollingId=1");  
  
                client = new MetadataRetrievalClient(binding, address);  
                client.ClientCredentials.UserName.UserName = "SCOTT";  
                client.ClientCredentials.UserName.Password = "TIGER";  
                client.Open();  
  
                // Browse for the first 3 (schema) nodes directly under the root  
                // The parameters are the parent Node ID, the start index, and the maximum number  
                // of nodes to return  
                MetadataRetrievalNode[] nodes = client.Browse(MetadataRetrievalNode.Root.NodeId, 0, 3);  
                nodeWriter.Write("Browse results for the root node:", nodes);  
  
                // Search for first 3 tables that contain "EMP" in the SCOTT schema  
                // The parameters are the parent node ID, the search expression, and the maximum number  
                // of nodes to return  
                nodes = client.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", 3);  
                nodeWriter.Write(String.Format("Search results for \"%EMP%\" under {0} node:", "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table"), nodes);  
  
                // Get a WSDL document that specifies a contract that contains the operations  
                // surfaced for the SCOTT.EMP table. The IsOperation property is set false  
                // because this is a category node.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP";  
                nodes[0].IsOperation = false;  
                System.Web.Services.Description.ServiceDescription description = client.GetMetadata(nodes);  
                description.Write("EmpTableContract.wsdl");  
  
                // Get a WSDL document that specifies a contract that contains the   
                // the POLLINGSTMT operation. The IsOperation property is set true  
                // because this is an operation node.  
                // Note that the operation NodeId is equivalent to the message action.  
                nodes = new MetadataRetrievalNode[1];  
                nodes[0] = new MetadataRetrievalNode();  
                nodes[0].NodeId = "http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT";  
                nodes[0].IsOperation = true;  
                description = client.GetMetadata(nodes);  
                description.Write("PollingContract.wsdl");  
  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
            }  
            finally  
            {  
                if (client != null)  
                {  
                    if (client.State == CommunicationState.Opened)  
                        client.Close();  
                    else  
                        client.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="f7153-178">以下在控制台上显示此程序的输出。</span><span class="sxs-lookup"><span data-stu-id="f7153-178">The following shows the output of this program on the console.</span></span> <span data-ttu-id="f7153-179">你可以看到每个方法返回的元数据检索节点的结构。</span><span class="sxs-lookup"><span data-stu-id="f7153-179">You can see the structure of the metadata retrieval nodes returned by each method.</span></span> <span data-ttu-id="f7153-180">该程序还将两个 WSDL 文档写入到文件中。</span><span class="sxs-lookup"><span data-stu-id="f7153-180">The program also writes two WSDL documents to files.</span></span>  
  
```  
Browse results for the root node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTERTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTERTEST  
        Description = Owned By ADAPTERTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADAPTEST  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADAPTEST  
        Description = Owned By ADAPTEST  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/ADMIN123  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = ADMIN123  
        Description = Owned By ADMIN123  
  
Search results for "%EMP%" under http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table node:  
  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/AEMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = AEMP  
        Description = Table.AEMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP  
        Description = Table.EMP  
NodeId = http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP1  
        Direction   = Outbound  
        IsOperation = False  
        DisplayName = EMP1  
        Description = Table.EMP1  
```  
  
## <a name="using-an-imetadataretrievalcontract-channel"></a><span data-ttu-id="f7153-181">使用 IMetadataRetrievalContract 通道</span><span class="sxs-lookup"><span data-stu-id="f7153-181">Using an IMetadataRetrievalContract Channel</span></span>  
 <span data-ttu-id="f7153-182">你还可以创建**IMetadataRetrievalContract**通道，然后使用此通道浏览、 搜索和检索元数据的适配器。</span><span class="sxs-lookup"><span data-stu-id="f7153-182">You can also create an **IMetadataRetrievalContract** channel and then use this channel to browse, search, and retrieve metadata from the adapter.</span></span> <span data-ttu-id="f7153-183">(方法签名为相同**MetadataRetrievalClient**类。)下面的示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f7153-183">(The method signatures are the same as for the **MetadataRetrievalClient** class.) The following example shows how to do this.</span></span>  
  
```  
…  
//Create a binding and endpoint address.  
OracleDBBinding binding = new OracleDBBinding();  
EndpointAddress address = new EndpointAddress("oracledb://ADAPTER/");  
  
//Create and open a channel factory that will return an IMetadataRetrievalContract object, on which browse, search, and get can be performed.  
ChannelFactory<IMetadataRetrievalContract> factory = new ChannelFactory<IMetadataRetrievalContract>(binding, address);  
factory.Credentials.UserName.UserName = "SCOTT";  
factory.Credentials.UserName.Password = "TIGER";  
factory.Open();  
  
//Obtain an IMetadataRetrievalContract channel from the factory.  
IMetadataRetrievalContract channel = factory.CreateChannel();  
  
//Perform a search using the channel.  
MetadataRetrievalNode[] nodes = channel.Search("http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table", "%EMP%", int.MaxValue);  
…  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7153-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7153-184">See Also</span></span>  
 [<span data-ttu-id="f7153-185">从 Oracle 数据库以编程方式获取元数据</span><span class="sxs-lookup"><span data-stu-id="f7153-185">Get Metadata Programmatically from the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-programmatically-from-the-oracle-database.md)