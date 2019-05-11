---
title: 如何查看本地服务器上的程序集和类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ddf6f60-9fef-4997-8b42-24eefd7ab0d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119fa6672ca5b01470336b4f8749c96459112e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333075"
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a><span data-ttu-id="87388-102">如何查看本地服务器上的程序集和类型</span><span class="sxs-lookup"><span data-stu-id="87388-102">How to View Assemblies and Types on the Local Server</span></span>
<span data-ttu-id="87388-103">可以使用 BizTalk 程序集查看器来检查所有 BizTalk 程序集和本地服务器上安装的类型。</span><span class="sxs-lookup"><span data-stu-id="87388-103">You can use the BizTalk Assembly Viewer to examine all BizTalk assemblies and types installed on the local server.</span></span>  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a><span data-ttu-id="87388-104">若要查看所有 BizTalk Server 程序集安装到 GAC 中</span><span class="sxs-lookup"><span data-stu-id="87388-104">To view all BizTalk Server assemblies installed in the GAC</span></span>  
  
-   <span data-ttu-id="87388-105">若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。</span><span class="sxs-lookup"><span data-stu-id="87388-105">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
     <span data-ttu-id="87388-106">所有 BizTalk 程序集安装在计算机上的全局程序集缓存 (GAC) 中都显示。</span><span class="sxs-lookup"><span data-stu-id="87388-106">All BizTalk assemblies installed in the global assembly cache (GAC) on the computer appear.</span></span>  
  
     <span data-ttu-id="87388-107">![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")</span><span class="sxs-lookup"><span data-stu-id="87388-107">![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")</span></span>  
<span data-ttu-id="87388-108">程序集查看器打开页</span><span class="sxs-lookup"><span data-stu-id="87388-108">Assembly Viewer open page</span></span>  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a><span data-ttu-id="87388-109">若要查看 BizTalk 程序集的类型、 属性和引用</span><span class="sxs-lookup"><span data-stu-id="87388-109">To view types, attributes, and references for a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="87388-110">若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。</span><span class="sxs-lookup"><span data-stu-id="87388-110">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="87388-111">双击适当的程序集。</span><span class="sxs-lookup"><span data-stu-id="87388-111">Double click the appropriate assembly.</span></span>  
  
     <span data-ttu-id="87388-112">在右窗格中显示了 BizTalk 程序集类型。</span><span class="sxs-lookup"><span data-stu-id="87388-112">The BizTalk assembly types appear in the right pane.</span></span> <span data-ttu-id="87388-113">属性和类型显示在左窗格中。</span><span class="sxs-lookup"><span data-stu-id="87388-113">The attributes and types appear in the left pane.</span></span>  
  
     <span data-ttu-id="87388-114">您还可导航到已安装的程序集的位置通过单击**基本代码**的左上角的任务窗格中的链接。</span><span class="sxs-lookup"><span data-stu-id="87388-114">You can also navigate to the installed location of the assembly by clicking the **Codebase** link in the upper left section of the task pane.</span></span> <span data-ttu-id="87388-115">（在 Windows 资源管理器是在文件夹视图中，因为任务窗格被文件夹列表时无法查看此链接。）</span><span class="sxs-lookup"><span data-stu-id="87388-115">(You cannot view this link when Windows Explorer is in Folder view because the task pane is replaced by the folder list.)</span></span>  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a><span data-ttu-id="87388-116">若要查看 BizTalk 程序集中的一种类型的内容</span><span class="sxs-lookup"><span data-stu-id="87388-116">To view the contents of a type in a BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="87388-117">若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。</span><span class="sxs-lookup"><span data-stu-id="87388-117">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="87388-118">双击适当的程序集。</span><span class="sxs-lookup"><span data-stu-id="87388-118">Double click the appropriate assembly.</span></span>  
  
3.  <span data-ttu-id="87388-119">在右窗格中，双击适当的类型。</span><span class="sxs-lookup"><span data-stu-id="87388-119">In the right pane, double-click the appropriate type.</span></span>  
  
     <span data-ttu-id="87388-120">**类型内容查看器**窗口将打开并显示 XML 定义。</span><span class="sxs-lookup"><span data-stu-id="87388-120">The **Type Content Viewer** window opens and the XML definition appears.</span></span>  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a><span data-ttu-id="87388-121">若要在 GAC 中添加 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="87388-121">To add a BizTalk assembly in the GAC</span></span>  
  
