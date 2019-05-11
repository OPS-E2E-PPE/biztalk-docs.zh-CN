---
title: 如何打开、 保存、 关闭和重命名映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5ef0bcaad7dc3cd4bd526657eb86194e2d986e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335819"
---
# <a name="how-to-open-save-close-and-rename-maps"></a><span data-ttu-id="a8f9f-102">如何打开、 保存、 关闭和重命名映射</span><span class="sxs-lookup"><span data-stu-id="a8f9f-102">How to Open, Save, Close, and Rename Maps</span></span>
<span data-ttu-id="a8f9f-103">在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，映射在文件系统中以扩展名为.btm 文件形式存在。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-103">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], maps exist as files in the file system with .btm extensions.</span></span> <span data-ttu-id="a8f9f-104">不过，它是更常见，若要使用映射作为 BizTalk 项目，从其执行操作，如打开、 保存和关闭映射中的项。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-104">Nevertheless, it is much more common to work with maps as items in a BizTalk project, from which you perform operations such as opening, saving, and closing maps.</span></span>  
  
### <a name="to-open-a-map"></a><span data-ttu-id="a8f9f-105">若要打开地图</span><span class="sxs-lookup"><span data-stu-id="a8f9f-105">To open a map</span></span>  
  
1.  <span data-ttu-id="a8f9f-106">在解决方案资源管理器，选择你想要打开的映射。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-106">In Solution Explorer, select the map you want to open.</span></span>  
  
2.  <span data-ttu-id="a8f9f-107">上**视图**菜单上，单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-107">On the **View** menu, click **Open**.</span></span>  
  
     <span data-ttu-id="a8f9f-108">在 BizTalk 映射器中打开该映射。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-108">The map opens in BizTalk Mapper.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a8f9f-109">您可以右键单击解决方案资源管理器中的映射，然后单击**打开**，或者仅双击解决方案资源管理器中的映射。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-109">You can also right-click the map in Solution Explorer, and then click **Open**, or simply double-click the map in Solution Explorer.</span></span>  
  
### <a name="to-save-a-map"></a><span data-ttu-id="a8f9f-110">若要保存映射</span><span class="sxs-lookup"><span data-stu-id="a8f9f-110">To save a map</span></span>  
  
1. <span data-ttu-id="a8f9f-111">在解决方案资源管理器，选择你想要保存的映射。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-111">In Solution Explorer, select the map you want to save.</span></span>  
  
2. <span data-ttu-id="a8f9f-112">上**文件**菜单上，单击 \* \* 保存 *\<名称的映射\>* \* \*。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-112">On the **File** menu, click \*\*Save \*\<Name of Map\>\*\*\*.</span></span>  
  
### <a name="to-save-a-map-to-a-new-location"></a><span data-ttu-id="a8f9f-113">若要将映射保存到新位置</span><span class="sxs-lookup"><span data-stu-id="a8f9f-113">To save a map to a new location</span></span>  
  
1.  <span data-ttu-id="a8f9f-114">在解决方案资源管理器，选择你想要将保存到新位置的映射。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-114">In Solution Explorer, select the map you want to save to a new location.</span></span>  
  
2.  <span data-ttu-id="a8f9f-115">上**文件**菜单上，单击\**保存*\<名称的映射\>\* 作为\*\*。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-115">On the **File** menu, click **Save *\<Name of Map\>* As**.</span></span>  
  
3.  <span data-ttu-id="a8f9f-116">在中**将文件另存为**对话框中，浏览到要保存该映射的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-116">In the **Save File As** dialog box, browse to the folder location where you want to save the map.</span></span>  
  
4.  <span data-ttu-id="a8f9f-117">在中**文件名**框中，键入该文件的名称，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-117">In the **File name** box, type a name for the file, and then click **Save**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a8f9f-118">不要使用以下名称用于映射："XmlContent"、"SourceSchemas"、"TargetSchemas"或者"XsltArgumentListContent"，这样做将导致编译问题在生成C#中相应的.NET 程序集的代码。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-118">Do not use the following names for maps: "XmlContent", "SourceSchemas", "TargetSchemas", or "XsltArgumentListContent"; doing so will cause compilation problems in the generated C# code in the corresponding .NET assembly.</span></span> <span data-ttu-id="a8f9f-119">有关问题及其解决方案的信息，请参阅[故障排除映射](../core/troubleshooting-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-119">For information about issues and their resolution, see [Troubleshooting Maps](../core/troubleshooting-maps.md).</span></span>  
  
### <a name="to-rename-a-map"></a><span data-ttu-id="a8f9f-120">若要重命名映射</span><span class="sxs-lookup"><span data-stu-id="a8f9f-120">To rename a map</span></span>  
  
1.  <span data-ttu-id="a8f9f-121">在解决方案资源管理器，右键单击你想要重命名，然后单击该地图**重命名**。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-121">In Solution Explorer, right-click the map that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="a8f9f-122">中将出现在解决方案资源管理器中的映射的位置的编辑框，键入新名称的地图或更改其现有的名称，，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-122">In the editing box that appears in the location of the map in Solution Explorer, type the new name for the map, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8f9f-123">您可能还需要更改**类型名称**映射时，其重命名。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-123">You may also want to change the **Type Name** of the map when you rename it.</span></span> <span data-ttu-id="a8f9f-124">您更改**类型名称**通过选择**地图**中的解决方案资源管理器并输入中的新名称**类型名称**属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-124">You change the **Type Name** by selecting the **map** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
#### <a name="to-close-a-map"></a><span data-ttu-id="a8f9f-125">若要关闭映射</span><span class="sxs-lookup"><span data-stu-id="a8f9f-125">To close a map</span></span>  
  
1. <span data-ttu-id="a8f9f-126">在解决方案资源管理器，选择你想要关闭的映射。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-126">In Solution Explorer, select the map you want to close.</span></span>  
  
2. <span data-ttu-id="a8f9f-127">在 **“文件”** 菜单上，单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-127">On the **File** menu, click **Close**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a8f9f-128">此外可以单击关闭图标 ([**x**]) 在 Microsoft 的右上角[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="a8f9f-128">You can also click the close icon ([**x**]) in the upper-right corner of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f9f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8f9f-129">See Also</span></span>  
 [<span data-ttu-id="a8f9f-130">管理项目中的映射</span><span class="sxs-lookup"><span data-stu-id="a8f9f-130">Managing Maps Within Projects</span></span>](../core/managing-maps-within-projects.md)