---
title: 浏览和搜索元数据中使用 WCF LOB 适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbb4add7-6cc8-4b93-b559-471b6e31c01a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67f4717c8621b798ff960487dfd156c4f0934dfc
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "22225669"
---
# <a name="browse-and-search-metadata-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="fd413-102">浏览和搜索元数据中使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="fd413-102">Browse and search metadata using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="fd413-103">本部分提供有关如何通过实现 IMetadataBrowseHandler 和 IMetadataSearchHandler，分别公开使用适配器的浏览和搜索功能的信息。</span><span class="sxs-lookup"><span data-stu-id="fd413-103">This section provides information about how to expose browse and search functionality with an adapter by implementing IMetadataBrowseHandler and IMetadataSearchHandler, respectively.</span></span>  
  
## <a name="imetadatabrowsehandler"></a><span data-ttu-id="fd413-104">IMetadataBrowseHandler</span><span class="sxs-lookup"><span data-stu-id="fd413-104">IMetadataBrowseHandler</span></span>  
 <span data-ttu-id="fd413-105">当将适配器添加到项目，IMetadataBrowseHandler 允许浏览的类别和的适配器支持的操作。</span><span class="sxs-lookup"><span data-stu-id="fd413-105">When adding an adapter to a project, IMetadataBrowseHandler allows browsing of the categories and operations that the adapter supports.</span></span> <span data-ttu-id="fd413-106">这样适配器使用者若要查看在设计时，元数据信息并选择仅在客户端过程要求的操作。</span><span class="sxs-lookup"><span data-stu-id="fd413-106">This allows the adapter consumer to view metadata information at design time, and to select only the operations that the client process requires.</span></span>  
  
 <span data-ttu-id="fd413-107">使用时[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]将适配器添加到项目，IMetadataBrowseHandler 填充**选择协定类型**，**选择类别**，和**可用类别和操作**框。</span><span class="sxs-lookup"><span data-stu-id="fd413-107">When using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to add an adapter to a project, the IMetadataBrowseHandler populates the **Select contract type**, **Select a Category**, and **Available categories and operations** boxes.</span></span>  
  
 <span data-ttu-id="fd413-108">![浏览操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b143971c-a50b-4ef2-a973-dfe4aa4fc17e.gif "b143971c-a50b-4ef2-a973-dfe4aa4fc17e")</span><span class="sxs-lookup"><span data-stu-id="fd413-108">![Browse Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/b143971c-a50b-4ef2-a973-dfe4aa4fc17e.gif "b143971c-a50b-4ef2-a973-dfe4aa4fc17e")</span></span>  
  
 <span data-ttu-id="fd413-109">下面的示例演示如何实现 IMetadataBrowseHandler。</span><span class="sxs-lookup"><span data-stu-id="fd413-109">The following example demonstrates how to implement IMetadataBrowseHandler.</span></span> <span data-ttu-id="fd413-110">构造一个 MetadataRetrievalNode 数组，包含的类别和的适配器支持的操作的信息。</span><span class="sxs-lookup"><span data-stu-id="fd413-110">It constructs a MetadataRetrievalNode array containing information on the categories and operations that the adapter supports.</span></span>  
  
