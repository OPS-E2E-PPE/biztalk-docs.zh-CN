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
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a>运行 JMS MQRFH2 标头保留示例
此示例的这一部分内存一条消息放入 WebSphere 队列。 ESB 拾取此消息，并放到出站 WebSphere 队列。 此示例演示，ESB 和 Microsoft BizTalk 保留完全保真的 RFH2 标头为消息的传输时通过 BizTalk Server。  
  
 **若要运行标头保留示例**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
2.  运行 IBM RfhUtil 实用程序，，然后选择名为 ESB 的队列管理器。JMS。在第一个下拉列表中连接到此队列管理器中的 Sample.QueueManager。  
  
3.  在第二个下拉列表中，选择名为 ESB 的目标出站队列。JMS。示例。SENDTOBIZTALK，如图 1 中所示。  
  
     ![队列管理器](../esb-toolkit/media/ch6-queuemanager.gif "Ch6 QueueManager")  
  
     **图 1**  
  
     **连接到的队列管理器和 RfhUtil 中的出站队列**  
  
4.  如果下拉列表不包含任何队列，请确保队列管理器正在运行通过检查 WebSphere MQ 服务项，如图 2 中所示。  
  
     ![Web 球](../esb-toolkit/media/ch6-websphere.gif "Ch6 WebSphere")  
  
     **图 2**  
  
     **检查 WebSphere 服务项目中正在运行的队列管理器**  
  
5.  单击**ReadFile**按钮 RfhUtil 实用程序中，定位到名为测试 000128 的测试消息文件。JMS 位于子文件夹中的名为 \Source\Samples\JMS\Test\Data\Load\\。 此文件包含一批 128 测试消息，但该实用程序将加载只有第一个。  
  
6.  单击**RFH**选项卡上，并确保该唯一**JMS**复选框处于选中状态。  
  
7.  单击**jms**选项卡，并请确保所选**回复**队列是 ESB。JMS。示例。DYNAMICQ1，所选**目标队列**是 ESB。JMS。示例。DYNAMICQ2。  
  
8.  单击**Main**选项卡上，并依次**编写 Q**按钮，将消息写入到队列。  
  
9. 在延迟后时应用程序执行，ESB 输出消息会出现在 ESB。JMS。示例。DYNAMICQ1 和 ESB。JMS。示例。DYNAMICQ1 队列。 打开 WebSphere 队列资源管理器并浏览队列为确认这一点。  
  
10. 返回到 RfhUtil 实用工具并连接到的队列以查看消息。 单击**MQMD、 RFH，** 和**jms**选项卡以验证输入和输出值是否为目标队列中的消息不变并回复队列中的消息是相同除外，而不是标准的 JMS 消息，该消息标记为"其他"。