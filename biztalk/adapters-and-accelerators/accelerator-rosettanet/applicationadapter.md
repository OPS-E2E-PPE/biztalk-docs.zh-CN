---
title: ApplicationAdapter |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9b876b-cd37-4e24-a476-186adc155ac0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee9d04f98da5e9b8aa1faba81f32fe5ec37d23b9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963187"
---
# <a name="applicationadapter"></a><span data-ttu-id="00bb8-102">ApplicationAdapter</span><span class="sxs-lookup"><span data-stu-id="00bb8-102">ApplicationAdapter</span></span>
<span data-ttu-id="00bb8-103">ApplicationAdapter 示例演示如何在接收消息时从响应方或发起方的公用流程和专用流程发送通知。</span><span class="sxs-lookup"><span data-stu-id="00bb8-103">The ApplicationAdapter sample demonstrates how to send notifications from the public and private processes (responder or initiator) when you receive a message.</span></span> <span data-ttu-id="00bb8-104">你可以自定义该示例，使其具有任何你需要的其他功能。</span><span class="sxs-lookup"><span data-stu-id="00bb8-104">You can customize the sample with whatever additional functionality you want.</span></span>  
  
 <span data-ttu-id="00bb8-105">ApplicationAdapter 示例演示如何将 `IApplicationAdapter` 接口实现到 `ApplicationAdapter1` 类。</span><span class="sxs-lookup"><span data-stu-id="00bb8-105">The ApplicationAdapter sample demonstrates how to implement the `IApplicationAdapter` interface to the `ApplicationAdapter1` class.</span></span> <span data-ttu-id="00bb8-106">此类包含 `BeginNotify` 和 `Notify` 这两个方法。</span><span class="sxs-lookup"><span data-stu-id="00bb8-106">This class includes two methods, `BeginNotify` and `Notify`.</span></span> <span data-ttu-id="00bb8-107">每个类的参数包括消息类别、源参与方名称、目标参与方名称、合作伙伴接口流程 (PIP) 代码、PIP 实例 ID 以及 PIP 版本。</span><span class="sxs-lookup"><span data-stu-id="00bb8-107">The parameters for each class are the message category, source party name, destination party name, Partner Interface Process (PIP) code, PIP instance ID, and PIP version.</span></span>  
  
 <span data-ttu-id="00bb8-108">在输入的程序集名称和类名设置了协议 ApplicationAdapter**常规**选项卡中的协议[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="00bb8-108">You set the ApplicationAdapter for an agreement by entering the assembly name and class name on the **General** tab of the agreement in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="00bb8-109">应用程序适配器 .dll 文件运行所用的凭据与 BizTalk 主机服务的凭据相同。</span><span class="sxs-lookup"><span data-stu-id="00bb8-109">The application adapter .dll file runs under the same credentials as the BizTalk host service.</span></span>  
  
 <span data-ttu-id="00bb8-110">如果更改了 ApplicationAdapter 示例或者 ApplicationAdapter 示例依赖的任何外部环境变量，请重新启动 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 公用流程的宿主 BizTalk 主机服务。</span><span class="sxs-lookup"><span data-stu-id="00bb8-110">If you change the ApplicationAdapter sample or any external environment variable that the ApplicationAdapter sample depends on, restart the BizTalk host service that hosts the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span>  
  
 <span data-ttu-id="00bb8-111">ApplicationAdapter 示例代码位于\<*驱动器*\>: files\ BizTalk\<版本\>Accelerator for RosettaNet\SDK\ApplicationAdapter\\.</span><span class="sxs-lookup"><span data-stu-id="00bb8-111">The ApplicationAdapter sample code is located at \<*drive*\>:\Program Files\ BizTalk \<version\> Accelerator for RosettaNet\SDK\ApplicationAdapter\\.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="00bb8-112">演示</span><span class="sxs-lookup"><span data-stu-id="00bb8-112">Demonstrates</span></span>  
 <span data-ttu-id="00bb8-113">ApplicationAdapter 示例演示如何通知响应方专用流程公用流程已收到消息。</span><span class="sxs-lookup"><span data-stu-id="00bb8-113">The ApplicationAdapter sample demonstrates how to notify the responder private process that the public process has received a message.</span></span> <span data-ttu-id="00bb8-114">通知指明消息类别、源参与方名称、目标参与方名称、PIP 代码、PIP 版本以及 PIP 实例 ID。</span><span class="sxs-lookup"><span data-stu-id="00bb8-114">The notification indicates the message category, the source party name, the destination party name, the PIP code, the PIP version, and the PIP instance ID.</span></span> <span data-ttu-id="00bb8-115">可以为操作或响应消息发送此通知。</span><span class="sxs-lookup"><span data-stu-id="00bb8-115">You can send this notification for either an action or a response message.</span></span>  
  
 <span data-ttu-id="00bb8-116">`BeginNotify` 和 `Notify` 方法的工作方式如下所示：</span><span class="sxs-lookup"><span data-stu-id="00bb8-116">The `BeginNotify` and `Notify` methods work as follows:</span></span>  
  
1.  <span data-ttu-id="00bb8-117">响应方公用流程接收消息。</span><span class="sxs-lookup"><span data-stu-id="00bb8-117">The responder public process receives a message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00bb8-118">以下步骤也适用于公用发起方从响应方接收响应消息的情况。</span><span class="sxs-lookup"><span data-stu-id="00bb8-118">The following steps are also applicable for the scenario in which the public initiator receives a response message from the responder.</span></span>  
  
2.  <span data-ttu-id="00bb8-119">如果接收管道、公用流程和验证适配器（如果有）执行的验证成功，则响应方公用流程会调用 `BeginNotify` 类中的 `ApplicationAdapter` 方法。</span><span class="sxs-lookup"><span data-stu-id="00bb8-119">If validation by the receive pipeline and public process, and validation adapter, if applicable, was successful, the responder public process calls the `BeginNotify` method in the `ApplicationAdapter` class.</span></span> <span data-ttu-id="00bb8-120">此方法通知响应方专用流程公用流程已收到新消息并将该消息保存在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="00bb8-120">This method notifies the responder private process that the public process has received the new message and saved the message in the MessageBox database.</span></span>  
  
3.  <span data-ttu-id="00bb8-121">响应方公用流程向发起方回送信号消息。</span><span class="sxs-lookup"><span data-stu-id="00bb8-121">The responder public process sends a signal message back to the initiator.</span></span>  
  
4.  <span data-ttu-id="00bb8-122">响应方公用流程向响应方专用流程发送消息服务内容。</span><span class="sxs-lookup"><span data-stu-id="00bb8-122">The responder public process sends the message service content to the responder private process.</span></span>  
  
5.  <span data-ttu-id="00bb8-123">响应方专用流程将消息放入 BTARNDATA 数据库的 MessagesToLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="00bb8-123">The responder private process puts the message in the MessagesToLOB table of the BTARNDATA database.</span></span>  
  
6.  <span data-ttu-id="00bb8-124">响应方专用流程调用 `Notify` 类中的 `ApplicationAdapter` 方法，将“通知结束”消息回送给响应方公用流程。</span><span class="sxs-lookup"><span data-stu-id="00bb8-124">The responder private process calls the `Notify` method in the `ApplicationAdapter` class to send the End Notify message back to the responder public process.</span></span> <span data-ttu-id="00bb8-125">只有在响应方公用流程收到“通知结束”消息时，该流程才算成功完成。</span><span class="sxs-lookup"><span data-stu-id="00bb8-125">The responder public process must receive the End Notify message for the process to be successfully completed.</span></span> <span data-ttu-id="00bb8-126">否则，消息被挂起。</span><span class="sxs-lookup"><span data-stu-id="00bb8-126">Otherwise, the message is suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00bb8-127">可以使用 `Notify` 消息通知业务线 (LOB) 应用程序消息正在 MessagesToLOB 表中等待。</span><span class="sxs-lookup"><span data-stu-id="00bb8-127">You can use the `Notify` message to signal the line-of-business (LOB) application that the message is waiting in the MessagesToLOB table.</span></span> <span data-ttu-id="00bb8-128">系统向 LOB 应用程序发出警报后，LOB 应用程序可立即从该表中检索此消息。</span><span class="sxs-lookup"><span data-stu-id="00bb8-128">As soon the system alerts the LOB application, the LOB application can retrieve the message from that table.</span></span>  
  
## <a name="to-implement-this-sample"></a><span data-ttu-id="00bb8-129">实现此示例</span><span class="sxs-lookup"><span data-stu-id="00bb8-129">To Implement this Sample</span></span>  
 <span data-ttu-id="00bb8-130">要实现该 ApplicationAdapter 示例，必须向协议添加应用程序适配器。</span><span class="sxs-lookup"><span data-stu-id="00bb8-130">To implement the ApplicationAdapter sample, you must add the application adapter to the agreement.</span></span>  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a><span data-ttu-id="00bb8-131">向协议添加应用程序适配器</span><span class="sxs-lookup"><span data-stu-id="00bb8-131">To add the application adapter to an agreement</span></span>  
  
1.  <span data-ttu-id="00bb8-132">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] **BizTalk\<版本\>Accelerator for RosettaNet**，，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="00bb8-132">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] **BizTalk \<version\> Accelerator for RosettaNet**, and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="00bb8-133">在[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="00bb8-133">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and click **Agreements**.</span></span>  
  
3.  <span data-ttu-id="00bb8-134">双击要添加应用程序适配器的协议。</span><span class="sxs-lookup"><span data-stu-id="00bb8-134">Double-click the agreement to which you want to add the application adapter.</span></span>  
  
4.  <span data-ttu-id="00bb8-135">在**应用程序适配器**框中，单击省略号按钮 (**...**) 的右侧的按钮**程序集名称**，移到包含的应用程序适配器程序集的位置，选择相应的.dll 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="00bb8-135">In the **Application Adapter** box, click the ellipsis button (**...**) button to the right of **Assembly name**, move to the location that contains the application adapter assembly, select the appropriate .dll file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="00bb8-136">单击向下的箭头**类名**，选择应用程序的适配器类，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="00bb8-136">Click the down arrow for **Class Name**, select the application adapter class, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00bb8-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00bb8-137">See Also</span></span>  
 [<span data-ttu-id="00bb8-138">适配器示例</span><span class="sxs-lookup"><span data-stu-id="00bb8-138">Adapter Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)