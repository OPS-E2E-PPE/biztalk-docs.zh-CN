---
title: ApplicationAdapter |Microsoft Docs
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
ms.openlocfilehash: a738003a3afb9f34e4546d1a1865e99376e8fba6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284907"
---
# <a name="applicationadapter"></a><span data-ttu-id="925df-102">ApplicationAdapter</span><span class="sxs-lookup"><span data-stu-id="925df-102">ApplicationAdapter</span></span>
<span data-ttu-id="925df-103">ApplicationAdapter 示例演示如何从公共和专用流程 （响应方或发起方） 发送通知时收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="925df-103">The ApplicationAdapter sample demonstrates how to send notifications from the public and private processes (responder or initiator) when you receive a message.</span></span> <span data-ttu-id="925df-104">具有所需的任何其他功能，可以自定义示例。</span><span class="sxs-lookup"><span data-stu-id="925df-104">You can customize the sample with whatever additional functionality you want.</span></span>  
  
 <span data-ttu-id="925df-105">ApplicationAdapter 示例演示如何实现`IApplicationAdapter`接口`ApplicationAdapter1`类。</span><span class="sxs-lookup"><span data-stu-id="925df-105">The ApplicationAdapter sample demonstrates how to implement the `IApplicationAdapter` interface to the `ApplicationAdapter1` class.</span></span> <span data-ttu-id="925df-106">此类包括两种方法`BeginNotify`和`Notify`。</span><span class="sxs-lookup"><span data-stu-id="925df-106">This class includes two methods, `BeginNotify` and `Notify`.</span></span> <span data-ttu-id="925df-107">每个类的参数包括消息类别、 源参与方名称、 目标参与方名称、 合作伙伴接口流程 (PIP) 代码、 PIP 实例 ID，以及 PIP 版本。</span><span class="sxs-lookup"><span data-stu-id="925df-107">The parameters for each class are the message category, source party name, destination party name, Partner Interface Process (PIP) code, PIP instance ID, and PIP version.</span></span>  
  
 <span data-ttu-id="925df-108">通过在输入程序集名称和类名设置为协议 ApplicationAdapter**常规**Microsoft® 中的协议选项卡[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="925df-108">You set the ApplicationAdapter for an agreement by entering the assembly name and class name on the **General** tab of the agreement in the Microsoft® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="925df-109">与 BizTalk 主机服务相同的凭据下运行的应用程序适配器.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="925df-109">The application adapter .dll file runs under the same credentials as the BizTalk host service.</span></span>  
  
 <span data-ttu-id="925df-110">如果您更改了 ApplicationAdapter 示例或者 ApplicationAdapter 示例依赖于任何外部环境变量，请重新启动托管的 BizTalk 主机服务[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用流程。</span><span class="sxs-lookup"><span data-stu-id="925df-110">If you change the ApplicationAdapter sample or any external environment variable that the ApplicationAdapter sample depends on, restart the BizTalk host service that hosts the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span>  
  
 <span data-ttu-id="925df-111">ApplicationAdapter 示例代码位于\<*驱动器*\>: files\ BizTalk\<版本\>Accelerator for RosettaNet\SDK\ApplicationAdapter\\.</span><span class="sxs-lookup"><span data-stu-id="925df-111">The ApplicationAdapter sample code is located at \<*drive*\>:\Program Files\ BizTalk \<version\> Accelerator for RosettaNet\SDK\ApplicationAdapter\\.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="925df-112">演示</span><span class="sxs-lookup"><span data-stu-id="925df-112">Demonstrates</span></span>  
 <span data-ttu-id="925df-113">ApplicationAdapter 示例演示如何通知响应方专用流程公用流程已收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="925df-113">The ApplicationAdapter sample demonstrates how to notify the responder private process that the public process has received a message.</span></span> <span data-ttu-id="925df-114">通知指明消息类别、 源参与方名称、 目标参与方名称、 PIP 代码、 PIP 版本和 PIP 实例 id。</span><span class="sxs-lookup"><span data-stu-id="925df-114">The notification indicates the message category, the source party name, the destination party name, the PIP code, the PIP version, and the PIP instance ID.</span></span> <span data-ttu-id="925df-115">可以发送此通知的操作或响应消息。</span><span class="sxs-lookup"><span data-stu-id="925df-115">You can send this notification for either an action or a response message.</span></span>  
  
 <span data-ttu-id="925df-116">`BeginNotify`和`Notify`方法的工作原理，如下所示：</span><span class="sxs-lookup"><span data-stu-id="925df-116">The `BeginNotify` and `Notify` methods work as follows:</span></span>  
  
1.  <span data-ttu-id="925df-117">响应方公用流程接收消息。</span><span class="sxs-lookup"><span data-stu-id="925df-117">The responder public process receives a message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="925df-118">以下步骤，还有适用于在其中公用发起方接收响应消息从响应方的方案。</span><span class="sxs-lookup"><span data-stu-id="925df-118">The following steps are also applicable for the scenario in which the public initiator receives a response message from the responder.</span></span>  
  
2.  <span data-ttu-id="925df-119">如果验证由接收管道、 公用流程和验证适配器，如果适用，成功，响应方公用流程会调用`BeginNotify`中的方法`ApplicationAdapter`类。</span><span class="sxs-lookup"><span data-stu-id="925df-119">If validation by the receive pipeline and public process, and validation adapter, if applicable, was successful, the responder public process calls the `BeginNotify` method in the `ApplicationAdapter` class.</span></span> <span data-ttu-id="925df-120">此方法通知响应方专用流程公用流程已收到新消息和该消息保存在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="925df-120">This method notifies the responder private process that the public process has received the new message and saved the message in the MessageBox database.</span></span>  
  
3.  <span data-ttu-id="925df-121">响应方公用流程将信号消息发送回发起方。</span><span class="sxs-lookup"><span data-stu-id="925df-121">The responder public process sends a signal message back to the initiator.</span></span>  
  
4.  <span data-ttu-id="925df-122">响应方公用流程将消息服务内容发送到响应方专用流程。</span><span class="sxs-lookup"><span data-stu-id="925df-122">The responder public process sends the message service content to the responder private process.</span></span>  
  
5.  <span data-ttu-id="925df-123">响应方专用流程将该消息放在 BTARNDATA 数据库的 MessagesToLOB 表中。</span><span class="sxs-lookup"><span data-stu-id="925df-123">The responder private process puts the message in the MessagesToLOB table of the BTARNDATA database.</span></span>  
  
6.  <span data-ttu-id="925df-124">响应方专用流程调用`Notify`中的方法`ApplicationAdapter`类返回到响应方公用流程发送最终通知消息。</span><span class="sxs-lookup"><span data-stu-id="925df-124">The responder private process calls the `Notify` method in the `ApplicationAdapter` class to send the End Notify message back to the responder public process.</span></span> <span data-ttu-id="925df-125">响应方公用流程必须接收进程才算成功完成通知结束消息。</span><span class="sxs-lookup"><span data-stu-id="925df-125">The responder public process must receive the End Notify message for the process to be successfully completed.</span></span> <span data-ttu-id="925df-126">否则，则会挂起消息。</span><span class="sxs-lookup"><span data-stu-id="925df-126">Otherwise, the message is suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="925df-127">可以使用`Notify`消息通知业务 (LOB) 应用程序消息正在 MessagesToLOB 表中等待。</span><span class="sxs-lookup"><span data-stu-id="925df-127">You can use the `Notify` message to signal the line-of-business (LOB) application that the message is waiting in the MessagesToLOB table.</span></span> <span data-ttu-id="925df-128">如很快系统会提醒 LOB 应用程序，LOB 应用程序可以从该表中检索消息。</span><span class="sxs-lookup"><span data-stu-id="925df-128">As soon the system alerts the LOB application, the LOB application can retrieve the message from that table.</span></span>  
  
## <a name="to-implement-this-sample"></a><span data-ttu-id="925df-129">若要实现此示例</span><span class="sxs-lookup"><span data-stu-id="925df-129">To Implement this Sample</span></span>  
 <span data-ttu-id="925df-130">若要实现该 ApplicationAdapter 示例，必须向协议添加应用程序适配器。</span><span class="sxs-lookup"><span data-stu-id="925df-130">To implement the ApplicationAdapter sample, you must add the application adapter to the agreement.</span></span>  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a><span data-ttu-id="925df-131">若要向协议添加应用程序适配器</span><span class="sxs-lookup"><span data-stu-id="925df-131">To add the application adapter to an agreement</span></span>  
  
1. <span data-ttu-id="925df-132">单击**启动**，依次指向**所有程序**，指向 Microsoft **BizTalk\<版本\>Accelerator for RosettaNet**，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="925df-132">Click **Start**, point to **All Programs**, point to Microsoft **BizTalk \<version\> Accelerator for RosettaNet**, and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="925df-133">在中[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="925df-133">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and click **Agreements**.</span></span>  
  
3. <span data-ttu-id="925df-134">双击你想要添加应用程序适配器的协议。</span><span class="sxs-lookup"><span data-stu-id="925df-134">Double-click the agreement to which you want to add the application adapter.</span></span>  
  
4. <span data-ttu-id="925df-135">在中**应用程序适配器**框中，单击省略号按钮 (**...**) 右侧的按钮**程序集名称**，转到包含应用程序适配器程序集的位置，选择相应的.dll 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="925df-135">In the **Application Adapter** box, click the ellipsis button (**...**) button to the right of **Assembly name**, move to the location that contains the application adapter assembly, select the appropriate .dll file, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="925df-136">单击向下的箭头**类名**，选择应用程序适配器类，并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="925df-136">Click the down arrow for **Class Name**, select the application adapter class, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="925df-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="925df-137">See Also</span></span>  
 [<span data-ttu-id="925df-138">适配器示例</span><span class="sxs-lookup"><span data-stu-id="925df-138">Adapter Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)