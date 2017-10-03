---
title: "如何创建组件接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating component interfaces
- component interfaces, creating
ms.assetid: 9def053a-cbf6-4b34-b2e8-b2d03bffc5fe
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86ee68edba66b05d3c2541dd9c41cc074bd790b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-component-interfaces"></a><span data-ttu-id="98387-102">如何创建组件接口</span><span class="sxs-lookup"><span data-stu-id="98387-102">How to Create Component Interfaces</span></span>
<span data-ttu-id="98387-103">您将使用 PeopleSoft 应用程序设计器创建组件接口。</span><span class="sxs-lookup"><span data-stu-id="98387-103">You create component interfaces using the PeopleSoft Application Designer.</span></span> <span data-ttu-id="98387-104">（有关应用程序设计器的详细信息，请参阅 PeopleSoft Enterprise 文档。）</span><span class="sxs-lookup"><span data-stu-id="98387-104">(For more information about Application Designer, see the PeopleSoft Enterprise documentation.)</span></span>  
  
 <span data-ttu-id="98387-105">可以从组件视图中的记录添加属性。</span><span class="sxs-lookup"><span data-stu-id="98387-105">You can add properties from the records in the component view.</span></span> <span data-ttu-id="98387-106">在组件接口中，您可以删除不希望公开的属性。</span><span class="sxs-lookup"><span data-stu-id="98387-106">In the component interface, you can delete a property that you do not want to expose.</span></span> <span data-ttu-id="98387-107">可以通过以下方式重命名属性：单击属性，然后再次单击，直到可以键入新的名称。</span><span class="sxs-lookup"><span data-stu-id="98387-107">You can rename properties by clicking the property and then clicking again until you can type a new name.</span></span> <span data-ttu-id="98387-108">重命名属性后，只需通过新的属性名即可在组件接口中对其进行引用，无需使用底层组件名。</span><span class="sxs-lookup"><span data-stu-id="98387-108">If you rename a property, you can reference it in the component interface only by the new name, not by the underlying component name.</span></span>  
  
 <span data-ttu-id="98387-109">属性旁边可能有各种图标。</span><span class="sxs-lookup"><span data-stu-id="98387-109">Properties may have various icons adjacent to them.</span></span> <span data-ttu-id="98387-110">例如，EMPLID 有一个图标指示它是来自底层记录的键字段。</span><span class="sxs-lookup"><span data-stu-id="98387-110">For example, EMPLID has an icon that indicates that it is a key field from the underlying record.</span></span> <span data-ttu-id="98387-111">NAME 有一个图标指示它是来自底层记录的备用键字段。</span><span class="sxs-lookup"><span data-stu-id="98387-111">NAME has an icon that indicates that it is an alternate key field from the underlying record.</span></span> <span data-ttu-id="98387-112">（有关属性图标的完整列表，请参阅 PeopleBooks 文档。）</span><span class="sxs-lookup"><span data-stu-id="98387-112">(For a complete list of property icons, see the PeopleBooks documentation.)</span></span>  
  
### <a name="creating-a-new-component-interface"></a><span data-ttu-id="98387-113">创建新的组件接口</span><span class="sxs-lookup"><span data-stu-id="98387-113">Creating a new component interface</span></span>  
  
1.  <span data-ttu-id="98387-114">打开 PeopleSoft 应用程序设计器。</span><span class="sxs-lookup"><span data-stu-id="98387-114">Open the PeopleSoft Application Designer.</span></span>  
  
2.  <span data-ttu-id="98387-115">在“文件”  菜单上，单击“新建” 。</span><span class="sxs-lookup"><span data-stu-id="98387-115">On the **File** menu, click **New**.</span></span>  
  
     ![](../core/media/psadapter-42-ps-new-compinterface.gif "PSAdapter_42_PS_New_CompInterface")  
  
3.  <span data-ttu-id="98387-116">在**新建**对话框中，选择**组件接口**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="98387-116">In the **New** dialog box, select **Component Interface**, and then click **OK**.</span></span>  
  
     ![](../core/media/psadapter-43-ps-selectsourcecomp.gif "PSAdapter_43_PS_SelectSourceComp")  
  
4.  <span data-ttu-id="98387-117">在**组件接口选择源组件**窗口中，选择要用作基础组件接口，然后单击的组件**选择**。</span><span class="sxs-lookup"><span data-stu-id="98387-117">In the **Select Source Component for Component Interface** window, select the component to use as a basis for the component interface, and then click **Select**.</span></span>  
  
     ![](../core/media/psadapter-44-ps-appdesigner1.gif "PSAdapter_44_PS_AppDesigner1")  
  
    > [!NOTE]
    >  <span data-ttu-id="98387-118">如果组件接口很大，请手动公开组件属性。</span><span class="sxs-lookup"><span data-stu-id="98387-118">If the component interface is large, expose the component properties manually.</span></span>  
  
5.  <span data-ttu-id="98387-119">在**应用程序设计器**对话框框中，选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="98387-119">In the **Application Designer** dialog box, choose one of the following options:</span></span>  
  
    -   <span data-ttu-id="98387-120">单击**否**以创建而不显示属性的组件接口并手动公开组件属性。</span><span class="sxs-lookup"><span data-stu-id="98387-120">Click **No** to create the component interface without displaying properties and to expose component properties manually.</span></span>  
  
         <span data-ttu-id="98387-121">a.</span><span class="sxs-lookup"><span data-stu-id="98387-121">a.</span></span> <span data-ttu-id="98387-122">将相关字段从左窗格中拖动到右窗格中。</span><span class="sxs-lookup"><span data-stu-id="98387-122">Drag the relevant fields from the left pane to the right pane.</span></span>  
  
         <span data-ttu-id="98387-123">b.</span><span class="sxs-lookup"><span data-stu-id="98387-123">b.</span></span> <span data-ttu-id="98387-124">若要选择要执行的各种函数，右键单击是右或向左窗格中，根据哪些窗格处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="98387-124">To select various functions to perform, right-click either the right or left pane, depending on which pane is active.</span></span>  
  
         <span data-ttu-id="98387-125">有关完整的功能列表，请参阅 PeopleBooks 文档。</span><span class="sxs-lookup"><span data-stu-id="98387-125">For a complete list of functions, see the PeopleBooks documentation.</span></span>  
  
    -   <span data-ttu-id="98387-126">单击**是**创建组件接口和显示的基础组件接口的属性。</span><span class="sxs-lookup"><span data-stu-id="98387-126">Click **Yes** to create the component interface and display the properties of the underlying component interface.</span></span>  
  
         ![](../core/media/psadapter-45-ps-appdesigner2.gif "PSAdapter_45_PS_AppDesigner2")  
  
## <a name="see-also"></a><span data-ttu-id="98387-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98387-127">See Also</span></span>  
 <span data-ttu-id="98387-128">[组件接口中的标准方法](../core/standard-methods-in-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="98387-128">[Standard Methods in Component Interfaces](../core/standard-methods-in-component-interfaces.md) </span></span>  
 <span data-ttu-id="98387-129">[附录 c： 使用组件接口](../core/appendix-c-using-component-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="98387-129">[Appendix C: Using Component Interfaces](../core/appendix-c-using-component-interfaces.md) </span></span>  
 [<span data-ttu-id="98387-130">附录 a： 组件接口方法</span><span class="sxs-lookup"><span data-stu-id="98387-130">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)