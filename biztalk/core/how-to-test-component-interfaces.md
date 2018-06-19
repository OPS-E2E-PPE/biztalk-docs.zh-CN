---
title: 如何测试组件接口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing component interfaces
- component interfaces, testing
ms.assetid: d637f76d-170d-4543-a2b2-a4ac4001386b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be50521e5c4421d8ac8902bcf7a414d734c3b9f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256565"
---
# <a name="how-to-test-component-interfaces"></a><span data-ttu-id="5dfa2-102">如何测试组件接口</span><span class="sxs-lookup"><span data-stu-id="5dfa2-102">How to Test Component Interfaces</span></span>
<span data-ttu-id="5dfa2-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise 使用 PeopleSoft 元数据和组件接口；因此，它可以处理新增或改进过的组件接口。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft metadata and component interfaces; therefore, it can handle new or modified component interfaces.</span></span> <span data-ttu-id="5dfa2-104">除假设组件接口符合逻辑并且有效之外，该适配器不对组件接口进行任何其他假设。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-104">The adapter makes no assumptions about component interfaces except that they are logical and valid.</span></span> <span data-ttu-id="5dfa2-105">因此，每个组件接口在用作适配器的来源之前都必须进行测试。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-105">Therefore, each component interface must be tested before it is used as a source for the adapter.</span></span>  
  
 <span data-ttu-id="5dfa2-106">如果用户或 PeopleSoft 软件升级对底层应用程序进行了任何更改，并且这些更改使得某个组件接口变为无效，那么在适配器使用组件接口之前，用户必须首先修复无效的接口。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-106">If changes are made to the underlying application by the user or by a PeopleSoft upgrade, and the changes invalidate a component interface, the user must repair the invalid component interface before the adapter uses it.</span></span>  
  
### <a name="to-test-a-component-interface"></a><span data-ttu-id="5dfa2-107">测试组件接口</span><span class="sxs-lookup"><span data-stu-id="5dfa2-107">To test a component interface</span></span>  
  
