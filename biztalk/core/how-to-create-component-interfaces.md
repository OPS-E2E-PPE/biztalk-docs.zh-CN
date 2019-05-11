---
title: 如何创建组件接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating component interfaces
- component interfaces, creating
ms.assetid: 9def053a-cbf6-4b34-b2e8-b2d03bffc5fe
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 778f9b59db2712fffb50d5e83e55155386ed81d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339446"
---
# <a name="how-to-create-component-interfaces"></a><span data-ttu-id="a733d-102">如何创建组件接口</span><span class="sxs-lookup"><span data-stu-id="a733d-102">How to Create Component Interfaces</span></span>
<span data-ttu-id="a733d-103">创建使用 PeopleSoft 应用程序设计器的组件接口。</span><span class="sxs-lookup"><span data-stu-id="a733d-103">You create component interfaces using the PeopleSoft Application Designer.</span></span> <span data-ttu-id="a733d-104">（有关应用程序设计器的详细信息，请参阅 PeopleSoft Enterprise 文档）。</span><span class="sxs-lookup"><span data-stu-id="a733d-104">(For more information about Application Designer, see the PeopleSoft Enterprise documentation.)</span></span>  
  
 <span data-ttu-id="a733d-105">您可以从组件视图中的记录添加属性。</span><span class="sxs-lookup"><span data-stu-id="a733d-105">You can add properties from the records in the component view.</span></span> <span data-ttu-id="a733d-106">在组件接口中，可以删除不希望公开的属性。</span><span class="sxs-lookup"><span data-stu-id="a733d-106">In the component interface, you can delete a property that you do not want to expose.</span></span> <span data-ttu-id="a733d-107">您可以通过单击属性，然后再次单击，直到您可以键入新名称重命名属性。</span><span class="sxs-lookup"><span data-stu-id="a733d-107">You can rename properties by clicking the property and then clicking again until you can type a new name.</span></span> <span data-ttu-id="a733d-108">如果您重命名属性，则可以引用其组件接口中只按新名称，而不是基础的组件名称。</span><span class="sxs-lookup"><span data-stu-id="a733d-108">If you rename a property, you can reference it in the component interface only by the new name, not by the underlying component name.</span></span>  
  
 <span data-ttu-id="a733d-109">属性可能有各种图标旁边。</span><span class="sxs-lookup"><span data-stu-id="a733d-109">Properties may have various icons adjacent to them.</span></span> <span data-ttu-id="a733d-110">例如，EMPLID 有一个图标指示它是来自底层记录的键字段。</span><span class="sxs-lookup"><span data-stu-id="a733d-110">For example, EMPLID has an icon that indicates that it is a key field from the underlying record.</span></span> <span data-ttu-id="a733d-111">名称有一个图标指示它是来自底层记录的备用键字段。</span><span class="sxs-lookup"><span data-stu-id="a733d-111">NAME has an icon that indicates that it is an alternate key field from the underlying record.</span></span> <span data-ttu-id="a733d-112">（有关属性图标的完整列表，请参阅 PeopleBooks 文档）。</span><span class="sxs-lookup"><span data-stu-id="a733d-112">(For a complete list of property icons, see the PeopleBooks documentation.)</span></span>  
  
### <a name="creating-a-new-component-interface"></a><span data-ttu-id="a733d-113">创建一个新组件接口</span><span class="sxs-lookup"><span data-stu-id="a733d-113">Creating a new component interface</span></span>  
  
1.  <span data-ttu-id="a733d-114">打开 PeopleSoft 应用程序设计器。</span><span class="sxs-lookup"><span data-stu-id="a733d-114">Open the PeopleSoft Application Designer.</span></span>  
  
2.  <span data-ttu-id="a733d-115">在“文件”  菜单上，单击“新建” 。</span><span class="sxs-lookup"><span data-stu-id="a733d-115">On the **File** menu, click **New**.</span></span>  
  
     <span data-ttu-id="a733d-116">![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")</span><span class="sxs-lookup"><span data-stu-id="a733d-116">![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")</span></span>  
  
3.  <span data-ttu-id="a733d-117">在中**新建**对话框中，选择**组件接口**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a733d-117">In the **New** dialog box, select **Component Interface**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="a733d-118">![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")</span><span class="sxs-lookup"><span data-stu-id="a733d-118">![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")</span></span>  
  
4.  <span data-ttu-id="a733d-119">在中**选择组件接口的源组件**窗口中，选择要用作基础组件接口，然后依次**选择**。</span><span class="sxs-lookup"><span data-stu-id="a733d-119">In the **Select Source Component for Component Interface** window, select the component to use as a basis for the component interface, and then click **Select**.</span></span>  
  
     <span data-ttu-id="a733d-120">![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")</span><span class="sxs-lookup"><span data-stu-id="a733d-120">![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a733d-121">如果组件接口很大，请手动公开组件属性。</span><span class="sxs-lookup"><span data-stu-id="a733d-121">If the component interface is large, expose the component properties manually.</span></span>  
  
5.  <span data-ttu-id="a733d-122">在中**应用程序设计器**对话框框中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="a733d-122">In the **Application Designer** dialog box, choose one of the following options:</span></span>  
  
    -   <span data-ttu-id="a733d-123">单击**否**创建组件接口而不显示属性并手动公开组件属性。</span><span class="sxs-lookup"><span data-stu-id="a733d-123">Click **No** to create the component interface without displaying properties and to expose component properties manually.</span></span>  
  
         <span data-ttu-id="a733d-124">a.</span><span class="sxs-lookup"><span data-stu-id="a733d-124">a.</span></span> <span data-ttu-id="a733d-125">将相关字段从左窗格中拖至右窗格中。</span><span class="sxs-lookup"><span data-stu-id="a733d-125">Drag the relevant fields from the left pane to the right pane.</span></span>  
  
         <span data-ttu-id="a733d-126">b.</span><span class="sxs-lookup"><span data-stu-id="a733d-126">b.</span></span> <span data-ttu-id="a733d-127">若要选择要执行的各种函数，右键单击是右侧或左侧窗格中，根据哪些窗格处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a733d-127">To select various functions to perform, right-click either the right or left pane, depending on which pane is active.</span></span>  
  
         <span data-ttu-id="a733d-128">有关函数的完整列表，请参阅 PeopleBooks 文档。</span><span class="sxs-lookup"><span data-stu-id="a733d-128">For a complete list of functions, see the PeopleBooks documentation.</span></span>  
  
    -   <span data-ttu-id="a733d-129">单击**是**创建组件接口并显示底层组件接口的属性。</span><span class="sxs-lookup"><span data-stu-id="a733d-129">Click **Yes** to create the component interface and display the properties of the underlying component interface.</span></span>  
  
         <span data-ttu-id="a733d-130">![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")</span><span class="sxs-lookup"><span data-stu-id="a733d-130">![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a733d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a733d-131">See Also</span></span>  
 <span data-ttu-id="a733d-132">[组件接口中的标准方法](../core/standard-methods-in-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="a733d-132">[Standard Methods in Component Interfaces](../core/standard-methods-in-component-interfaces.md) </span></span>  
 <span data-ttu-id="a733d-133">[附录 c:使用组件接口](../core/appendix-c-using-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="a733d-133">[Appendix C: Using Component Interfaces](../core/appendix-c-using-component-interfaces.md) </span></span>  
 [<span data-ttu-id="a733d-134">附录 a:组件接口方法</span><span class="sxs-lookup"><span data-stu-id="a733d-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)