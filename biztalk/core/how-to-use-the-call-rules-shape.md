---
title: "如何使用该调用规则形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a634c2e0a97e627925390610bf4c3039c8afc85c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-call-rules-shape"></a><span data-ttu-id="eb889-102">如何使用调用规则形状</span><span class="sxs-lookup"><span data-stu-id="eb889-102">How to Use the Call Rules Shape</span></span>
<span data-ttu-id="eb889-103">在业务流程设计器中，你可以使用**调用规则**形状以调用业务策略。</span><span class="sxs-lookup"><span data-stu-id="eb889-103">In Orchestration Designer, you can use the **Call Rules** shape to call a business policy.</span></span>  
  
### <a name="to-configure-the-call-rules-shape"></a><span data-ttu-id="eb889-104">配置调用规则形状</span><span class="sxs-lookup"><span data-stu-id="eb889-104">To configure the Call Rules shape</span></span>  
  
1.  <span data-ttu-id="eb889-105">从工具箱中**BizTalk 业务流程**选项卡上，拖动**调用规则**到业务流程设计图面上的连接线的形状。</span><span class="sxs-lookup"><span data-stu-id="eb889-105">From the Toolbox, in the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line on the Orchestration Design Surface.</span></span>  
  
     <span data-ttu-id="eb889-106">-或者-</span><span class="sxs-lookup"><span data-stu-id="eb889-106">—Or—</span></span>  
  
     <span data-ttu-id="eb889-107">右键单击连接的线条或形状占位符想要添加该形状，指向**插入形状**上下文菜单，然后单击**调用规则**。</span><span class="sxs-lookup"><span data-stu-id="eb889-107">Right-click the connecting line or the shape placeholder where you want to add the shape, point to **Insert Shape** on the context menu, and then click **Call Rules**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb889-108">在[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，不需要具有原子作用域插入**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="eb889-108">In [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], you do not need to have an atomic scope to insert a **Call Rules** shape.</span></span> <span data-ttu-id="eb889-109">您可以拖动**调用规则**从工具箱调整到业务流程设计图面。</span><span class="sxs-lookup"><span data-stu-id="eb889-109">You can drag a **Call Rules** shape into the Orchestration Design Surface from the Toolbox.</span></span> <span data-ttu-id="eb889-110">但是，在[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、**调用规则**菜单项被禁用的上下文菜单中，如果你尝试插入**调用规则**内没有原子作用域的业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="eb889-110">However, in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], the **Call Rules** menu item is disabled in the context menu if you try to insert a **Call Rules** shape inside an orchestration that does not have an atomic scope.</span></span> <span data-ttu-id="eb889-111">这是与限制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品。</span><span class="sxs-lookup"><span data-stu-id="eb889-111">This is a limitation with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] product.</span></span>  
  
2.  <span data-ttu-id="eb889-112">在业务流程设计器中，选择**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="eb889-112">In Orchestration Designer, select the **Call Rules** shape.</span></span>  
  
3.  <span data-ttu-id="eb889-113">双击要显示的形状**规则策略配置**对话框。</span><span class="sxs-lookup"><span data-stu-id="eb889-113">Double-click the shape to display the **CallRules policy configuration** dialog box.</span></span>  
  
4.  <span data-ttu-id="eb889-114">在**选择你想要调用的业务策略**下拉列表中，选择您需要的策略。</span><span class="sxs-lookup"><span data-stu-id="eb889-114">In the **Select the business policy you wish to call** drop-down list, select the policy you need.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb889-115">调用规则配置在确定策略中使用的类型时将查看保存策略的最新版本。</span><span class="sxs-lookup"><span data-stu-id="eb889-115">Call Rules configuration will look at the latest saved version of a policy when determining the types used in the policy.</span></span> <span data-ttu-id="eb889-116">运行时，将使用部署的该策略的最新版本。</span><span class="sxs-lookup"><span data-stu-id="eb889-116">At run time, the latest deployed version of the policy will be used.</span></span>  
  
5.  <span data-ttu-id="eb889-117">在**指定策略参数**列表框中，选择中的某个变量**参数名称**属性。</span><span class="sxs-lookup"><span data-stu-id="eb889-117">In the **Specify policy parameters** list box, select a variable from the **Parameter Name** property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb889-118">**调用规则**形状实质上重新构造消息，就像使用**构造**形状，这又可能导致丢失消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="eb889-118">The **Call Rules** shape is essentially reconstructing the message, as if using a **Construct** shape, which in turn may cause context properties of the message to be lost.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb889-119">作为参数传递给 BRE 策略，可以指定某个消息或.NET 变量。</span><span class="sxs-lookup"><span data-stu-id="eb889-119">You can specify a message or a .NET variable as a parameter to a BRE policy.</span></span> <span data-ttu-id="eb889-120">若要将传递**TypedXmlDocument**事实，指定相应的消息作为参数业务流程中声明。</span><span class="sxs-lookup"><span data-stu-id="eb889-120">To pass a **TypedXmlDocument** fact, specify the corresponding message declared in the orchestration as a parameter.</span></span> <span data-ttu-id="eb889-121">若要传递 .NET 事实，请将在业务流程中声明的 .NET 变量指定为参数。</span><span class="sxs-lookup"><span data-stu-id="eb889-121">To pass a .NET fact, specify a .NET variable declared in the orchestration as a parameter.</span></span> <span data-ttu-id="eb889-122">若要将传递数据库事实，指定类型的.NET 变量**该组**或**TypedDataTable**作为参数传递给策略。</span><span class="sxs-lookup"><span data-stu-id="eb889-122">To pass a database fact, specify a .NET variable of type **DataConnection** or **TypedDataTable** as a parameter to the policy.</span></span>