```csharp  
public class EchoAdapterMetadataBrowseHandler : EchoAdapterHandlerBase, IMetadataBrowseHandler  
    {  
        /// <summary>  
        /// Initializes a new instance of the EchoAdapterMetadataBrowseHandler class  
        /// </summary>  
        public EchoAdapterMetadataBrowseHandler(EchoAdapterConnection connection  
            , MetadataLookup metadataLookup)  
            : base(connection, metadataLookup)  
        {  
        }  
  
        #region IMetadataBrowseHandler Members  
  
        /// <summary>  
        /// Retrieves an array of MetadataRetrievalNodes from the target system.  
        /// The browse operation will return nodes starting from the childStartIndex in the path provided in absoluteName, and the number of nodes returned is limited by maxChildNodes.  
        /// The method should complete within the specified timespan or throw a timeout exception.  
        /// If absoluteName is null or an empty string, return nodes starting from the root + childStartIndex.  
        /// If childStartIndex is zero, then return starting at the node indicated by absoluteName (or the root node if absoluteName is null or empty).  
        /// </summary>  
        public MetadataRetrievalNode[] Browse(string nodeId  
            , int childStartIndex  
            , int maxChildNodes, TimeSpan timeout)  
        {  
            // note we don't support timeout in this sample  
            if (MetadataRetrievalNode.Root.NodeId.Equals(nodeId))  
            {  
                MetadataRetrievalNode node = new MetadataRetrievalNode("EchoMainCategory");  
                node.DisplayName = "Main Category";  
                node.IsOperation = false;  
                node.Description = "This category contains inbound and outbound categories.";  
                node.Direction = MetadataRetrievalNodeDirections.Inbound | MetadataRetrievalNodeDirections.Outbound;  
                return new MetadataRetrievalNode[] { node };  
            }  
            else if( "EchoMainCategory".CompareTo(nodeId) == 0 )  
            {  
                // Inbound operations  
                MetadataRetrievalNode inOpNode1 = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
                inOpNode1.DisplayName = "OnReceiveEcho";  
                inOpNode1.Description = "This operation echoes the location and length of a file dropped in the specified file system.";  
                inOpNode1.Direction = MetadataRetrievalNodeDirections.Inbound;  
                inOpNode1.IsOperation = true;  
                // Outbound operations  
                MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
                outOpNode1.DisplayName = "EchoStrings";  
                outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
                outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode1.IsOperation = true;  
                MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
                outOpNode2.DisplayName = "EchoGreetings";  
                outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
                outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode2.IsOperation = true;  
                MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
                outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
                outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
                outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode3.IsOperation = true;  
                return new MetadataRetrievalNode[] { inOpNode1, outOpNode1, outOpNode2, outOpNode3 };  
            }  
  
            return null;  
        }  
  
        #endregion IMetadataBrowseHandler Members  
    }  
```  
  
