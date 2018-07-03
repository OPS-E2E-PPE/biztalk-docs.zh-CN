---
title: 步骤 4： 实现 Echo 适配器的元数据浏览处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d31fc6c1-e4b5-4529-ba3e-2a8cfb8ece1c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c50110fff32b81bdaa429a479cefe8041d919356
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003414"
---
# <a name="step-4-implement-the-metadata-browse-handler-for-the-echo-adapter"></a><span data-ttu-id="be739-102">步骤 4： 实现 Echo 适配器的元数据浏览处理程序</span><span class="sxs-lookup"><span data-stu-id="be739-102">Step 4: Implement the Metadata Browse Handler for the Echo Adapter</span></span>
<span data-ttu-id="be739-103">![步骤 4 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span><span class="sxs-lookup"><span data-stu-id="be739-103">![Step 4 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span></span>  
  
 <span data-ttu-id="be739-104">**完成时间：** 45 分钟</span><span class="sxs-lookup"><span data-stu-id="be739-104">**Time to complete:** 45 minutes</span></span>  
  
 <span data-ttu-id="be739-105">在此步骤中，将实现 Echo 适配器的浏览功能。</span><span class="sxs-lookup"><span data-stu-id="be739-105">In this step, you implement the browse capability of the Echo adapter.</span></span> <span data-ttu-id="be739-106">此功能允许您的适配器来执行基于连接的浏览，从目标系统中获取元数据。</span><span class="sxs-lookup"><span data-stu-id="be739-106">This capability allows your adapter to perform a connection-based browse to obtain metadata from the target system.</span></span> <span data-ttu-id="be739-107">无论您的适配器的功能，您的适配器必须支持的浏览功能。</span><span class="sxs-lookup"><span data-stu-id="be739-107">Regardless of your adapter's capabilities, your adapter must support the browse capability.</span></span>  
  
 <span data-ttu-id="be739-108">根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，若要支持浏览功能，必须实现`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="be739-108">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support browse capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="be739-109">Echo 适配器[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成名为 EchoAdapterMetadataBrowseHandler 派生的类。</span><span class="sxs-lookup"><span data-stu-id="be739-109">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates the derived class called EchoAdapterMetadataBrowseHandler.</span></span>  
  
 <span data-ttu-id="be739-110">在以下步骤中，更新此类，以更好地理解如何实现`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法中，如何设置各种属性的`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象和操作和适配器支持的类别节点中的显示方式[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="be739-110">In the following steps, you update this class to get a better understanding of how to implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method, how to set various properties of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and how the operation and category nodes supported by the adapter appear in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be739-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="be739-111">Prerequisites</span></span>  
 <span data-ttu-id="be739-112">在开始此步骤之前，你必须已成功完成[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="be739-112">Before you begin this step, you must have successfully completed [Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md).</span></span> <span data-ttu-id="be739-113">您还必须了解以下类：</span><span class="sxs-lookup"><span data-stu-id="be739-113">You must also understand the following classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`  
  
## <a name="the-imetadatabrowsehandler-interface"></a><span data-ttu-id="be739-114">IMetadataBrowseHandler 接口</span><span class="sxs-lookup"><span data-stu-id="be739-114">The IMetadataBrowseHandler Interface</span></span>  
 <span data-ttu-id="be739-115">`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口如下定义：</span><span class="sxs-lookup"><span data-stu-id="be739-115">The `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface is defined as:</span></span>  
  
```  
public interface IMetadataBrowseHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Browse(string nodeId, int childStartIndex, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="be739-116">`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象根据方法的参数。</span><span class="sxs-lookup"><span data-stu-id="be739-116">The `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method returns an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects based on the method parameters.</span></span> <span data-ttu-id="be739-117">参数定义`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法以下表所述。</span><span class="sxs-lookup"><span data-stu-id="be739-117">The parameter definitions for the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method are described in the following table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be739-118">Echo 适配器实现使用仅限节点 ID，并忽略其他三个参数，因为 Echo 适配器支持仅在几个节点。</span><span class="sxs-lookup"><span data-stu-id="be739-118">The Echo adapter implementation uses only the node ID and ignores the other three parameters, since the Echo adapter supports only a few nodes.</span></span>  
  
|  <span data-ttu-id="be739-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="be739-119">**Parameter**</span></span>  |                                                                                                                                                                                                                               <span data-ttu-id="be739-120">**定义**</span><span class="sxs-lookup"><span data-stu-id="be739-120">**Definition**</span></span>                                                                                                                                                                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     <span data-ttu-id="be739-121">nodeId</span><span class="sxs-lookup"><span data-stu-id="be739-121">nodeId</span></span>      | <span data-ttu-id="be739-122">在层次结构中的元数据资源管理器的每个项 ([!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和</span><span class="sxs-lookup"><span data-stu-id="be739-122">Each item in the hierarchy of the metadata explorer (the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and</span></span><br /><br /> [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]<span data-ttu-id="be739-123">) 具有 nodeId。</span><span class="sxs-lookup"><span data-stu-id="be739-123">) has a nodeId.</span></span> <span data-ttu-id="be739-124">每个节点 ID 必须是唯一的并且可以是一个类别或操作。</span><span class="sxs-lookup"><span data-stu-id="be739-124">Each node ID must be unique and can be a category or an operation.</span></span> <span data-ttu-id="be739-125">类别具有子类别。</span><span class="sxs-lookup"><span data-stu-id="be739-125">The category can have subcategories.</span></span> <span data-ttu-id="be739-126">**注意：** 如果为 null 或空字符串 ("")，从根节点 （"/"） 默认情况下检索操作。</span><span class="sxs-lookup"><span data-stu-id="be739-126">**Note:**  If null or an empty string (""), operations are retrieved from the root node ("/") by default.</span></span> |
| <span data-ttu-id="be739-127">childStartIndex</span><span class="sxs-lookup"><span data-stu-id="be739-127">childStartIndex</span></span> |                                                                                                                                                                                           <span data-ttu-id="be739-128">要返回的第一个子级的索引。</span><span class="sxs-lookup"><span data-stu-id="be739-128">The index of the first child to return.</span></span><br /><br /> <span data-ttu-id="be739-129">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="be739-129">Not supported by the Echo adapter.</span></span>                                                                                                                                                                                            |
|  <span data-ttu-id="be739-130">maxChildNodes</span><span class="sxs-lookup"><span data-stu-id="be739-130">maxChildNodes</span></span>  |                                                                                                                                                                  <span data-ttu-id="be739-131">最大可返回的结果节点数。</span><span class="sxs-lookup"><span data-stu-id="be739-131">The maximum number of result nodes to return.</span></span> <span data-ttu-id="be739-132">使用 Int32.Max 检索所有结果节点。</span><span class="sxs-lookup"><span data-stu-id="be739-132">Use Int32.Max to retrieve all result nodes.</span></span><br /><br /> <span data-ttu-id="be739-133">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="be739-133">Not supported by the Echo adapter.</span></span>                                                                                                                                                                   |
|     <span data-ttu-id="be739-134">timeout</span><span class="sxs-lookup"><span data-stu-id="be739-134">timeout</span></span>     |                                                                                                                                                                                   <span data-ttu-id="be739-135">若要完成该操作允许的最大时间。</span><span class="sxs-lookup"><span data-stu-id="be739-135">The maximum time allowed for the operation to complete.</span></span><br /><br /> <span data-ttu-id="be739-136">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="be739-136">Not supported by the Echo adapter.</span></span>                                                                                                                                                                                    |
  
 <span data-ttu-id="be739-137">在实现时`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法，必须将类别和操作的每个节点添加到的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。</span><span class="sxs-lookup"><span data-stu-id="be739-137">When implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method, you must add every category and operation node to the array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="be739-138">若要指定一个节点作为类别，设置`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`到`false`。</span><span class="sxs-lookup"><span data-stu-id="be739-138">To specify a node as category, set the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` to `false`.</span></span> <span data-ttu-id="be739-139">若要指定一个节点作为操作，请设置`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A`到`true`。</span><span class="sxs-lookup"><span data-stu-id="be739-139">To specify a node as operation, set the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.IsOperation%2A` to `true`.</span></span>  
  
## <a name="echo-adapter-metadata-browse"></a><span data-ttu-id="be739-140">Echo 适配器的元数据浏览</span><span class="sxs-lookup"><span data-stu-id="be739-140">Echo Adapter Metadata Browse</span></span>  
 <span data-ttu-id="be739-141">根据目标系统的类别和操作，有许多种方法来生成一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。</span><span class="sxs-lookup"><span data-stu-id="be739-141">Depending on your target system's categories and operations, there are many ways to build an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="be739-142">操作和你选择的类别应表示你想要公开的操作。</span><span class="sxs-lookup"><span data-stu-id="be739-142">The operations and categories you choose should represent the operations you want to expose.</span></span> <span data-ttu-id="be739-143">但对于 Echo 适配器，它只不过是创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`列出对象为每个节点 id 的以下节点：</span><span class="sxs-lookup"><span data-stu-id="be739-143">But for the Echo adapter, it simply creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for each of the following nodes with node ID listed:</span></span>  
  
```  
EchoMainCategory  (node under the root node)  
        Echo/EchoStrings   (outbound operation)  
        Echo/EchoGreetings(outbound operation)  
        Echo/EchoCustomGreetingFromFile(outbound operation)  
        Echo/OnReceiveEcho (inbound operation)  
```  
  
 <span data-ttu-id="be739-144">EchoMainCategory 是根节点 （"/"） 下的类别节点。</span><span class="sxs-lookup"><span data-stu-id="be739-144">The EchoMainCategory is the category node under the root node ("/").</span></span> <span data-ttu-id="be739-145">此节点还作为类别用于入站和出站操作。</span><span class="sxs-lookup"><span data-stu-id="be739-145">This node is also used as the category for both inbound and outbound operations.</span></span> <span data-ttu-id="be739-146">因此，在创建时`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象为该类别中，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be739-146">Hence, when creating the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for that category, you can do the following:</span></span>  
  
```  
MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
node.IsOperation = false; //category  
node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound  //for both inbound and outbound  
```  
  
 <span data-ttu-id="be739-147">对于出站操作如属于 EchoMainCategory/Echo EchoString，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be739-147">For an outbound operation such as Echo/EchoString that belongs to the EchoMainCategory, you can do the following:</span></span>  
  
```  
if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
      {  
          // Outbound operations  
          MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
          outOpNode1.DisplayName = "EchoStrings";  
          outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
          outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
          outOpNode1.IsOperation = true;  
```  
  
 <span data-ttu-id="be739-148">对于入站操作如属于 EchoMainCategory/Echo OnReceiveEcho，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be739-148">For an inbound operation such as Echo/OnReceiveEcho that belongs to the EchoMainCategory, you can do the following:</span></span>  
  
```  
  if( "EchoMainCategory".CompareTo(nodeId) == 0 ) //category is EchoMainCategory  
        {             
// Inbound operations  
            MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
            inOpNode1.DisplayName = "OnReceiveEcho";  
            inOpNode1.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
            inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
            inOpNode1.IsOperation = true;  
```  
  
 <span data-ttu-id="be739-149">当[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具探索 Echo 适配器的元数据，默认情况下，它从根节点 （"/"） 开始。</span><span class="sxs-lookup"><span data-stu-id="be739-149">When the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools explore the Echo adapter metadata, by default, it starts from the root node ("/").</span></span>  
  
 <span data-ttu-id="be739-150">下图显示了 EchoMainCategory 节点显示在根节点 （"/"）：</span><span class="sxs-lookup"><span data-stu-id="be739-150">The following figure shows that the EchoMainCategory node appears under the root node ("/"):</span></span>  
  
 <span data-ttu-id="be739-151">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span><span class="sxs-lookup"><span data-stu-id="be739-151">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/e4b9d0b8-f07f-4342-815f-9ef1507b0980.gif "e4b9d0b8-f07f-4342-815f-9ef1507b0980")</span></span>  
  
 <span data-ttu-id="be739-152">若要浏览的三个出站操作，在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，在**选择协定类型**下拉列表中，选择**客户端 （出站操作）** 选项。</span><span class="sxs-lookup"><span data-stu-id="be739-152">To browse the three outbound operations, in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, in the **Select contract type** drop-down list,select the **Client (Outbound operations)** option.</span></span> <span data-ttu-id="be739-153">请参阅中的这些操作**可用类别和操作**列表框中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="be739-153">You see those operations in the **Available categories and operations** list box, as shown below:</span></span>  
  
 <span data-ttu-id="be739-154">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")</span><span class="sxs-lookup"><span data-stu-id="be739-154">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/c8755805-cbb0-40f1-887a-a3123f71ae7e.gif "c8755805-cbb0-40f1-887a-a3123f71ae7e")</span></span>  
  
 <span data-ttu-id="be739-155">在上图中，注意`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`值将出现在**名称**的列**可用类别和操作**列表框。</span><span class="sxs-lookup"><span data-stu-id="be739-155">In the previous figure, notice that the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A` value appears in the **Name** column of the **Available categories and operations** list box.</span></span> <span data-ttu-id="be739-156">将参数传递到`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`构造函数中将出现**节点 ID**的列**可用类别和操作**列表框中，和`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A`值显示为工具提示包含说明中，右键单击时`Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`。</span><span class="sxs-lookup"><span data-stu-id="be739-156">The parameter passed into the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` constructor appears in the **Node ID** column of the **Available categories and operations** list box, and the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.Description%2A` value appears as the tool tip that contains the description, when you right-click the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode.DisplayName%2A`.</span></span>  
  
 <span data-ttu-id="be739-157">若要查看的入站的操作，在[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具，在**选择协定类型**下拉列表中，选择**服务 （入站操作）** 选项。</span><span class="sxs-lookup"><span data-stu-id="be739-157">To see the inbound operations, in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool, in the **Select contract type** drop-down list,select the **Service (Inbound operations)** option.</span></span> <span data-ttu-id="be739-158">请参阅中的入站的 OnReceiveEcho 操作**可用类别和操作**列表框中下, 图中所示：</span><span class="sxs-lookup"><span data-stu-id="be739-158">You see the inbound OnReceiveEcho operation in the **Available categories and operations** list box, as shown in the following figure:</span></span>  
  
 <span data-ttu-id="be739-159">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")</span><span class="sxs-lookup"><span data-stu-id="be739-159">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb.gif "26b7b3c7-bc39-46f8-bc73-7d76fd3c02eb")</span></span>  
  
## <a name="implementing-the-imetadatabrowsehandler"></a><span data-ttu-id="be739-160">实现 IMetadataBrowseHandler</span><span class="sxs-lookup"><span data-stu-id="be739-160">Implementing the IMetadataBrowseHandler</span></span>  
 <span data-ttu-id="be739-161">在此步骤中，你将更新 EchoAdapterMetadataBrowseHandler 类，它是实现 Echo 适配器的元数据浏览，以实现`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法的`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="be739-161">In this step, you update the EchoAdapterMetadataBrowseHandler class to implement the Echo adapter's metadata browse, that is, to implement the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="be739-162">具体而言，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象为每个类别和操作，设置适当的值，该对象，并返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`类别和操作的对象。</span><span class="sxs-lookup"><span data-stu-id="be739-162">Specifically, you create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for each category and operation, set appropriate values for that object, and then return the array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects for category and operations.</span></span> <span data-ttu-id="be739-163">请记住，在创建时`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，你需要传入的节点 ID，而不是显示名称。</span><span class="sxs-lookup"><span data-stu-id="be739-163">Keep in mind that when you create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, you need to pass in the node ID, not the display name.</span></span>  
  
#### <a name="to-update-the-echoadaptermetadatabrowsehandler-class"></a><span data-ttu-id="be739-164">若要更新 EchoAdapterMetadataBrowseHandler 类</span><span class="sxs-lookup"><span data-stu-id="be739-164">To update the EchoAdapterMetadataBrowseHandler class</span></span>  
  
1.  <span data-ttu-id="be739-165">在解决方案资源管理器中双击**EchoAdapterMetadataBrowseHandler.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="be739-165">In Solution Explorer, double-click the **EchoAdapterMetadataBrowseHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="be739-166">在 Visual Studio 编辑器中，右键单击任意位置在编辑器内，在上下文菜单中，指向**大纲**，然后单击**停止大纲显示**。</span><span class="sxs-lookup"><span data-stu-id="be739-166">In the Visual Studio editor, right-click anywhere within the editor, in the context menu, point to **Outlining**, and then click **Stop Outlining**.</span></span>  
  
3.  <span data-ttu-id="be739-167">在 Visual Studio 编辑器中，内部**浏览**方法，用来创建以下内容替换现有逻辑`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`EchoMainCategory 的对象。</span><span class="sxs-lookup"><span data-stu-id="be739-167">In the Visual Studio editor, inside the **Browse** method, replace the existing logic with the following to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for EchoMainCategory.</span></span>  
  
    ```csharp  
    if (MetadataRetrievalNode.Root.NodeId.Equals(nodeId))  
    {  
        MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
        node.DisplayName = "Main Category";  
        node.IsOperation = false;  
        node.Description = "This category contains inbound and outbound categories.";  
        node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound;  
        return new MetadataRetrievalNode[] { node };  
    }  
    ```  
  
4.  <span data-ttu-id="be739-168">继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`Echo/OnReceiveEcho 的对象。</span><span class="sxs-lookup"><span data-stu-id="be739-168">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/OnReceiveEcho.</span></span>  
  
    ```csharp  
    if( "EchoMainCategory".CompareTo(nodeId) == 0 )  
    {  
        // Inbound operations  
        MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        inOpNode1.DisplayName = "OnReceiveEcho";  
        inOpNode1.Description = "This operation echos the location and length of a file dropped in the specified file system.";  
        inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
        inOpNode1.IsOperation = true;  
    ```  
  
5.  <span data-ttu-id="be739-169">继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`Echo/EchoStrings 的对象。</span><span class="sxs-lookup"><span data-stu-id="be739-169">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/EchoStrings.</span></span>  
  
    ```csharp  
    // Outbound operations  
    MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
    outOpNode1.DisplayName = "EchoStrings";  
    outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
    outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode1.IsOperation = true;  
    ```  
  
6.  <span data-ttu-id="be739-170">继续添加以下代码以创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`Echo/EchoGreetings 的对象。</span><span class="sxs-lookup"><span data-stu-id="be739-170">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/EchoGreetings.</span></span>  
  
    ```csharp  
    MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
    outOpNode2.DisplayName = "EchoGreetings";  
    outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
    outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode2.IsOperation = true;  
    ```  
  
7.  <span data-ttu-id="be739-171">继续添加以下代码以创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`回送的对象 / EchoGreetingFromFile。</span><span class="sxs-lookup"><span data-stu-id="be739-171">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for Echo/ EchoGreetingFromFile.</span></span>  
  
    ```csharp  
    MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
    outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
    outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
    outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
    outOpNode3.IsOperation = true;  
    ```  
  
8.  <span data-ttu-id="be739-172">继续添加以下代码以返回一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象或如果不匹配，则为 null。</span><span class="sxs-lookup"><span data-stu-id="be739-172">Continue adding the following code to return an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects or null if not matched.</span></span>  
  
    ```  
        return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
    }  
    return null;  
    ```  
  
9. <span data-ttu-id="be739-173">在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="be739-173">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
10. <span data-ttu-id="be739-174">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="be739-174">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="be739-175">您应已成功生成项目。</span><span class="sxs-lookup"><span data-stu-id="be739-175">You should successfully build the project.</span></span> <span data-ttu-id="be739-176">如果没有，请确保您已按照上述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="be739-176">If not, ensure that you have followed every step above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be739-177">保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="be739-177">You saved your work.</span></span> <span data-ttu-id="be739-178">可以安全地关闭 Visual Studio 或转到下一步[步骤 5： 实现 Echo 适配器的元数据搜索处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="be739-178">You can safely close Visual Studio at this time or go to the next step, [Step 5: Implement the Metadata Search Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="be739-179">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="be739-179">What Did I Just Do?</span></span>  
 <span data-ttu-id="be739-180">只需实现通过实现浏览 Echo 适配器的功能的元数据`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A`方法的`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="be739-180">You just implemented the metadata browsing capability of the Echo adapter, by implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler.Browse%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler` interface.</span></span> <span data-ttu-id="be739-181">具体而言，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象的类别，并为一个数组，则返回它`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。</span><span class="sxs-lookup"><span data-stu-id="be739-181">Specifically, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for the category, and then returned it as an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span> <span data-ttu-id="be739-182">您为每个操作，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，并则返回所有这些对象的数组中`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`。</span><span class="sxs-lookup"><span data-stu-id="be739-182">For each operation, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and then returned all those objects in an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="be739-183">后续步骤</span><span class="sxs-lookup"><span data-stu-id="be739-183">Next Steps</span></span>  
 <span data-ttu-id="be739-184">您实现元数据搜索和解析功能以及出站消息交换。</span><span class="sxs-lookup"><span data-stu-id="be739-184">You implement metadata searching and resolving capabilities, and the outbound message exchange.</span></span> <span data-ttu-id="be739-185">最后，您生成并部署 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="be739-185">Finally, you build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be739-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="be739-186">See Also</span></span>  
 <span data-ttu-id="be739-187">[教程 1： 开发 Echo 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="be739-187">[Tutorial 1: Develop the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="be739-188">[步骤 3： 实现 Echo 适配器的连接](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="be739-188">[Step 3: Implement the Connection for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-implement-the-connection-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="be739-189">步骤 5：实现 Echo 适配器的元数据搜索处理程序</span><span class="sxs-lookup"><span data-stu-id="be739-189">Step 5: Implement the Metadata Search Handler for the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-5-implement-the-metadata-search-handler-for-the-echo-adapter.md)