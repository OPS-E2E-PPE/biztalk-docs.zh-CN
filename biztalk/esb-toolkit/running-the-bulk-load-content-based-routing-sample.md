---
title: "运行大容量加载基于内容的路由示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e981567-7c6c-4c13-bd5b-597efdd3fb50
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c5348563cc52c31b14dbceddf35bdb3d5d94cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a>运行大容量加载基于内容的路由示例
本部分中的示例演示了大容量加载具有 ESB 和 Microsoft BizTalk 将路由到基于每个消息中指定的队列名称的不同目标队列的消息的队列。 它的前面的两个部分中使用你已了解该示例的功能。  
  
 **若要运行基于大容量加载内容的路由访问示例**  
  
1.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
2.  运行 IBM RfhUtil 实用程序，，然后选择名为 ESB 的队列管理器。JMS。在第一个下拉列表中连接到此队列管理器中，如第 2 部分中的此示例中所示的 Sample.QueueManager。  
  
3.  在第二个下拉列表中，选择名为 ESB 的目标出站队列。JMS。示例。SENDTOBIZTALK，如第 2 部分中的此示例中所示。  
  
4.  单击**负载 Q**在 RfhUtil 实用工具中，按钮，然后定位到名为测试 000128 测试消息文件。JMS 位于子文件夹中的名为 \Source\Samples\JMS\Test\Data\Load\\。 此文件包含一批 128 示例会将发送到 ESB 的测试消息。  
  
5.  在**负载**对话框中，保留所有的值设置为其默认值。  
  
6.  在**负载**对话框中，单击**确定**将所有消息添加到输入队列。  
  
7.  在延迟后时应用程序执行，ESB 输出消息出现在不同的目标队列，具体取决于其 JMS 标头中的值。 但是，所有指定同一个答复到队列中，因此所有答复都出现在 ESB。JMS。示例。答复队列。 打开 WebSphere 队列资源管理器并浏览队列为确认这一点。