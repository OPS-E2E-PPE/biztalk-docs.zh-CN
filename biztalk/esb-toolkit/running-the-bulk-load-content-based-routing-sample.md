---
title: 运行大容量加载基于内容的路由示例 |Microsoft Docs
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
ms.openlocfilehash: d2c9f3bac1c74ba867a4ef6570ff7c1b44e961d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292527"
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a><span data-ttu-id="13432-102">运行大容量加载基于内容的路由示例</span><span class="sxs-lookup"><span data-stu-id="13432-102">Running the Bulk Load Content-Based Routing Sample</span></span>
<span data-ttu-id="13432-103">本部分的示例演示了大容量加载具有 ESB 和 Microsoft BizTalk 将路由到基于每个消息中指定的队列名称的不同目标队列的消息的队列。</span><span class="sxs-lookup"><span data-stu-id="13432-103">This part of the sample demonstrates bulk loading a queue with messages that the ESB and Microsoft BizTalk will route to different destination queues based on the queue name specified in each message.</span></span> <span data-ttu-id="13432-104">在前面的两个部分中，它使用您已经看到了示例的功能。</span><span class="sxs-lookup"><span data-stu-id="13432-104">It uses the features of the sample that you have seen in the previous two parts.</span></span>  
  
 <span data-ttu-id="13432-105">**若要运行大容量加载内容基于路由的访问权限示例**</span><span class="sxs-lookup"><span data-stu-id="13432-105">**To run the Bulk Load Content-based Routing Access sample**</span></span>  
  
1.  <span data-ttu-id="13432-106">如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。</span><span class="sxs-lookup"><span data-stu-id="13432-106">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="13432-107">运行 IBM RfhUtil 实用工具，然后选择名为 ESB 的队列管理器。JMS。若要连接到此队列管理器中，如本示例的第 2 部分中所示的第一个下拉列表 Sample.QueueManager。</span><span class="sxs-lookup"><span data-stu-id="13432-107">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager, as in Part 2 of this sample.</span></span>  
  
3.  <span data-ttu-id="13432-108">在第二个下拉列表中，选择名为 ESB 的出站目标队列。JMS。示例。SENDTOBIZTALK，如本示例的第 2 部分中所示。</span><span class="sxs-lookup"><span data-stu-id="13432-108">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as in Part 2 of this sample.</span></span>  
  
4.  <span data-ttu-id="13432-109">单击**负载 Q**在 RfhUtil 实用程序中，按钮，然后定位到名为测试 000128 测试消息文件。位于名为 \Source\Samples\JMS\Test\Data\Load 子文件夹中的 JMS\\。</span><span class="sxs-lookup"><span data-stu-id="13432-109">Click the **Load Q** button in the RfhUtil utility, and then navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="13432-110">此文件包含该示例会将发送到 ESB 的 128 测试消息的批处理。</span><span class="sxs-lookup"><span data-stu-id="13432-110">This file contains a batch of 128 test messages that the sample will send to the ESB.</span></span>  
  
5.  <span data-ttu-id="13432-111">在中**负载**对话框中，将保留所有值都设置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="13432-111">In the **Load** dialog box, leave all values set to their default values.</span></span>  
  
6.  <span data-ttu-id="13432-112">在中**负载**对话框中，单击**确定**将所有消息添加到输入队列。</span><span class="sxs-lookup"><span data-stu-id="13432-112">In the **Load** dialog box, click **OK** to add all the messages to the input queue.</span></span>  
  
7.  <span data-ttu-id="13432-113">在延迟后时的应用程序执行，ESB 输出消息将显示在不同的目标队列，具体取决于其 JMS 标头中的值。</span><span class="sxs-lookup"><span data-stu-id="13432-113">After a delay while the application executes, the ESB output messages appear in various destination queues, depending on the values in their JMS headers.</span></span> <span data-ttu-id="13432-114">但是，所有指定同一个答复队列，因此所有答复都出现在 ESB。JMS。示例。答复队列。</span><span class="sxs-lookup"><span data-stu-id="13432-114">However, all specify the same Reply To queue, so all the replies appear in the ESB.JMS.SAMPLE.REPLY queue.</span></span> <span data-ttu-id="13432-115">打开 WebSphere 队列资源管理器并浏览队列来确认这一点。</span><span class="sxs-lookup"><span data-stu-id="13432-115">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>