---
title: 绑定和启动 FRR 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, binding orchestrations
- FRR, starting orchestrations
- bindings, orchestrations
- orchestrations, bindings
ms.assetid: b74a0116-e98b-4fec-b386-710ce421a1e2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01386cedbd25148e5ea0ce2ac44fb56e9fe3d03
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987438"
---
# <a name="binding-and-starting-the-frr-orchestration"></a><span data-ttu-id="570c9-102">绑定和启动 FRR 业务流程</span><span class="sxs-lookup"><span data-stu-id="570c9-102">Binding and Starting the FRR Orchestration</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="570c9-103"> 包括 FRR 业务流程，作为部署的程序集 (Microsoft。Solutions.FinancialServices.SWIFT.FrrOrchestration)。</span><span class="sxs-lookup"><span data-stu-id="570c9-103"> includes the FRR orchestration as a deployed assembly (Microsoft .Solutions.FinancialServices.SWIFT.FrrOrchestration).</span></span> <span data-ttu-id="570c9-104">您需要启动此业务流程。</span><span class="sxs-lookup"><span data-stu-id="570c9-104">You need to start this orchestration.</span></span>  
  
 <span data-ttu-id="570c9-105">**摘要**</span><span class="sxs-lookup"><span data-stu-id="570c9-105">**Summary**</span></span>  
  
 <span data-ttu-id="570c9-106">若要启动 FRR 业务流程，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="570c9-106">To start the FRR orchestration, do the following:</span></span>  
  
-   <span data-ttu-id="570c9-107">通过设置到 BizTalkServerApplication 主机绑定 FrrOrchestration.FrrMain 业务流程。</span><span class="sxs-lookup"><span data-stu-id="570c9-107">Bind the FrrOrchestration.FrrMain orchestration by setting the host to BizTalkServerApplication.</span></span>  
  
-   <span data-ttu-id="570c9-108">启动 FrrOrchestration.FrrMain 业务流程。</span><span class="sxs-lookup"><span data-stu-id="570c9-108">Start the FrrOrchestration.FrrMain orchestration.</span></span>  
  
### <a name="to-bind-and-start-the-frr-orchestration"></a><span data-ttu-id="570c9-109">绑定和启动 FRR 业务流程</span><span class="sxs-lookup"><span data-stu-id="570c9-109">To bind and start the FRR orchestration</span></span>  
  
1.  <span data-ttu-id="570c9-110">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，然后**BizTalk应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="570c9-110">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, **BizTalk Group**, **Applications**, and then **BizTalk Application 1**.</span></span> <span data-ttu-id="570c9-111">单击**业务流程**。</span><span class="sxs-lookup"><span data-stu-id="570c9-111">Click **Orchestrations**.</span></span>  
  
2.  <span data-ttu-id="570c9-112">在业务流程窗格中，右键单击**FrrOrchestration.FrrMain**业务流程，并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="570c9-112">In the Orchestrations pane, right-click the **FrrOrchestration.FrrMain** orchestration, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="570c9-113">在业务流程属性对话框中，单击**绑定**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="570c9-113">In the Orchestration Properties dialog box, click **Bindings** in the left pane.</span></span> <span data-ttu-id="570c9-114">有关**主机**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="570c9-114">For **Host**, select **BizTalkServerApplication**.</span></span> <span data-ttu-id="570c9-115">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="570c9-115">Click **Apply**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="570c9-116">在业务流程窗格中，右键单击**FrrMain**业务流程，并单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="570c9-116">In the Orchestrations pane, right-click the **FrrMain** orchestration, and then click **Start**.</span></span>