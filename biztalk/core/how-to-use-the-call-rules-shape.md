---
title: 如何使用调用规则形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6955acfee9052a3b46dcfb70c90ecc95fe216be3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003110"
---
# <a name="how-to-use-the-call-rules-shape"></a><span data-ttu-id="c7ebc-102">如何使用调用规则形状</span><span class="sxs-lookup"><span data-stu-id="c7ebc-102">How to Use the Call Rules Shape</span></span>
<span data-ttu-id="c7ebc-103">在业务流程设计器中，你可以使用**调用规则**形状调用业务策略。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-103">In Orchestration Designer, you can use the **Call Rules** shape to call a business policy.</span></span>  
  
### <a name="to-configure-the-call-rules-shape"></a><span data-ttu-id="c7ebc-104">配置调用规则形状</span><span class="sxs-lookup"><span data-stu-id="c7ebc-104">To configure the Call Rules shape</span></span>  
  
1. <span data-ttu-id="c7ebc-105">从工具箱中**BizTalk 业务流程**选项卡上，拖动**调用规则**形状在业务流程设计图面上的连接线上。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-105">From the Toolbox, in the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
    <span data-ttu-id="c7ebc-106">-或-</span><span class="sxs-lookup"><span data-stu-id="c7ebc-106">—Or—</span></span>  
  
    <span data-ttu-id="c7ebc-107">右键单击连接的线条或形状占位符，你想要添加形状，指向**插入形状**上下文菜单，然后单击**调用规则**。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-107">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape** on the context menu, and then click **Call Rules**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c7ebc-108">在 BizTalk Server 中，不需要具有原子作用域插入**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-108">In BizTalk Server, you do not need to have an atomic scope to insert a **Call Rules** shape.</span></span> <span data-ttu-id="c7ebc-109">可以拖动**调用规则**到业务流程设计图面上形状从工具箱。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-109">You can drag a **Call Rules** shape into the Orchestration Design Surface from the Toolbox.</span></span> <span data-ttu-id="c7ebc-110">但是，在 BizTalk Server 中，**调用规则**上下文菜单中禁用菜单项，如果尝试插入**调用规则**不具有原子作用域的业务流程内部的形状。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-110">However, in BizTalk Server, the **Call Rules** menu item is disabled in the context menu if you try to insert a **Call Rules** shape inside an orchestration that does not have an atomic scope.</span></span> <span data-ttu-id="c7ebc-111">这是一个限制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-111">This is a limitation with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product.</span></span>  
  
2. <span data-ttu-id="c7ebc-112">在业务流程设计器中，选择**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-112">In Orchestration Designer, select the **Call Rules** shape.</span></span>  
  
3. <span data-ttu-id="c7ebc-113">双击该形状以显示**CallRules 策略配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-113">Double-click the shape to display the **CallRules policy configuration** dialog box.</span></span>  
  
4. <span data-ttu-id="c7ebc-114">在中**选择你想要调用的业务策略**下拉列表中，选择所需的策略。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-114">In the **Select the business policy you wish to call** drop-down list, select the policy you need.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c7ebc-115">调用规则配置在确定策略中使用的类型时将查看保存策略的最新版本。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-115">Call Rules configuration will look at the latest saved version of a policy when determining the types used in the policy.</span></span> <span data-ttu-id="c7ebc-116">运行时，将使用部署的该策略的最新版本。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-116">At run time, the latest deployed version of the policy will be used.</span></span>  
  
5. <span data-ttu-id="c7ebc-117">在中**指定策略参数**列表框中，选择从变量**参数名称**属性。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-117">In the **Specify policy parameters** list box, select a variable from the **Parameter Name** property.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c7ebc-118">**调用规则**形状实质上重新构造消息，如同使用**构造**形状，因而可能导致消息丢失的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-118">The **Call Rules** shape is essentially reconstructing the message, as if using a **Construct** shape, which in turn may cause context properties of the message to be lost.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="c7ebc-119">您可以指定一条消息或.NET 变量作为 BRE 策略的参数。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-119">You can specify a message or a .NET variable as a parameter to a BRE policy.</span></span> <span data-ttu-id="c7ebc-120">要传递**TypedXmlDocument**这一事实，指定作为参数在业务流程中声明的相应消息。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-120">To pass a **TypedXmlDocument** fact, specify the corresponding message declared in the orchestration as a parameter.</span></span> <span data-ttu-id="c7ebc-121">若要传递 .NET 事实，请将在业务流程中声明的 .NET 变量指定为参数。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-121">To pass a .NET fact, specify a .NET variable declared in the orchestration as a parameter.</span></span> <span data-ttu-id="c7ebc-122">若要传递数据库事实，指定类型的.NET 变量**DataConnection**或**TypedDataTable**作为策略的参数。</span><span class="sxs-lookup"><span data-stu-id="c7ebc-122">To pass a database fact, specify a .NET variable of type **DataConnection** or **TypedDataTable** as a parameter to the policy.</span></span>