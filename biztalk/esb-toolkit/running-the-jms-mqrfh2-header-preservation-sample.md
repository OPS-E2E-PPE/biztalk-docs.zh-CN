---
title: 运行 JMS MQRFH2 Header 保留示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65982dca-77e1-4267-9528-26c59237e9b1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb03053169b815b01ff2f8a303d969c57bc4916
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242752"
---
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a><span data-ttu-id="99fc6-102">运行 JMS MQRFH2 Header 保留示例</span><span class="sxs-lookup"><span data-stu-id="99fc6-102">Running the JMS MQRFH2 Header Preservation Sample</span></span>
<span data-ttu-id="99fc6-103">此示例的此部分内存一条消息放入 WebSphere 队列。</span><span class="sxs-lookup"><span data-stu-id="99fc6-103">This part of this sample deposits a message into a WebSphere queue.</span></span> <span data-ttu-id="99fc6-104">ESB 提取此消息和出站的 WebSphere 队列到它。</span><span class="sxs-lookup"><span data-stu-id="99fc6-104">The ESB picks up this message and deposits it into an outbound WebSphere queue.</span></span> <span data-ttu-id="99fc6-105">这表明，ESB 和 Microsoft BizTalk 保留完全保真的 RFH2 标头消息通过 BizTalk Server 传输时。</span><span class="sxs-lookup"><span data-stu-id="99fc6-105">This demonstrates that the ESB and Microsoft BizTalk preserve full-fidelity RFH2 headers as a message travels through BizTalk Server.</span></span>  
  
 <span data-ttu-id="99fc6-106">**若要运行标头保留示例**</span><span class="sxs-lookup"><span data-stu-id="99fc6-106">**To run the Header Preservation sample**</span></span>  
  
1.  <span data-ttu-id="99fc6-107">如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="99fc6-107">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="99fc6-108">运行 IBM RfhUtil 实用工具，然后选择名为 ESB 的队列管理器。JMS。若要连接到此队列管理器的第一个下拉列表 Sample.QueueManager。</span><span class="sxs-lookup"><span data-stu-id="99fc6-108">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager.</span></span>  
  
3.  <span data-ttu-id="99fc6-109">在第二个下拉列表中，选择名为 ESB 的出站目标队列。JMS。示例。SENDTOBIZTALK，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="99fc6-109">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as shown in Figure 1.</span></span>  
  
     <span data-ttu-id="99fc6-110">![队列管理器](../esb-toolkit/media/ch6-queuemanager.gif "Ch6-QueueManager")</span><span class="sxs-lookup"><span data-stu-id="99fc6-110">![Queue Manager](../esb-toolkit/media/ch6-queuemanager.gif "Ch6-QueueManager")</span></span>  
  
     <span data-ttu-id="99fc6-111">**图 1**</span><span class="sxs-lookup"><span data-stu-id="99fc6-111">**Figure 1**</span></span>  
  
     <span data-ttu-id="99fc6-112">**连接到的队列管理器和 RfhUtil 中的出站队列**</span><span class="sxs-lookup"><span data-stu-id="99fc6-112">**Connecting to the queue manager and the outbound queue in RfhUtil**</span></span>  
  
4.  <span data-ttu-id="99fc6-113">如果下拉列表不包含任何队列，请确保队列管理器正在运行通过检查 WebSphere MQ 服务项，如图 2 中所示。</span><span class="sxs-lookup"><span data-stu-id="99fc6-113">If the drop-down list does not contain any queues, make sure that the queue manager is running by checking the WebSphere MQ Services item, as shown in Figure 2.</span></span>  
  
     <span data-ttu-id="99fc6-114">![Web 球体](../esb-toolkit/media/ch6-websphere.gif "Ch6 WebSphere")</span><span class="sxs-lookup"><span data-stu-id="99fc6-114">![Web Sphere](../esb-toolkit/media/ch6-websphere.gif "Ch6-WebSphere")</span></span>  
  
     <span data-ttu-id="99fc6-115">**图 2**</span><span class="sxs-lookup"><span data-stu-id="99fc6-115">**Figure 2**</span></span>  
  
     <span data-ttu-id="99fc6-116">**检查队列管理器正在 WebSphere 服务项**</span><span class="sxs-lookup"><span data-stu-id="99fc6-116">**Checking that the queue manager is running in the WebSphere Services item**</span></span>  
  
5.  <span data-ttu-id="99fc6-117">单击**ReadFile**按钮 RfhUtil 实用程序，并导航到名为测试 000128 的测试消息文件。位于名为 \Source\Samples\JMS\Test\Data\Load 子文件夹中的 JMS\\。</span><span class="sxs-lookup"><span data-stu-id="99fc6-117">Click the **ReadFile** button in the RfhUtil utility and navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="99fc6-118">此文件包含一批 128 测试消息，但该实用程序将加载只有第一个。</span><span class="sxs-lookup"><span data-stu-id="99fc6-118">This file contains a batch of 128 test messages, but the utility loads only the first one.</span></span>  
  
6.  <span data-ttu-id="99fc6-119">单击**RFH**选项卡，并确保只有**JMS**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="99fc6-119">Click the **RFH** tab, and then make sure that only the **JMS** check box is selected.</span></span>  
  
7.  <span data-ttu-id="99fc6-120">单击**jms**选项卡，并请确保所选**答复**队列是 ESB。JMS。示例。DYNAMICQ1，所选**目标队列**是 ESB。JMS。示例。DYNAMICQ2。</span><span class="sxs-lookup"><span data-stu-id="99fc6-120">Click the **jms** tab, and then make sure that the selected **Reply To** queue is ESB.JMS.SAMPLE.DYNAMICQ1 and that the selected **Destination Queue** is ESB.JMS.SAMPLE.DYNAMICQ2.</span></span>  
  
8.  <span data-ttu-id="99fc6-121">单击**Main**选项卡，然后依次**编写 Q**按钮可将消息写入到队列。</span><span class="sxs-lookup"><span data-stu-id="99fc6-121">Click the **Main** tab, and then click the **Write Q** button to write the message into the queue.</span></span>  
  
9. <span data-ttu-id="99fc6-122">后一段延迟时应用程序执行，ESB 输出消息将出现在 ESB。JMS。示例。DYNAMICQ1 和 ESB。JMS。示例。DYNAMICQ1 队列。</span><span class="sxs-lookup"><span data-stu-id="99fc6-122">After a delay while the application executes, the ESB output message appears in the ESB.JMS.SAMPLE.DYNAMICQ1 and ESB.JMS.SAMPLE.DYNAMICQ1 queues.</span></span> <span data-ttu-id="99fc6-123">打开 WebSphere 队列资源管理器并浏览队列来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="99fc6-123">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>  
  
10. <span data-ttu-id="99fc6-124">返回到 RfhUtil 实用工具并连接到队列以查看消息。</span><span class="sxs-lookup"><span data-stu-id="99fc6-124">Go back to the RfhUtil utility and connect to the queues to see the messages.</span></span> <span data-ttu-id="99fc6-125">单击**MQMD、 RFH，** 并**jms**选项卡来验证输入和输出值的目标队列中的消息不变并且回复到队列中的消息是相同除外，而不是成为标准的 JMS 消息，该消息标记为"其他"。</span><span class="sxs-lookup"><span data-stu-id="99fc6-125">Click the **MQMD, RFH,** and **jms** tabs to verify that the input and output values are unchanged for the message in the Destination Queue, and that the message in the Reply To queue is the same except that, instead of being a standard JMS message, the message is marked as "other".</span></span>