## <a name="imetadatasearchhandler"></a><span data-ttu-id="fd413-111">IMetadataSearchHandler</span><span class="sxs-lookup"><span data-stu-id="fd413-111">IMetadataSearchHandler</span></span>  
 <span data-ttu-id="fd413-112">在适配器内实现 IMetadataSearchHandler 提供的功能来搜索可用操作在设计时输入的搜索词，如操作名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="fd413-112">Implementing IMetadataSearchHandler within an adapter provides the ability to search for available operations at design time by entering a search term, such as a portion of an operation name.</span></span> <span data-ttu-id="fd413-113">这是如果你的适配器包含许多操作，因为在输入搜索值限制返回的操作非常有用。</span><span class="sxs-lookup"><span data-stu-id="fd413-113">This is very useful if your adapter contains many operations, since you can enter search values to limit the operations returned.</span></span>  
  
 <span data-ttu-id="fd413-114">使用时[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要将适配器添加到项目，IMetadataSearchHandler 解析搜索字符串中输入**类别中的搜索**框中，并返回匹配的列表中的项**可用类别和操作**框。</span><span class="sxs-lookup"><span data-stu-id="fd413-114">When using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to add an adapter to a project, the IMetadataSearchHandler resolves search strings entered in the **Search in category** box, and returns a list of matching items in the **Available categories and operations** box.</span></span>  
  
 <span data-ttu-id="fd413-115">![搜索操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/48dc9ca6-8697-42bf-9419-5fa35a19937f.gif "48dc9ca6-8697-42bf-9419-5fa35a19937f")</span><span class="sxs-lookup"><span data-stu-id="fd413-115">![Search Operations](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/48dc9ca6-8697-42bf-9419-5fa35a19937f.gif "48dc9ca6-8697-42bf-9419-5fa35a19937f")</span></span>  
  
 <span data-ttu-id="fd413-116">你还可以执行搜索 svcutil.exe 生成 WSDL 或代理的适配器时，通过将搜索值传递作为查询字符串中的操作的格式为值。</span><span class="sxs-lookup"><span data-stu-id="fd413-116">You can also perform searches with svcutil.exe when generating WSDL or proxy for an adapter, by passing the search value as a query string in the format of op=value.</span></span> <span data-ttu-id="fd413-117">下面是使用 svcutil.exe 以返回回显/EchoStrings 的操作信息的示例。</span><span class="sxs-lookup"><span data-stu-id="fd413-117">The following is an example of using svcutil.exe to return only the Echo/EchoStrings operation information.</span></span>  
  
```  
svcutil.exe “echov2://lobhostname/lobapplication?enableAuthentication=False&op=Echo/EchoStrings” /target:metadata  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="fd413-118">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不提供默认通配符的搜索功能，例如 Echo \* 或 %echo%。</span><span class="sxs-lookup"><span data-stu-id="fd413-118">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not provide a default wildcard search functionality such as Echo\* or %Echo%.</span></span> <span data-ttu-id="fd413-119">负责适配器创作者能够实现通配符或模式匹配功能。</span><span class="sxs-lookup"><span data-stu-id="fd413-119">It is up to the adapter author to implement wildcard or pattern matching functionality.</span></span>  
  
 <span data-ttu-id="fd413-120">下面的示例演示如何实现 IMetadataSearchHandler。</span><span class="sxs-lookup"><span data-stu-id="fd413-120">The following example demonstrates how to implement IMetadataSearchHandler.</span></span> <span data-ttu-id="fd413-121">构造一个 MetadataRetrievalNode 数组，包含的类别和的适配器支持的操作有关的信息。</span><span class="sxs-lookup"><span data-stu-id="fd413-121">It constructs a MetadataRetrievalNode array containing information about the categories and operations that the adapter supports.</span></span>  
  
```csharp  
public class EchoAdapterMetadataSearchHandler : EchoAdapterHandlerBase, IMetadataSearchHandler  
    {  
        /// <summary>  
        /// Initializes a new instance of the EchoAdapterMetadataSearchHandler class  
        /// </summary>  
        public EchoAdapterMetadataSearchHandler(EchoAdapterConnection connection  
            , MetadataLookup metadataLookup)  
            : base(connection, metadataLookup)  
        {  
        }  
  
        #region IMetadataSearchHandler Members  
  
        /// <summary>  
        /// Retrieves an array of MetadataRetrievalNodes (see Microsoft.ServiceModel.Channels) from the target system.  
        /// The search will begin at the path provided in absoluteName, which points to a location in the tree of metadata nodes.  
        /// The contents of the array are filtered by SearchCriteria and the number of nodes returned is limited by maxChildNodes.  
        /// The method should complete within the specified timespan or throw a timeout exception.  If absoluteName is null or an empty string, return nodes starting from the root.  
        /// If SearchCriteria is null or an empty string, return all nodes.  
        /// </summary>  
        public MetadataRetrievalNode[] Search(string nodeId  
            , string searchCriteria  
            , int maxChildNodes, TimeSpan timeout)  
        {  
  
            List<MetadataRetrievalNode> resultList = new List<MetadataRetrievalNode>();  
            if ("OnReceiveEcho".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode nodeInbound = new MetadataRetrievalNode("Echo/OnReceiveEcho");  
                nodeInbound.DisplayName = "OnReceiveEcho";  
                nodeInbound.Description = "This operation echos the location and length of a file dropped in the specified file system.";  
                nodeInbound.Direction = MetadataRetrievalNodeDirections.Inbound;  
                nodeInbound.IsOperation = true;  
                resultList.Add(nodeInbound);  
            }  
            if ("EchoStrings".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode1 = new MetadataRetrievalNode("Echo/EchoStrings");  
                outOpNode1.DisplayName = "EchoStrings";  
                outOpNode1.Description = "This operation echoes the incoming string COUNT number of times in a string array.";  
                outOpNode1.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode1.IsOperation = true;  
                resultList.Add(outOpNode1);  
            }  
            if ("EchoGreetings".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode2 = new MetadataRetrievalNode("Echo/EchoGreetings");  
                outOpNode2.DisplayName = "EchoGreetings";  
                outOpNode2.Description = "This operation echoes the incoming Greeting object COUNT number of times in an array of type Greeting.";  
                outOpNode2.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode2.IsOperation = true;  
                resultList.Add(outOpNode2);  
            }  
            if ("EchoCustomGreetingFromFile".ToLower().Contains(searchCriteria.ToLower()))  
            {  
                MetadataRetrievalNode outOpNode3 = new MetadataRetrievalNode("Echo/EchoCustomGreetingFromFile");  
                outOpNode3.DisplayName = "EchoCustomGreetingFromFile";  
                outOpNode3.Description = "This operation echoes the greeting object by reading its instance from a file. The Greeting object's metadata is obtained from a predefined XSD file.";  
                outOpNode3.Direction = MetadataRetrievalNodeDirections.Outbound;  
                outOpNode3.IsOperation = true;  
                resultList.Add(outOpNode3);  
            }  
            return resultList.ToArray();  
        }  
  
        #endregion IMetadataSearchHandler Members  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd413-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd413-122">See Also</span></span>  
 [<span data-ttu-id="fd413-123">开发活动</span><span class="sxs-lookup"><span data-stu-id="fd413-123">Development Activities</span></span>](../../esb-toolkit/development-activities.md)