1.  <span data-ttu-id="5dfa2-108">在应用程序设计器上**工具**菜单上，单击**测试组件接口**。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-108">In Application Designer, on the **Tools** menu, click **Test Component Interface**.</span></span>  
  
     ![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")  
  
2.  <span data-ttu-id="5dfa2-109">在**组件接口测试人员**对话框框中，通过使用以下方法之一来测试该组件接口。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-109">In the **Component Interface Tester** dialog box, test the component interface by using one the following methods.</span></span> <span data-ttu-id="5dfa2-110">在您完成更改工作之后，请右键单击窗格中最顶部的一项。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-110">After you finish making changes, right-click the top item in the pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5dfa2-111">如果需要，请单击对话框使其成为前台窗口。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-111">If required, click the dialog box to bring it to the foreground.</span></span>  
  
    -   <span data-ttu-id="5dfa2-112">若要测试使用查找方法该组件接口，请单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-112">To test the component interface using the Find method, click **Find**.</span></span>  
  
         <span data-ttu-id="5dfa2-113">**组件接口测试器-查找结果**对话框随即打开，显示基础组件的可能的所有项。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-113">The **Component Interface Tester - Find Results** dialog box opens, displaying all the possible entries for the underlying component.</span></span> <span data-ttu-id="5dfa2-114">如果项数超过 300，会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-114">If there are more than 300 entries, a message appears.</span></span>  
  
         <span data-ttu-id="5dfa2-115">a.</span><span class="sxs-lookup"><span data-stu-id="5dfa2-115">a.</span></span> <span data-ttu-id="5dfa2-116">在左窗格中**查找结果**对话框中，选择一个字段。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-116">In the left pane of the **Find Results** dialog box, select a field.</span></span>  
  
         <span data-ttu-id="5dfa2-117">b.</span><span class="sxs-lookup"><span data-stu-id="5dfa2-117">b.</span></span> <span data-ttu-id="5dfa2-118">若要显示该特定字段的相关数据，请单击**获取的所选**。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-118">To display the relevant data for that particular field, click **Get Selected**.</span></span>  
  
         <span data-ttu-id="5dfa2-119">将出现以下屏幕。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-119">The following screen appears.</span></span>  
  
         ![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")  
  
         <span data-ttu-id="5dfa2-120">如果安全设置允许，可以更改各个字段中的值。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-120">If the security settings allow, you can change the values in the individual fields.</span></span>  
  
         <span data-ttu-id="5dfa2-121">将打开以下对话框。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-121">The following dialog box opens.</span></span>  
  
         ![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")  
  
    -   <span data-ttu-id="5dfa2-122">若要测试组件接口使用`Get`方法：</span><span class="sxs-lookup"><span data-stu-id="5dfa2-122">To test the component interface using the `Get` method:</span></span>  
  
         <span data-ttu-id="5dfa2-123">a.</span><span class="sxs-lookup"><span data-stu-id="5dfa2-123">a.</span></span> <span data-ttu-id="5dfa2-124">输入现有密钥。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-124">Enter the existing key(s).</span></span>  
  
         <span data-ttu-id="5dfa2-125">b.</span><span class="sxs-lookup"><span data-stu-id="5dfa2-125">b.</span></span> <span data-ttu-id="5dfa2-126">单击**获取现有**。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-126">Click **Get Existing**.</span></span>  
  
         <span data-ttu-id="5dfa2-127">这会返回您输入的键的已公开属性。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-127">This returns the exposed properties for the key that you entered.</span></span>  
  
         <span data-ttu-id="5dfa2-128">你可以更改值，如果**更新访问权限**指定。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-128">You can change values if **Update access** was specified.</span></span>  
  
         <span data-ttu-id="5dfa2-129">或者，你可以测试使用`Create`方法。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-129">Alternatively, you can test using the `Create` method.</span></span>  
  
         ![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")  
  
    -   <span data-ttu-id="5dfa2-130">若要测试组件接口使用`Create`方法：</span><span class="sxs-lookup"><span data-stu-id="5dfa2-130">To test the component interface using the `Create` method:</span></span>  
  
         <span data-ttu-id="5dfa2-131">a.</span><span class="sxs-lookup"><span data-stu-id="5dfa2-131">a.</span></span> <span data-ttu-id="5dfa2-132">输入所有所需的密钥值。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-132">Enter all required key values.</span></span>  
  
         <span data-ttu-id="5dfa2-133">b.</span><span class="sxs-lookup"><span data-stu-id="5dfa2-133">b.</span></span> <span data-ttu-id="5dfa2-134">单击**创建新**。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-134">Click **Create New**.</span></span>  
  
         <span data-ttu-id="5dfa2-135">在输入中的有效值**创建密钥**，与默认数据就地展开表名后，此时将打开显示 JOBCODE 数据窗格。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-135">When you enter valid values in **Create keys**, a pane that displays the JOBCODE data opens after the Table name is expanded with default data in place.</span></span>  
  
         <span data-ttu-id="5dfa2-136">现在，可以更改字段。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-136">You can change fields now.</span></span>  
  
         ![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")  
  
         <span data-ttu-id="5dfa2-137">将针对组件的底层业务逻辑对更改进行验证。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-137">Changes are validated against the component's underlying business logic.</span></span>  
  
3.  <span data-ttu-id="5dfa2-138">若要保存所做的更改，请单击**保存**图标。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-138">To save your changes, click the **Save** icon.</span></span>  
  
     <span data-ttu-id="5dfa2-139">用来创建记录的键可以与 Get 方法一起使用以查看数据。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-139">The keys used to create the record can be used with the Get method for viewing data.</span></span> <span data-ttu-id="5dfa2-140">可以在 PeopleSoft Component 中查看添加的数据，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-140">The data that was added can be viewed in the PeopleSoft Component as shown in the following example.</span></span>  
  
     ![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")  
  
     <span data-ttu-id="5dfa2-141">**生效日期**是默认值之一。</span><span class="sxs-lookup"><span data-stu-id="5dfa2-141">**Effective Date** is one of the default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dfa2-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dfa2-142">See Also</span></span>  
 <span data-ttu-id="5dfa2-143">[附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="5dfa2-143">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="5dfa2-144">附录 c： 使用组件接口</span><span class="sxs-lookup"><span data-stu-id="5dfa2-144">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)