1.  <span data-ttu-id="87388-122">若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。</span><span class="sxs-lookup"><span data-stu-id="87388-122">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="87388-123">使用 Windows 资源管理器导航到你想要在 GAC 中添加的程序集。</span><span class="sxs-lookup"><span data-stu-id="87388-123">Use Windows Explorer to navigate to the assembly that you want to add in the GAC.</span></span>  
  
3.  <span data-ttu-id="87388-124">将程序集拖放到 BizTalk 程序集查看器上。</span><span class="sxs-lookup"><span data-stu-id="87388-124">Drag the assembly and drop it into the BizTalk Assembly Viewer.</span></span>  
  
     <span data-ttu-id="87388-125">BizTalk 程序集查看器接受仅 BizTalk Server 程序集。</span><span class="sxs-lookup"><span data-stu-id="87388-125">The BizTalk Assembly Viewer accepts only BizTalk Server assemblies.</span></span> <span data-ttu-id="87388-126">如果在查看器中删除非 BizTalk 程序集，则忽略它。</span><span class="sxs-lookup"><span data-stu-id="87388-126">If you drop a non-BizTalk assembly in the viewer, it is ignored.</span></span>  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a><span data-ttu-id="87388-127">若要从 GAC 中删除 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="87388-127">To remove a BizTalk assembly from the GAC</span></span>  
  
1.  <span data-ttu-id="87388-128">若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。</span><span class="sxs-lookup"><span data-stu-id="87388-128">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="87388-129">右键单击你想要从 GAC 和单击删除的程序集**删除**。</span><span class="sxs-lookup"><span data-stu-id="87388-129">Right-click the assembly you want to remove from the GAC and click **Delete**.</span></span>  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a><span data-ttu-id="87388-130">若要搜索所有 BizTalk 程序集中的类型</span><span class="sxs-lookup"><span data-stu-id="87388-130">To search for a type in all BizTalk assemblies</span></span>  
  
1.  <span data-ttu-id="87388-131">若要打开 BizTalk 程序集查看器，请双击**我的电脑**，然后双击**BizTalk Server 程序集**。</span><span class="sxs-lookup"><span data-stu-id="87388-131">To open the BizTalk Assembly Viewer, double-click **My Computer**, and then double-click **BizTalk Server Assemblies**.</span></span>  
  
2.  <span data-ttu-id="87388-132">从菜单栏中，单击**Biz 通信服务器搜索**图标。</span><span class="sxs-lookup"><span data-stu-id="87388-132">From the menu bar, click the **Biz Talk Server Search** icon.</span></span>  
  
3.  <span data-ttu-id="87388-133">在搜索窗口中，指定在类型**查找类型**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="87388-133">In the Search window, specify the type in the **Find Types** drop-down list.</span></span>  
  
4.  <span data-ttu-id="87388-134">在中**在 BizTalk Server 程序集中查找**下拉列表中，选择要搜索的程序集。</span><span class="sxs-lookup"><span data-stu-id="87388-134">In the **Look in BizTalk Server assemblies** drop-down list, select the assemblies to be searched.</span></span>  
  
5.  <span data-ttu-id="87388-135">若要缩小搜索范围以包括引用的指定类型的类型，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="87388-135">To narrow your search to include only types that are referenced by a specified type, do the following:</span></span>  
  
    1.  <span data-ttu-id="87388-136">单击**高级搜索条件**链接。</span><span class="sxs-lookup"><span data-stu-id="87388-136">Click the **Advanced Search Criteria** link.</span></span>  
  
    2.  <span data-ttu-id="87388-137">在中**引用的**下拉列表中，选择的类型。</span><span class="sxs-lookup"><span data-stu-id="87388-137">In the **Which are referenced by** drop-down list, select the type.</span></span>  
  
    3.  <span data-ttu-id="87388-138">单击 **“搜索”**。</span><span class="sxs-lookup"><span data-stu-id="87388-138">Click **Search**.</span></span>  
  
         <span data-ttu-id="87388-139">指定的类型显示在搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="87388-139">The specified types appear in the search results.</span></span>  
  
         <span data-ttu-id="87388-140">![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")</span><span class="sxs-lookup"><span data-stu-id="87388-140">![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")</span></span>  
<span data-ttu-id="87388-141">BizTalk 程序集类型</span><span class="sxs-lookup"><span data-stu-id="87388-141">BizTalk Assembly Types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87388-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="87388-142">See Also</span></span>  
 [<span data-ttu-id="87388-143">使用 BizTalk 程序集查看器查看程序集</span><span class="sxs-lookup"><span data-stu-id="87388-143">Viewing Assemblies with the BizTalk Assembly Viewer</span></span>](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)