---
title: 如何测试组件接口 |Microsoft Docs
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
ms.openlocfilehash: d8450177cd97d7136d8ee4146ff93fceee20b351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333859"
---
# <a name="how-to-test-component-interfaces"></a><span data-ttu-id="188b5-102">如何测试组件接口</span><span class="sxs-lookup"><span data-stu-id="188b5-102">How to Test Component Interfaces</span></span>
<span data-ttu-id="188b5-103">适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用 PeopleSoft 元数据和组件接口;因此，它可以处理新的或已修改的组件接口。</span><span class="sxs-lookup"><span data-stu-id="188b5-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft metadata and component interfaces; therefore, it can handle new or modified component interfaces.</span></span> <span data-ttu-id="188b5-104">适配器组件接口中进行任何假设，只不过逻辑并且有效。</span><span class="sxs-lookup"><span data-stu-id="188b5-104">The adapter makes no assumptions about component interfaces except that they are logical and valid.</span></span> <span data-ttu-id="188b5-105">因此，每个组件接口必须为适配器作为源使用之前进行测试。</span><span class="sxs-lookup"><span data-stu-id="188b5-105">Therefore, each component interface must be tested before it is used as a source for the adapter.</span></span>  
  
 <span data-ttu-id="188b5-106">如果由用户或 peoplesoft 软件升级，对基础应用程序进行更改，并且所做的更改使之无效的组件接口，用户必须首先修复无效的组件接口之前，适配器将使用它。</span><span class="sxs-lookup"><span data-stu-id="188b5-106">If changes are made to the underlying application by the user or by a PeopleSoft upgrade, and the changes invalidate a component interface, the user must repair the invalid component interface before the adapter uses it.</span></span>  
  
### <a name="to-test-a-component-interface"></a><span data-ttu-id="188b5-107">若要测试组件接口</span><span class="sxs-lookup"><span data-stu-id="188b5-107">To test a component interface</span></span>  
  
