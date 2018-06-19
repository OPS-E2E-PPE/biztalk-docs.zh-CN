---
title: 运行大容量加载基于内容的路由示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e981567-7c6c-4c13-bd5b-597efdd3fb50
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c5348563cc52c31b14dbceddf35bdb3d5d94cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294941"
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a><span data-ttu-id="cf587-102">运行大容量加载基于内容的路由示例</span><span class="sxs-lookup"><span data-stu-id="cf587-102">Running the Bulk Load Content-Based Routing Sample</span></span>
<span data-ttu-id="cf587-103">本部分中的示例演示了大容量加载具有 ESB 和 Microsoft BizTalk 将路由到基于每个消息中指定的队列名称的不同目标队列的消息的队列。</span><span class="sxs-lookup"><span data-stu-id="cf587-103">This part of the sample demonstrates bulk loading a queue with messages that the ESB and Microsoft BizTalk will route to different destination queues based on the queue name specified in each message.</span></span> <span data-ttu-id="cf587-104">它的前面的两个部分中使用你已了解该示例的功能。</span><span class="sxs-lookup"><span data-stu-id="cf587-104">It uses the features of the sample that you have seen in the previous two parts.</span></span>  
  
 <span data-ttu-id="cf587-105">**若要运行基于大容量加载内容的路由访问示例**</span><span class="sxs-lookup"><span data-stu-id="cf587-105">**To run the Bulk Load Content-based Routing Access sample**</span></span>  
  
1.  <span data-ttu-id="cf587-106">如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="cf587-106">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="cf587-107">运行 IBM RfhUtil 实用程序，，然后选择名为 ESB 的队列管理器。JMS。在第一个下拉列表中连接到此队列管理器中，如第 2 部分中的此示例中所示的 Sample.QueueManager。</span><span class="sxs-lookup"><span data-stu-id="cf587-107">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager, as in Part 2 of this sample.</span></span>  
  
3.  <span data-ttu-id="cf587-108">在第二个下拉列表中，选择名为 ESB 的目标出站队列。JMS。示例。SENDTOBIZTALK，如第 2 部分中的此示例中所示。</span><span class="sxs-lookup"><span data-stu-id="cf587-108">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as in Part 2 of this sample.</span></span>  
  
4.  <span data-ttu-id="cf587-109">单击**负载 Q**在 RfhUtil 实用工具中，按钮，然后定位到名为测试 000128 测试消息文件。JMS 位于子文件夹中的名为 \Source\Samples\JMS\Test\Data\Load\\。</span><span class="sxs-lookup"><span data-stu-id="cf587-109">Click the **Load Q** button in the RfhUtil utility, and then navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="cf587-110">此文件包含一批 128 示例会将发送到 ESB 的测试消息。</span><span class="sxs-lookup"><span data-stu-id="cf587-110">This file contains a batch of 128 test messages that the sample will send to the ESB.</span></span>  
  
5.  <span data-ttu-id="cf587-111">在**负载**对话框中，保留所有的值设置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="cf587-111">In the **Load** dialog box, leave all values set to their default values.</span></span>  
  
6.  <span data-ttu-id="cf587-112">在**负载**对话框中，单击**确定**将所有消息添加到输入队列。</span><span class="sxs-lookup"><span data-stu-id="cf587-112">In the **Load** dialog box, click **OK** to add all the messages to the input queue.</span></span>  
  
7.  <span data-ttu-id="cf587-113">在延迟后时应用程序执行，ESB 输出消息出现在不同的目标队列，具体取决于其 JMS 标头中的值。</span><span class="sxs-lookup"><span data-stu-id="cf587-113">After a delay while the application executes, the ESB output messages appear in various destination queues, depending on the values in their JMS headers.</span></span> <span data-ttu-id="cf587-114">但是，所有指定同一个答复到队列中，因此所有答复都出现在 ESB。JMS。示例。答复队列。</span><span class="sxs-lookup"><span data-stu-id="cf587-114">However, all specify the same Reply To queue, so all the replies appear in the ESB.JMS.SAMPLE.REPLY queue.</span></span> <span data-ttu-id="cf587-115">打开 WebSphere 队列资源管理器并浏览队列为确认这一点。</span><span class="sxs-lookup"><span data-stu-id="cf587-115">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>