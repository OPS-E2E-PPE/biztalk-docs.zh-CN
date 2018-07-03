---
title: 设置公用业务流程和 HTTP 适配器的超时值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, HTTP adapters
- public processes, orchestrations
- orchestrations, time-outs
- public processes, time-outs
- orchestrations, public-process orchestrations
- HTTP adapters, public processes
- HTTP adapters, time-outs
ms.assetid: 82fd64ac-6191-410c-94b3-8a3d1ff2611f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e0977589e310746e2c75c1f89fdd2c41ecb86aa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976710"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a><span data-ttu-id="40b38-102">设置公用业务流程和 HTTP 适配器的超时值</span><span class="sxs-lookup"><span data-stu-id="40b38-102">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>
<span data-ttu-id="40b38-103">在同步方案中，如果将公用业务流程与 HTTP 适配器一起使用，则必须为它们设置相应的超时值。</span><span class="sxs-lookup"><span data-stu-id="40b38-103">When you use a public-process orchestration with an HTTP adapter in a synchronous scenario, you must set the time-outs for each appropriately.</span></span> <span data-ttu-id="40b38-104">业务流程的超时设置（执行时间）必须小于 HTTP 适配器的超时设置（请求超时值）。</span><span class="sxs-lookup"><span data-stu-id="40b38-104">The time-out setting for the orchestration (Time to Perform) must be smaller than the time-out for the HTTP adapter (Request Timeout).</span></span> <span data-ttu-id="40b38-105">这是因为如果 HTTP 适配器的设置较小，则适配器可能会在业务流程执行完之前发生超时。</span><span class="sxs-lookup"><span data-stu-id="40b38-105">This is because if the setting for the HTTP adapter is smaller, the adapter could time out before the orchestration.</span></span> <span data-ttu-id="40b38-106">这使适配器可以控制流程。</span><span class="sxs-lookup"><span data-stu-id="40b38-106">This gives the adapter control of the process.</span></span> <span data-ttu-id="40b38-107">业务流程必须在流程的控制之下；因此，业务流程的超时设置必须较小。</span><span class="sxs-lookup"><span data-stu-id="40b38-107">The orchestration must be in control of the process; therefore, its time-out setting must be smaller.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a><span data-ttu-id="40b38-108">设置 HTTP 适配器的超时设置</span><span class="sxs-lookup"><span data-stu-id="40b38-108">To set the time-out setting for the HTTP adapter</span></span>  
  
1.  <span data-ttu-id="40b38-109">在 BizTalk 浏览器中，展开**发送端口**，然后双击与公用业务流程使用的 HTTP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="40b38-109">In BizTalk Explorer, expand **Send ports**, and then double-click the HTTP send port used with the public-process orchestration.</span></span>  
  
2.  <span data-ttu-id="40b38-110">在发送端口属性窗口中，单击省略号按钮 (**...**) 用于**地址 (URI)**。</span><span class="sxs-lookup"><span data-stu-id="40b38-110">In the Send Port Properties window, click the ellipsis button (**...**) for **Address (URI)**.</span></span>  
  
3.  <span data-ttu-id="40b38-111">在常规窗格中的 HTTP 传输属性窗口中**请求超时 （秒）** 框中，键入适当的值来表示超时值。此值必须大于**执行时间**设置为相关合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="40b38-111">In the HTTP Transport Properties window, in the General pane, in the **Request timeout (sec.)** box, type an appropriate value for the time-out. This value must be larger than the **Time to Perform** setting for the relevant Partner Interface Process (PIP).</span></span>  
  
4.  <span data-ttu-id="40b38-112">单击**确定**，然后单击**确定**试。</span><span class="sxs-lookup"><span data-stu-id="40b38-112">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a><span data-ttu-id="40b38-113">设置公用业务流程的超时设置</span><span class="sxs-lookup"><span data-stu-id="40b38-113">To set the time-out setting for the public-process orchestration</span></span>  
  
1. <span data-ttu-id="40b38-114">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**BizTalk Accelerator for RosettaNet 管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="40b38-114">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click  **BizTalk Accelerator for RosettaNet Management Console**.</span></span>  
  
2. <span data-ttu-id="40b38-115">展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**流程配置设置**。</span><span class="sxs-lookup"><span data-stu-id="40b38-115">Expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Process Configuration Settings**.</span></span>  
  
3. <span data-ttu-id="40b38-116">右键单击你想要设置超时设置的 PIP，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="40b38-116">Right-click the PIP that you want to set the time-out setting for, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="40b38-117">在属性对话框中，在**活动**选项卡上，在**执行时间**框中，键入适当的值小于 HTTP 适配器超时设置，然后依次**确定**.</span><span class="sxs-lookup"><span data-stu-id="40b38-117">In theProperties dialog box, on the **Activity** tab, in the **Time to Perform** box, type an appropriate value that is smaller than the HTTP adapter time-out setting, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b38-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="40b38-118">See Also</span></span>  
 [<span data-ttu-id="40b38-119">编程指南</span><span class="sxs-lookup"><span data-stu-id="40b38-119">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)