1.  <span data-ttu-id="188b5-108">在应用程序设计器上**工具**菜单上，单击**测试组件接口**。</span><span class="sxs-lookup"><span data-stu-id="188b5-108">In Application Designer, on the **Tools** menu, click **Test Component Interface**.</span></span>  
  
     <span data-ttu-id="188b5-109">![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")</span><span class="sxs-lookup"><span data-stu-id="188b5-109">![](../core/media/psadapter-54-ps-testcompinterface1.gif "PSAdapter_54_PS_TestCompInterface1")</span></span>  
  
2.  <span data-ttu-id="188b5-110">在中**Component Interface Tester**对话框框中，通过使用以下方法之一测试组件接口。</span><span class="sxs-lookup"><span data-stu-id="188b5-110">In the **Component Interface Tester** dialog box, test the component interface by using one the following methods.</span></span> <span data-ttu-id="188b5-111">完成更改后，右键单击窗格顶部的项目。</span><span class="sxs-lookup"><span data-stu-id="188b5-111">After you finish making changes, right-click the top item in the pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="188b5-112">如果需要，单击对话框中，将其置于前台。</span><span class="sxs-lookup"><span data-stu-id="188b5-112">If required, click the dialog box to bring it to the foreground.</span></span>  
  
    -   <span data-ttu-id="188b5-113">若要测试组件接口使用 Find 方法，请单击**查找**。</span><span class="sxs-lookup"><span data-stu-id="188b5-113">To test the component interface using the Find method, click **Find**.</span></span>  
  
         <span data-ttu-id="188b5-114">**Component Interface Tester-查找结果**对话框将打开，显示针对该底层组件的所有可能的项。</span><span class="sxs-lookup"><span data-stu-id="188b5-114">The **Component Interface Tester - Find Results** dialog box opens, displaying all the possible entries for the underlying component.</span></span> <span data-ttu-id="188b5-115">如果有 300 多个项，会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="188b5-115">If there are more than 300 entries, a message appears.</span></span>  
  
         <span data-ttu-id="188b5-116">a.</span><span class="sxs-lookup"><span data-stu-id="188b5-116">a.</span></span> <span data-ttu-id="188b5-117">在左窗格中**查找结果**对话框中，选择一个字段。</span><span class="sxs-lookup"><span data-stu-id="188b5-117">In the left pane of the **Find Results** dialog box, select a field.</span></span>  
  
         <span data-ttu-id="188b5-118">b.</span><span class="sxs-lookup"><span data-stu-id="188b5-118">b.</span></span> <span data-ttu-id="188b5-119">若要显示该特定字段的相关数据，请单击**获取的所选**。</span><span class="sxs-lookup"><span data-stu-id="188b5-119">To display the relevant data for that particular field, click **Get Selected**.</span></span>  
  
         <span data-ttu-id="188b5-120">出现以下屏幕。</span><span class="sxs-lookup"><span data-stu-id="188b5-120">The following screen appears.</span></span>  
  
         <span data-ttu-id="188b5-121">![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")</span><span class="sxs-lookup"><span data-stu-id="188b5-121">![](../core/media/psadapter-55-ps-testcompinterface2.gif "PSAdapter_55_PS_TestCompInterface2")</span></span>  
  
         <span data-ttu-id="188b5-122">如果安全设置允许，可以更改中的每个字段的值。</span><span class="sxs-lookup"><span data-stu-id="188b5-122">If the security settings allow, you can change the values in the individual fields.</span></span>  
  
         <span data-ttu-id="188b5-123">此时将打开以下对话框。</span><span class="sxs-lookup"><span data-stu-id="188b5-123">The following dialog box opens.</span></span>  
  
         <span data-ttu-id="188b5-124">![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")</span><span class="sxs-lookup"><span data-stu-id="188b5-124">![](../core/media/psadapter-56-ps-testcompinterface3.gif "PSAdapter_56_PS_TestCompInterface3")</span></span>  
  
    -   <span data-ttu-id="188b5-125">若要测试组件接口使用`Get`方法：</span><span class="sxs-lookup"><span data-stu-id="188b5-125">To test the component interface using the `Get` method:</span></span>  
  
         <span data-ttu-id="188b5-126">a.</span><span class="sxs-lookup"><span data-stu-id="188b5-126">a.</span></span> <span data-ttu-id="188b5-127">输入现有键。</span><span class="sxs-lookup"><span data-stu-id="188b5-127">Enter the existing key(s).</span></span>  
  
         <span data-ttu-id="188b5-128">b.</span><span class="sxs-lookup"><span data-stu-id="188b5-128">b.</span></span> <span data-ttu-id="188b5-129">单击**获取现有**。</span><span class="sxs-lookup"><span data-stu-id="188b5-129">Click **Get Existing**.</span></span>  
  
         <span data-ttu-id="188b5-130">这会返回您输入的密钥的公开的属性。</span><span class="sxs-lookup"><span data-stu-id="188b5-130">This returns the exposed properties for the key that you entered.</span></span>  
  
         <span data-ttu-id="188b5-131">您可以更改值，如果**更新访问**指定。</span><span class="sxs-lookup"><span data-stu-id="188b5-131">You can change values if **Update access** was specified.</span></span>  
  
         <span data-ttu-id="188b5-132">或者，您可以使用测试`Create`方法。</span><span class="sxs-lookup"><span data-stu-id="188b5-132">Alternatively, you can test using the `Create` method.</span></span>  
  
         <span data-ttu-id="188b5-133">![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")</span><span class="sxs-lookup"><span data-stu-id="188b5-133">![](../core/media/psadapter-57-ps-testcompinterface4.gif "PSAdapter_57_PS_TestCompInterface4")</span></span>  
  
    -   <span data-ttu-id="188b5-134">若要测试组件接口使用`Create`方法：</span><span class="sxs-lookup"><span data-stu-id="188b5-134">To test the component interface using the `Create` method:</span></span>  
  
         <span data-ttu-id="188b5-135">a.</span><span class="sxs-lookup"><span data-stu-id="188b5-135">a.</span></span> <span data-ttu-id="188b5-136">输入所有所需的密钥值。</span><span class="sxs-lookup"><span data-stu-id="188b5-136">Enter all required key values.</span></span>  
  
         <span data-ttu-id="188b5-137">b.</span><span class="sxs-lookup"><span data-stu-id="188b5-137">b.</span></span> <span data-ttu-id="188b5-138">单击**创建新的**。</span><span class="sxs-lookup"><span data-stu-id="188b5-138">Click **Create New**.</span></span>  
  
         <span data-ttu-id="188b5-139">当输入中的有效值**创建密钥**，完成对默认数据扩展表名称后，将打开显示 JOBCODE 数据的窗格。</span><span class="sxs-lookup"><span data-stu-id="188b5-139">When you enter valid values in **Create keys**, a pane that displays the JOBCODE data opens after the Table name is expanded with default data in place.</span></span>  
  
         <span data-ttu-id="188b5-140">可以现在更改字段。</span><span class="sxs-lookup"><span data-stu-id="188b5-140">You can change fields now.</span></span>  
  
         <span data-ttu-id="188b5-141">![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")</span><span class="sxs-lookup"><span data-stu-id="188b5-141">![](../core/media/psadapter-58-ps-testcompinterface5.gif "PSAdapter_58_PS_TestCompInterface5")</span></span>  
  
         <span data-ttu-id="188b5-142">更改针对组件的基础业务逻辑对进行验证。</span><span class="sxs-lookup"><span data-stu-id="188b5-142">Changes are validated against the component's underlying business logic.</span></span>  
  
3.  <span data-ttu-id="188b5-143">若要保存所做的更改，请单击**保存**图标。</span><span class="sxs-lookup"><span data-stu-id="188b5-143">To save your changes, click the **Save** icon.</span></span>  
  
     <span data-ttu-id="188b5-144">用于创建记录的密钥可以用于查看数据的 Get 方法。</span><span class="sxs-lookup"><span data-stu-id="188b5-144">The keys used to create the record can be used with the Get method for viewing data.</span></span> <span data-ttu-id="188b5-145">可以在 PeopleSoft Component 中查看已添加的数据，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="188b5-145">The data that was added can be viewed in the PeopleSoft Component as shown in the following example.</span></span>  
  
     <span data-ttu-id="188b5-146">![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")</span><span class="sxs-lookup"><span data-stu-id="188b5-146">![](../core/media/psadapter-59-ps-testcompinterface6.gif "PSAdapter_59_PS_TestCompInterface6")</span></span>  
  
     <span data-ttu-id="188b5-147">**生效日期**是默认值之一。</span><span class="sxs-lookup"><span data-stu-id="188b5-147">**Effective Date** is one of the default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="188b5-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="188b5-148">See Also</span></span>  
 <span data-ttu-id="188b5-149">[附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md) </span><span class="sxs-lookup"><span data-stu-id="188b5-149">[Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md) </span></span>  
 [<span data-ttu-id="188b5-150">附录 c:使用组件接口</span><span class="sxs-lookup"><span data-stu-id="188b5-150">Appendix C: Using Component Interfaces</span></span>](../core/appendix-c-using-component-interfaces.md)