---
title: "如何打开、 保存、 关闭，以及重命名映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bad04c72e4c3f0caf1af8e223d3f17e4687b736
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-open-save-close-and-rename-maps"></a><span data-ttu-id="c437b-102">如何打开、 保存、 关闭，以及重命名映射</span><span class="sxs-lookup"><span data-stu-id="c437b-102">How to Open, Save, Close, and Rename Maps</span></span>
<span data-ttu-id="c437b-103">在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，映射在文件系统中以扩展名为 .btm 的文件形式存在。</span><span class="sxs-lookup"><span data-stu-id="c437b-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], maps exist as files in the file system with .btm extensions.</span></span> <span data-ttu-id="c437b-104">不过，它是得更加常见，若要使用映射作为 BizTalk 项目，你在其中执行操作，如打开、 保存和关闭地图中的项。</span><span class="sxs-lookup"><span data-stu-id="c437b-104">Nevertheless, it is much more common to work with maps as items in a BizTalk project, from which you perform operations such as opening, saving, and closing maps.</span></span>  
  
### <a name="to-open-a-map"></a><span data-ttu-id="c437b-105">若要打开地图</span><span class="sxs-lookup"><span data-stu-id="c437b-105">To open a map</span></span>  
  
1.  <span data-ttu-id="c437b-106">在解决方案资源管理器，选择你想要打开的映射。</span><span class="sxs-lookup"><span data-stu-id="c437b-106">In Solution Explorer, select the map you want to open.</span></span>  
  
2.  <span data-ttu-id="c437b-107">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="c437b-107">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="c437b-108">在 BizTalk 映射程序中打开代码图。</span><span class="sxs-lookup"><span data-stu-id="c437b-108">The map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c437b-109">你可以右键单击解决方案资源管理器中的映射，然后单击**打开**，或只需双击解决方案资源管理器中的映射。</span><span class="sxs-lookup"><span data-stu-id="c437b-109">You can also right-click the map in Solution Explorer, and then click **Open**, or simply double-click the map in Solution Explorer.</span></span>  
  
### <a name="to-save-a-map"></a><span data-ttu-id="c437b-110">用于保存代码图</span><span class="sxs-lookup"><span data-stu-id="c437b-110">To save a map</span></span>  
  
1.  <span data-ttu-id="c437b-111">在解决方案资源管理器，选择你想要保存的映射。</span><span class="sxs-lookup"><span data-stu-id="c437b-111">In Solution Explorer, select the map you want to save.</span></span>  
  
2.  <span data-ttu-id="c437b-112">上**文件**菜单上，单击**保存*\<映射名称 >***。</span><span class="sxs-lookup"><span data-stu-id="c437b-112">On the **File** menu, click **Save *\<Name of Map>***.</span></span>  
  
### <a name="to-save-a-map-to-a-new-location"></a><span data-ttu-id="c437b-113">若要保存到一个新位置的地图</span><span class="sxs-lookup"><span data-stu-id="c437b-113">To save a map to a new location</span></span>  
  
1.  <span data-ttu-id="c437b-114">在解决方案资源管理器，选择你想要将保存到新位置的映射。</span><span class="sxs-lookup"><span data-stu-id="c437b-114">In Solution Explorer, select the map you want to save to a new location.</span></span>  
  
2.  <span data-ttu-id="c437b-115">上**文件**菜单上，单击**保存*\<映射名称 >*作为**。</span><span class="sxs-lookup"><span data-stu-id="c437b-115">On the **File** menu, click **Save *\<Name of Map>* As**.</span></span>  
  
3.  <span data-ttu-id="c437b-116">在**文件另存为**对话框中，浏览到你想要保存代码图的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="c437b-116">In the **Save File As** dialog box, browse to the folder location where you want to save the map.</span></span>  
  
4.  <span data-ttu-id="c437b-117">在**文件名**框中，键入该文件的名称，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c437b-117">In the **File name** box, type a name for the file, and then click **Save**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c437b-118">不使用地图的以下名称:"XmlContent"、"SourceSchemas"、"TargetSchemas"或"XsltArgumentListContent";因此，这样做将在 C# 中生成的代码的相应的.NET 程序集导致编译问题。</span><span class="sxs-lookup"><span data-stu-id="c437b-118">Do not use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent"; doing so will cause compilation problems in the generated C# code in the corresponding .NET assembly.</span></span> <span data-ttu-id="c437b-119">问题和及其解决方法有关的信息，请参阅[故障排除地图](../core/troubleshooting-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="c437b-119">For information about issues and their resolution, see [Troubleshooting Maps](../core/troubleshooting-maps.md).</span></span>  
  
### <a name="to-rename-a-map"></a><span data-ttu-id="c437b-120">若要重命名地图</span><span class="sxs-lookup"><span data-stu-id="c437b-120">To rename a map</span></span>  
  
1.  <span data-ttu-id="c437b-121">在解决方案资源管理器，右键单击你想要重命名，然后单击地图**重命名**。</span><span class="sxs-lookup"><span data-stu-id="c437b-121">In Solution Explorer, right-click the map that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="c437b-122">在出现在解决方案资源管理器中的映射的位置编辑框中，键入新名称的地图或改变其现有的名称，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c437b-122">In the editing box that appears in the location of the map in Solution Explorer, type the new name for the map, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c437b-123">你可能还想要更改**类型名称**映射时将其重命名。</span><span class="sxs-lookup"><span data-stu-id="c437b-123">You may also want to change the **Type Name** of the map when you rename it.</span></span> <span data-ttu-id="c437b-124">你更改**类型名称**通过选择**映射**在解决方案资源管理器并输入中的新名称**类型名称**属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="c437b-124">You change the **Type Name** by selecting the **map** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
#### <a name="to-close-a-map"></a><span data-ttu-id="c437b-125">若要关闭映射</span><span class="sxs-lookup"><span data-stu-id="c437b-125">To close a map</span></span>  
  
1.  <span data-ttu-id="c437b-126">在解决方案资源管理器，选择你想要关闭的映射。</span><span class="sxs-lookup"><span data-stu-id="c437b-126">In Solution Explorer, select the map you want to close.</span></span>  
  
2.  <span data-ttu-id="c437b-127">在 **“文件”** 菜单上，单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="c437b-127">On the **File** menu, click **Close**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c437b-128">您也可以单击关闭图标 ([**x**]) 的 Microsoft 右上角[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="c437b-128">You can also click the close icon ([**x**]) in the upper-right corner of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c437b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c437b-129">See Also</span></span>  
 [<span data-ttu-id="c437b-130">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="c437b-130">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)