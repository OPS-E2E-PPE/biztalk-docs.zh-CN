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
# <a name="running-the-bulk-load-content-based-routing-sample"></a>运行大容量加载基于内容的路由示例
本部分的示例演示了大容量加载具有 ESB 和 Microsoft BizTalk 将路由到基于每个消息中指定的队列名称的不同目标队列的消息的队列。 在前面的两个部分中，它使用您已经看到了示例的功能。  
  
 **若要运行大容量加载内容基于路由的访问权限示例**  
  
1.  如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  
  
2.  运行 IBM RfhUtil 实用工具，然后选择名为 ESB 的队列管理器。JMS。若要连接到此队列管理器中，如本示例的第 2 部分中所示的第一个下拉列表 Sample.QueueManager。  
  
3.  在第二个下拉列表中，选择名为 ESB 的出站目标队列。JMS。示例。SENDTOBIZTALK，如本示例的第 2 部分中所示。  
  
4.  单击**负载 Q**在 RfhUtil 实用程序中，按钮，然后定位到名为测试 000128 测试消息文件。位于名为 \Source\Samples\JMS\Test\Data\Load 子文件夹中的 JMS\\。 此文件包含该示例会将发送到 ESB 的 128 测试消息的批处理。  
  
5.  在中**负载**对话框中，将保留所有值都设置为其默认值。  
  
6.  在中**负载**对话框中，单击**确定**将所有消息添加到输入队列。  
  
7.  在延迟后时的应用程序执行，ESB 输出消息将显示在不同的目标队列，具体取决于其 JMS 标头中的值。 但是，所有指定同一个答复队列，因此所有答复都出现在 ESB。JMS。示例。答复队列。 打开 WebSphere 队列资源管理器并浏览队列来确认这一点。