---
title: 运行 JMS MQRFH2 标头保留示例 |Microsoft 文档
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
ms.openlocfilehash: ab840ed1d319f8fd50d3a386e0ffc9b349f61b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295125"
---
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a><span data-ttu-id="02a99-102">运行 JMS MQRFH2 标头保留示例</span><span class="sxs-lookup"><span data-stu-id="02a99-102">Running the JMS MQRFH2 Header Preservation Sample</span></span>
<span data-ttu-id="02a99-103">此示例的这一部分内存一条消息放入 WebSphere 队列。</span><span class="sxs-lookup"><span data-stu-id="02a99-103">This part of this sample deposits a message into a WebSphere queue.</span></span> <span data-ttu-id="02a99-104">ESB 拾取此消息，并放到出站 WebSphere 队列。</span><span class="sxs-lookup"><span data-stu-id="02a99-104">The ESB picks up this message and deposits it into an outbound WebSphere queue.</span></span> <span data-ttu-id="02a99-105">此示例演示，ESB 和 Microsoft BizTalk 保留完全保真的 RFH2 标头为消息的传输时通过 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="02a99-105">This demonstrates that the ESB and Microsoft BizTalk preserve full-fidelity RFH2 headers as a message travels through BizTalk Server.</span></span>  
  
 <span data-ttu-id="02a99-106">**若要运行标头保留示例**</span><span class="sxs-lookup"><span data-stu-id="02a99-106">**To run the Header Preservation sample**</span></span>  
  
1.  <span data-ttu-id="02a99-107">如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="02a99-107">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="02a99-108">运行 IBM RfhUtil 实用程序，，然后选择名为 ESB 的队列管理器。JMS。在第一个下拉列表中连接到此队列管理器中的 Sample.QueueManager。</span><span class="sxs-lookup"><span data-stu-id="02a99-108">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager.</span></span>  
  
3.  <span data-ttu-id="02a99-109">在第二个下拉列表中，选择名为 ESB 的目标出站队列。JMS。示例。SENDTOBIZTALK，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="02a99-109">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as shown in Figure 1.</span></span>  
  
     <span data-ttu-id="02a99-110">![队列管理器](../esb-toolkit/media/ch6-queuemanager.gif "Ch6 QueueManager")</span><span class="sxs-lookup"><span data-stu-id="02a99-110">![Queue Manager](../esb-toolkit/media/ch6-queuemanager.gif "Ch6-QueueManager")</span></span>  
  
     <span data-ttu-id="02a99-111">**图 1**</span><span class="sxs-lookup"><span data-stu-id="02a99-111">**Figure 1**</span></span>  
  
     <span data-ttu-id="02a99-112">**连接到的队列管理器和 RfhUtil 中的出站队列**</span><span class="sxs-lookup"><span data-stu-id="02a99-112">**Connecting to the queue manager and the outbound queue in RfhUtil**</span></span>  
  
4.  <span data-ttu-id="02a99-113">如果下拉列表不包含任何队列，请确保队列管理器正在运行通过检查 WebSphere MQ 服务项，如图 2 中所示。</span><span class="sxs-lookup"><span data-stu-id="02a99-113">If the drop-down list does not contain any queues, make sure that the queue manager is running by checking the WebSphere MQ Services item, as shown in Figure 2.</span></span>  
  
     <span data-ttu-id="02a99-114">![Web 球](../esb-toolkit/media/ch6-websphere.gif "Ch6 WebSphere")</span><span class="sxs-lookup"><span data-stu-id="02a99-114">![Web Sphere](../esb-toolkit/media/ch6-websphere.gif "Ch6-WebSphere")</span></span>  
  
     <span data-ttu-id="02a99-115">**图 2**</span><span class="sxs-lookup"><span data-stu-id="02a99-115">**Figure 2**</span></span>  
  
     <span data-ttu-id="02a99-116">**检查 WebSphere 服务项目中正在运行的队列管理器**</span><span class="sxs-lookup"><span data-stu-id="02a99-116">**Checking that the queue manager is running in the WebSphere Services item**</span></span>  
  
5.  <span data-ttu-id="02a99-117">单击**ReadFile**按钮 RfhUtil 实用程序中，定位到名为测试 000128 的测试消息文件。JMS 位于子文件夹中的名为 \Source\Samples\JMS\Test\Data\Load\\。</span><span class="sxs-lookup"><span data-stu-id="02a99-117">Click the **ReadFile** button in the RfhUtil utility and navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="02a99-118">此文件包含一批 128 测试消息，但该实用程序将加载只有第一个。</span><span class="sxs-lookup"><span data-stu-id="02a99-118">This file contains a batch of 128 test messages, but the utility loads only the first one.</span></span>  
  
6.  <span data-ttu-id="02a99-119">单击**RFH**选项卡上，并确保该唯一**JMS**复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="02a99-119">Click the **RFH** tab, and then make sure that only the **JMS** check box is selected.</span></span>  
  
7.  <span data-ttu-id="02a99-120">单击**jms**选项卡，并请确保所选**回复**队列是 ESB。JMS。示例。DYNAMICQ1，所选**目标队列**是 ESB。JMS。示例。DYNAMICQ2。</span><span class="sxs-lookup"><span data-stu-id="02a99-120">Click the **jms** tab, and then make sure that the selected **Reply To** queue is ESB.JMS.SAMPLE.DYNAMICQ1 and that the selected **Destination Queue** is ESB.JMS.SAMPLE.DYNAMICQ2.</span></span>  
  
8.  <span data-ttu-id="02a99-121">单击**Main**选项卡上，并依次**编写 Q**按钮，将消息写入到队列。</span><span class="sxs-lookup"><span data-stu-id="02a99-121">Click the **Main** tab, and then click the **Write Q** button to write the message into the queue.</span></span>  
  
9. <span data-ttu-id="02a99-122">在延迟后时应用程序执行，ESB 输出消息会出现在 ESB。JMS。示例。DYNAMICQ1 和 ESB。JMS。示例。DYNAMICQ1 队列。</span><span class="sxs-lookup"><span data-stu-id="02a99-122">After a delay while the application executes, the ESB output message appears in the ESB.JMS.SAMPLE.DYNAMICQ1 and ESB.JMS.SAMPLE.DYNAMICQ1 queues.</span></span> <span data-ttu-id="02a99-123">打开 WebSphere 队列资源管理器并浏览队列为确认这一点。</span><span class="sxs-lookup"><span data-stu-id="02a99-123">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>  
  
10. <span data-ttu-id="02a99-124">返回到 RfhUtil 实用工具并连接到的队列以查看消息。</span><span class="sxs-lookup"><span data-stu-id="02a99-124">Go back to the RfhUtil utility and connect to the queues to see the messages.</span></span> <span data-ttu-id="02a99-125">单击**MQMD、 RFH，** 和**jms**选项卡以验证输入和输出值是否为目标队列中的消息不变并回复队列中的消息是相同除外，而不是标准的 JMS 消息，该消息标记为"其他"。</span><span class="sxs-lookup"><span data-stu-id="02a99-125">Click the **MQMD, RFH,** and **jms** tabs to verify that the input and output values are unchanged for the message in the Destination Queue, and that the message in the Reply To queue is the same except that, instead of being a standard JMS message, the message is marked as "other".</span></span>