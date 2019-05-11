---
title: 如何添加现有映射 |Microsoft Docs
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
ms.openlocfilehash: 4a566a76d1d42d099e1825af7d6774644bb9049d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387293"
---
# <a name="how-to-add-existing-maps"></a><span data-ttu-id="43533-102">如何添加现有映射</span><span class="sxs-lookup"><span data-stu-id="43533-102">How to Add Existing Maps</span></span>
<span data-ttu-id="43533-103">可能存在你想要将现有的映射添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="43533-103">There may be times when you want to add an existing map to a BizTalk project.</span></span> <span data-ttu-id="43533-104">这样做之前必须确保映射的源和目标架构都包含向其中添加映射中，则在 BizTalk 项目中或者，通过相应的.NET 程序集引用。</span><span class="sxs-lookup"><span data-stu-id="43533-104">Before doing so, you must ensure that the source and destination schemas of the map are included in the BizTalk project to which you are adding the map; or, referenced by the corresponding .NET assembly.</span></span>  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a><span data-ttu-id="43533-105">若要将现有的映射添加到 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="43533-105">To add an existing map to a BizTalk project</span></span>  
  
1. <span data-ttu-id="43533-106">右键单击解决方案资源管理器中的 BizTalk 项目，指向**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="43533-106">Right-click a BizTalk project in Solution Explorer, point to **Add**, and then click **Existing Item**.</span></span>  
  
2. <span data-ttu-id="43533-107">在中**添加现有项**对话框中，浏览到包含要添加、 选择它，然后单击该映射的文件夹**添加**。</span><span class="sxs-lookup"><span data-stu-id="43533-107">In the **Add Existing Item** dialog box, browse to the folder containing the map to be added, select it, and then click **Add**.</span></span>  
  
    <span data-ttu-id="43533-108">在 BizTalk 映射器中打开该映射。</span><span class="sxs-lookup"><span data-stu-id="43533-108">The map opens in BizTalk Mapper.</span></span> <span data-ttu-id="43533-109">在解决方案资源管理器中的当前 BizTalk 项目的小孩也会出现新添加的映射。</span><span class="sxs-lookup"><span data-stu-id="43533-109">The newly added map also appears as a child of the current BizTalk project in Solution Explorer.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="43533-110">如果浏览到的文件夹不是 BizTalk 项目文件夹，在项目文件夹中，创建一份所添加的映射，并已添加到项目的映射此副本。</span><span class="sxs-lookup"><span data-stu-id="43533-110">If you browsed to a folder other than the BizTalk project folder, a copy of the map you added was created in the project folder, and it was this copy of the map that was added to the project.</span></span> <span data-ttu-id="43533-111">对此副本，不到其他文件夹中的原始映射进行映射的后续更改。</span><span class="sxs-lookup"><span data-stu-id="43533-111">Subsequent changes to the map are made to this copy, not to the original map in the other folder.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="43533-112">BizTalk 映射只能通过 BizTalk 映射器，托管在 Microsoft 内打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。</span><span class="sxs-lookup"><span data-stu-id="43533-112">BizTalk maps can only be opened by BizTalk Mapper, which is hosted within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="43533-113">如果您双击 Windows 资源管理器的新实例中某个映射[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]将打开，然后该映射将会打开 BizTalk 映射器提供了相应的架构已正确加载。</span><span class="sxs-lookup"><span data-stu-id="43533-113">If you double-click a map in Windows Explorer, a new instance of [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] will be opened, and then the map will be opened by BizTalk Mapper, provided the corresponding schemas are loaded properly.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="43533-114">如果现有映射中包含自定义 functoid，然后在负载测试相应的 Dll 必须将复制到文件夹"%BTSINSTALLPATH%\Developer Tools\Mapper Extensions"。</span><span class="sxs-lookup"><span data-stu-id="43533-114">If the existing map contains custom functoids, then the corresponding DLLs must be copied to the folder “%BTSINSTALLPATH%\Developer Tools\Mapper Extensions”.</span></span> <span data-ttu-id="43533-115">否则，映射将不会加载和由于加载自定义 functoid 失败将引发错误。</span><span class="sxs-lookup"><span data-stu-id="43533-115">Else, the map will not load and throws an error because of failure to load custom functoids.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43533-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="43533-116">See Also</span></span>  
 <span data-ttu-id="43533-117">[管理项目中的映射](../core/managing-maps-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="43533-117">[Managing Maps Within Projects](../core/managing-maps-within-projects.md) </span></span>  
 [<span data-ttu-id="43533-118">开发自定义 Functoid</span><span class="sxs-lookup"><span data-stu-id="43533-118">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)