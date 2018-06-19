---
title: 如何添加现有映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbeaea05-016e-488c-90f3-af8c6b9a3d84
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a61fb0faf5f4eed614257361b00cea781db2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247453"
---
# <a name="how-to-add-existing-maps"></a><span data-ttu-id="fb696-102">如何添加现有的映射</span><span class="sxs-lookup"><span data-stu-id="fb696-102">How to Add Existing Maps</span></span>
<span data-ttu-id="fb696-103">有时，您可能希望向 BizTalk 项目添加现有映射。</span><span class="sxs-lookup"><span data-stu-id="fb696-103">There may be times when you want to add an existing map to a BizTalk project.</span></span> <span data-ttu-id="fb696-104">在进行此操作之前，必须确保映射的源架构和目标架构都包含在要向其添加映射的 BizTalk 项目中，或均由相应的 .NET 程序集引用。</span><span class="sxs-lookup"><span data-stu-id="fb696-104">Before doing so, you must ensure that the source and destination schemas of the map are included in the BizTalk project to which you are adding the map; or, referenced by the corresponding .NET assembly.</span></span>  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a><span data-ttu-id="fb696-105">向 BizTalk 项目添加现有映射</span><span class="sxs-lookup"><span data-stu-id="fb696-105">To add an existing map to a BizTalk project</span></span>  
  
1.  <span data-ttu-id="fb696-106">右键单击解决方案资源管理器中的 BizTalk 项目，指向**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="fb696-106">Right-click a BizTalk project in Solution Explorer, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="fb696-107">在**添加现有项**对话框中，浏览到包含要添加，选中它，，然后单击的映射的文件夹**添加**。</span><span class="sxs-lookup"><span data-stu-id="fb696-107">In the **Add Existing Item** dialog box, browse to the folder containing the map to be added, select it, and then click **Add**.</span></span>  
  
     <span data-ttu-id="fb696-108">在 BizTalk 映射程序中打开代码图。</span><span class="sxs-lookup"><span data-stu-id="fb696-108">The map opens in BizTalk Mapper.</span></span> <span data-ttu-id="fb696-109">新添加的映射也会在解决方案资源管理器中显示为当前 BizTalk 项目的子项。</span><span class="sxs-lookup"><span data-stu-id="fb696-109">The newly added map also appears as a child of the current BizTalk project in Solution Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb696-110">如果您浏览到的文件夹不是 BizTalk 项目文件夹，而在项目文件夹中创建了所添加映射的副本，并且添加到项目中的正是此映射副本，</span><span class="sxs-lookup"><span data-stu-id="fb696-110">If you browsed to a folder other than the BizTalk project folder, a copy of the map you added was created in the project folder, and it was this copy of the map that was added to the project.</span></span> <span data-ttu-id="fb696-111">那么，对该映射进行的后续更改将保存在这个副本中，而不会保存在另一文件夹下的原始映射中。</span><span class="sxs-lookup"><span data-stu-id="fb696-111">Subsequent changes to the map are made to this copy, not to the original map in the other folder.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="fb696-112">BizTalk 映射只能通过 BizTalk 映射器打开，该映射器的宿主是 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 外壳程序。</span><span class="sxs-lookup"><span data-stu-id="fb696-112">BizTalk maps can only be opened by BizTalk Mapper, which is hosted within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="fb696-113">如果您在 Windows 资源管理器中双击某个映射，并且已经正确加载了相应的架构，则会先打开一个新 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 实例，然后 BizTalk 映射器再打开该映射。</span><span class="sxs-lookup"><span data-stu-id="fb696-113">If you double-click a map in Windows Explorer, a new instance of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] will be opened, and then the map will be opened by BizTalk Mapper, provided the corresponding schemas are loaded properly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fb696-114">如果现有映射中包含自定义 functoid，则必须将相应 DLL 复制到文件夹“%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”。</span><span class="sxs-lookup"><span data-stu-id="fb696-114">If the existing map contains custom functoids, then the corresponding DLLs must be copied to the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span> <span data-ttu-id="fb696-115">否则，映射将不会加载，并且会引发错误，因为加载自定义 functoid 失败。</span><span class="sxs-lookup"><span data-stu-id="fb696-115">Else, the map will not load and throws an error because of failure to load custom functoids.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb696-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb696-116">See Also</span></span>  
 <span data-ttu-id="fb696-117">[管理项目中的映射](../core/managing-maps-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="fb696-117">[Managing Maps Within Projects](../core/managing-maps-within-projects.md) </span></span>  
 [<span data-ttu-id="fb696-118">开发自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="fb696-118">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)