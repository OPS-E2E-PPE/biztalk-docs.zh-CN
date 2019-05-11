---
title: 步骤 5：实现 Echo 适配器的元数据搜索处理程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a133a99-1d6c-4634-b928-0f4f23c6f6e4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 764f5ff5bdd95ad51cfc5cc9c7495c27905131f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363135"
---
# <a name="step-5-implement-the-metadata-search-handler-for-the-echo-adapter"></a><span data-ttu-id="6dc7c-102">步骤 5：实现 Echo 适配器的元数据搜索处理程序</span><span class="sxs-lookup"><span data-stu-id="6dc7c-102">Step 5: Implement the Metadata Search Handler for the Echo Adapter</span></span>
<span data-ttu-id="6dc7c-103">![步骤 5 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span><span class="sxs-lookup"><span data-stu-id="6dc7c-103">![Step 5 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-5of9.gif "Step_5of9")</span></span>  
  
 <span data-ttu-id="6dc7c-104">**若要完成的时间：** 30 分钟</span><span class="sxs-lookup"><span data-stu-id="6dc7c-104">**Time to complete:** 30 minutes</span></span>  
  
 <span data-ttu-id="6dc7c-105">在本教程的此步骤中，将实现 Echo 适配器的搜索功能。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-105">In this step of the tutorial, you implement the search capability of the Echo adapter.</span></span> <span data-ttu-id="6dc7c-106">与不同的浏览、 搜索是可选的。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-106">Unlike browse, search is optional.</span></span> <span data-ttu-id="6dc7c-107">根据[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，若要支持搜索功能，必须实现`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-107">According to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], to support search capability, you must implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="6dc7c-108">Echo 适配器[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]自动生成一个名为 EchoAdapterMetadataSearchHandler 的派生的类。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-108">For the Echo adapter, the [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] automatically generates one derived class called EchoAdapterMetadataSearchHandler.</span></span>  
  
 <span data-ttu-id="6dc7c-109">第一次更新 EchoAdapterMetadataSearchHandler 类，以获取更好地了解如何实现此接口，如何填充`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象，并且搜索结果中的显示方式[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]工具。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-109">You first update the EchoAdapterMetadataSearchHandler class to get a better understanding of how to implement this interface, how to populate  `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object, and how the search results appear in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] tool.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6dc7c-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="6dc7c-110">Prerequisites</span></span>  
 <span data-ttu-id="6dc7c-111">在开始此步骤之前，完成[步骤 4:实现 Echo 适配器的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-111">Before you begin this step, complete [Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md).</span></span> <span data-ttu-id="6dc7c-112">您还必须清楚地了解有关以下类：</span><span class="sxs-lookup"><span data-stu-id="6dc7c-112">You must also have a clear understanding about the following classes:</span></span>  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`
  
-   `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`  
  
-   `Microsoft.ServiceModel.Channels.MetadataRetrievalNodeDirections`  
  
## <a name="the-imetadatasearchhandler-interface"></a><span data-ttu-id="6dc7c-113">IMetadataSearchHandler 接口</span><span class="sxs-lookup"><span data-stu-id="6dc7c-113">The IMetadataSearchHandler Interface</span></span>  
 <span data-ttu-id="6dc7c-114">`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`定义为：</span><span class="sxs-lookup"><span data-stu-id="6dc7c-114">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` is defined as:</span></span>  
  
```  
public interface IMetadataSearchHandler : IConnectionHandler, IDisposable  
{  
    MetadataRetrievalNode[] Search(string nodeId, string searchCriteria, int maxChildNodes, TimeSpan timeout);  
}  
```  
  
 <span data-ttu-id="6dc7c-115">`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法返回的数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象根据搜索条件。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-115">The `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method returns an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects based on the search criteria.</span></span> <span data-ttu-id="6dc7c-116">搜索方法的参数定义如下表所述：</span><span class="sxs-lookup"><span data-stu-id="6dc7c-116">The parameter definitions for the Search method are described in the following table:</span></span>  
  
|<span data-ttu-id="6dc7c-117">**参数**</span><span class="sxs-lookup"><span data-stu-id="6dc7c-117">**Parameter**</span></span>|<span data-ttu-id="6dc7c-118">**定义**</span><span class="sxs-lookup"><span data-stu-id="6dc7c-118">**Definition**</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="6dc7c-119">nodeId</span><span class="sxs-lookup"><span data-stu-id="6dc7c-119">nodeId</span></span>|<span data-ttu-id="6dc7c-120">要从开始搜索的节点 ID。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-120">The node ID to start searching from.</span></span> <span data-ttu-id="6dc7c-121">如果为 null 或空字符串 ("")，将从根节点 （"/"） 检索操作。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-121">If null or an empty string (""), operations will be retrieved from the root node ("/").</span></span>|  
|<span data-ttu-id="6dc7c-122">searchCriteria</span><span class="sxs-lookup"><span data-stu-id="6dc7c-122">searchCriteria</span></span>|<span data-ttu-id="6dc7c-123">搜索条件，这是特定于适配器的。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-123">The search criteria, which is adapter-specific.</span></span> <span data-ttu-id="6dc7c-124">如果不指定了任何搜索条件，则适配器应返回所有节点。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-124">If no search criteria are specified, the adapter should return all nodes.</span></span>|  
|<span data-ttu-id="6dc7c-125">maxChildNodes</span><span class="sxs-lookup"><span data-stu-id="6dc7c-125">maxChildNodes</span></span>|<span data-ttu-id="6dc7c-126">最大可返回的结果节点数。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-126">The maximum number of result nodes to return.</span></span> <span data-ttu-id="6dc7c-127">使用 Int32.Max 检索所有结果节点。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-127">Use Int32.Max to retrieve all result nodes.</span></span><br /><br /> <span data-ttu-id="6dc7c-128">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-128">Not supported by the Echo adapter.</span></span>|  
|<span data-ttu-id="6dc7c-129">timeout</span><span class="sxs-lookup"><span data-stu-id="6dc7c-129">timeout</span></span>|<span data-ttu-id="6dc7c-130">若要完成该操作允许的最大时间。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-130">The maximum time allowed for the operation to complete.</span></span><br /><br /> <span data-ttu-id="6dc7c-131">不支持 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-131">Not supported by the Echo adapter.</span></span>|  
  
 <span data-ttu-id="6dc7c-132">搜索结果中，为您的适配器可以选择返回类别节点和/或操作节点。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-132">For search result, your adapter can choose to return either category nodes or operation nodes, or both.</span></span> <span data-ttu-id="6dc7c-133">将搜索功能的类型由您的适配器支持。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-133">It is up to the type of search feature your adapter supports.</span></span>  
  
## <a name="echo-adapter-metadata-search"></a><span data-ttu-id="6dc7c-134">Echo 适配器的元数据搜索</span><span class="sxs-lookup"><span data-stu-id="6dc7c-134">Echo adapter Metadata Search</span></span>  
 <span data-ttu-id="6dc7c-135">根据目标系统的类别和操作，有许多种方法来生成一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`可以返回的对象。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-135">Depending on your target system's categories and operations, there are many ways to build an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects to return.</span></span> <span data-ttu-id="6dc7c-136">Echo 适配器实现搜索功能的方法是通过使用其下面的列表中的节点 ID 的每个操作：</span><span class="sxs-lookup"><span data-stu-id="6dc7c-136">The way Echo adapter implements the search functionality is to go through every operation with its node ID in the following list:</span></span>  
  
```  
Echo/OnReceiveEcho, inbound operation  
Echo/EchoStrings, outbound operation  
Echo/EchoGreetings, outbound operation  
Echo/EchoGreetingFromFile, outbound operation  
```  
  
- <span data-ttu-id="6dc7c-137">如果节点 ID 然后匹配搜索条件，它将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象使用该操作的节点 ID，然后将具有值的属性。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-137">If the node ID then matches the search criteria, it creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object using the node ID of the operation, and then assigns the properties with values.</span></span> <span data-ttu-id="6dc7c-138">例如，</span><span class="sxs-lookup"><span data-stu-id="6dc7c-138">For example,</span></span>  
  
  ```  
  MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho"); //create the MetadataRetrievalNode using the operation's node ID.  
  nodeInbound.DisplayName = "OnReceiveEcho"; //The Display Name shown in the Name column of the Add Adapter Service Reference Visual Studio Plug-in  
  nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  //The Description shown as the tool tip in the Add Adapter Service Visual Studio Plug-in  
  nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;    //It is an inbound operation  
  nodeInbound.IsOperation = true;  //It is an operation, not category.  
  ```  
  
- <span data-ttu-id="6dc7c-139">然后将该对象添加到一系列`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s，例如，</span><span class="sxs-lookup"><span data-stu-id="6dc7c-139">And then add the object to a collection of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode`s, for example,</span></span>  
  
  ```  
  resultList.Add(nodeInbound);  
  ```  
  
- <span data-ttu-id="6dc7c-140">最后的数组格式返回的集合。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-140">Lastly returns the collection in an array format.</span></span>  
  
  ```  
  return resultList.ToArray();  
  ```  
  
  <span data-ttu-id="6dc7c-141">可以使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]工具执行的搜索基于连接的可用操作。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-141">You can use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] tools to perform a connection-based search for the available operations.</span></span> <span data-ttu-id="6dc7c-142">例如下, 图显示的搜索条件时将字符串**问候**，搜索返回**EchoGreetings**并**EchoGreetingFromFile**操作。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-142">For example, the following figure shows that when the searching criteria is the string **Greeting**, the search returns the **EchoGreetings** and **EchoGreetingFromFile** operations.</span></span>  
  
  <span data-ttu-id="6dc7c-143">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")</span><span class="sxs-lookup"><span data-stu-id="6dc7c-143">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/874c046a-590f-4047-9b9c-bb8074664755.gif "874c046a-590f-4047-9b9c-bb8074664755")</span></span>  
  
  <span data-ttu-id="6dc7c-144">如果不找到任何匹配项，则这两个工具将返回在下图中显示的错误消息。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-144">If no match is found, either tool will return the error message shown in the following figure.</span></span>  
  
  <span data-ttu-id="6dc7c-145">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")</span><span class="sxs-lookup"><span data-stu-id="6dc7c-145">![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cb1f79a2-a63d-4828-9dce-905c026cd1dc.gif "cb1f79a2-a63d-4828-9dce-905c026cd1dc")</span></span>  
  
## <a name="implementing-the-imetadatasearchhandler"></a><span data-ttu-id="6dc7c-146">实现 IMetadataSearchHandler</span><span class="sxs-lookup"><span data-stu-id="6dc7c-146">Implementing the IMetadataSearchHandler</span></span>  
 <span data-ttu-id="6dc7c-147">将实现`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法的`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-147">You will implement the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="6dc7c-148">如果该操作显示名称与搜索条件匹配，则将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象对于该操作，并将该对象添加到一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-148">If the operation's display name matches the search criteria, you will create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for that operation, and then add that object to an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
#### <a name="to-update-the-echoadaptermetadatasearchhandler-class"></a><span data-ttu-id="6dc7c-149">若要更新 EchoAdapterMetadataSearchHandler 类</span><span class="sxs-lookup"><span data-stu-id="6dc7c-149">To update the EchoAdapterMetadataSearchHandler class</span></span>  
  
1.  <span data-ttu-id="6dc7c-150">在解决方案资源管理器中双击**EchoAdapterMetadataSearchHandler.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-150">In Solution Explorer, double-click the **EchoAdapterMetadataSearchHandler.cs** file.</span></span>  
  
2.  <span data-ttu-id="6dc7c-151">在 Visual Studio 编辑器中，内部**搜索**方法，用以下代码替换现有的逻辑。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-151">In the Visual Studio editor, inside the **Search** method, replace the existing logic with the following.</span></span> <span data-ttu-id="6dc7c-152">此逻辑将创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/OnReceiveEcho 是否与指定的搜索条件匹配。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-152">This logic creates a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/OnReceiveEcho matches the specified search criteria.</span></span>  
  
    ```csharp  
    List<MetadataRetrievalNode> resultList = new List<MetadataRetrievalNode>();  
    if ("OnReceiveEcho".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
        nodeInbound.DisplayName = "OnReceiveEcho";  
        nodeInbound.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
        nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;  
        nodeInbound.IsOperation = true;  
        resultList.Add(nodeInbound);  
    }  
    ```  
  
3.  <span data-ttu-id="6dc7c-153">继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/EchoStrings 是否与指定的搜索条件匹配。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-153">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoStrings matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoStrings".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
        outOpNode1.DisplayName = "EchoStrings";  
        outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
        outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode1.IsOperation = true;  
        resultList.Add(outOpNode1);  
    }  
    ```  
  
4.  <span data-ttu-id="6dc7c-154">继续添加以下逻辑创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/EchoGreetings 是否与指定的搜索条件匹配。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-154">Continue adding the following logic to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetings matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoGreetings".ToLower().Contains(searchCriteria.ToLower()))  
        {  
            MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
            outOpNode2.DisplayName = "EchoGreetings";  
            outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
            outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
            outOpNode2.IsOperation = true;  
            resultList.Add(outOpNode2);  
        }  
    ```  
  
5.  <span data-ttu-id="6dc7c-155">继续添加以下代码以创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象 Echo/EchoGreetingFromFile 是否与指定的搜索条件匹配。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-155">Continue adding the following code to create a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object if Echo/EchoGreetingFromFile matches the specified search criteria.</span></span>  
  
    ```csharp  
    if ("EchoCustomGreetingFromFile".ToLower().Contains(searchCriteria.ToLower()))  
    {  
        MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
        outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
        outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
        outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
        outOpNode3.IsOperation = true;  
        resultList.Add(outOpNode3);  
    }  
    ```  
  
6.  <span data-ttu-id="6dc7c-156">继续添加以下代码以返回一个数组`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-156">Continue adding the following code to return an array of `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
    ```csharp  
    return resultList.ToArray();  
    ```  
  
7.  <span data-ttu-id="6dc7c-157">在 Visual Studio 中，在**文件**菜单上，单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-157">In Visual Studio, on the **File** menu, click **Save All**.</span></span>  
  
8.  <span data-ttu-id="6dc7c-158">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-158">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="6dc7c-159">您应已成功编译项目。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-159">You should successfully compiled the project.</span></span> <span data-ttu-id="6dc7c-160">如果没有，请确保您已按照上述每个步骤。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-160">If not, ensure that you have followed every step above.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6dc7c-161">保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-161">You saved your work.</span></span> <span data-ttu-id="6dc7c-162">可以安全地关闭 Visual Studio 或转到下一步，[步骤 6:实现 Echo 适配器的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-162">You can safely close Visual Studio at this time or go to the next step, [Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md).</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="6dc7c-163">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="6dc7c-163">What Did I Just Do?</span></span>  
 <span data-ttu-id="6dc7c-164">只需实现通过实现搜索功能的 Echo 适配器的元数据`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A`方法的`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`接口。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-164">You just implemented the metadata searching capability of the Echo adapter, by implementing the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler.Search%2A` method of the `Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler` interface.</span></span> <span data-ttu-id="6dc7c-165">具体而言，创建`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对于每个操作与条件匹配，则返回一个数组对象`Microsoft.ServiceModel.Channels.MetadataRetrievalNode`对象。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-165">Specifically, you created a `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` object for every operation that matches the criteria and then returned an array of the `Microsoft.ServiceModel.Channels.MetadataRetrievalNode` objects.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6dc7c-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6dc7c-166">Next Steps</span></span>  
 <span data-ttu-id="6dc7c-167">将实现解析功能和出站和入站消息的 exchange 功能的元数据。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-167">You will implement the metadata resolving capability, and the outbound and inbound message exchange capabilities.</span></span> <span data-ttu-id="6dc7c-168">最后，将生成并部署 Echo 适配器。</span><span class="sxs-lookup"><span data-stu-id="6dc7c-168">Finally, you will build and deploy the Echo adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc7c-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="6dc7c-169">See Also</span></span>  
 <span data-ttu-id="6dc7c-170">[步骤 4：实现 Echo 适配器的元数据浏览处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6dc7c-170">[Step 4: Implement the Metadata Browse Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-4-implement-the-metadata-browse-handler-for-the-echo-adapter.md) </span></span>  
 <span data-ttu-id="6dc7c-171">[步骤 6：实现 Echo 适配器的元数据解析处理程序](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6dc7c-171">[Step 6: Implement the Metadata Resolve Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-6-implement-the-metadata-resolve-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="6dc7c-172">教程 1:开发 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="6dc7c-172">Tutorial 1: Develop the Echo Adapter</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-1-develop-the-echo-adapter.md)