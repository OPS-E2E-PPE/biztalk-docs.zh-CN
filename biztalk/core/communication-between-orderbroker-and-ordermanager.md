---
title: OrderBroker 和 OrderManager 之间的通信 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, publishing [MessageBox database]
- MessageBox database, publishing
ms.assetid: 1b77dcd2-f7a5-4013-b9a2-c06ace161792
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f438b0dfe744aae5867943f4b1493bb163994f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231869"
---
# <a name="communication-between-orderbroker-and-ordermanager"></a>OrderBroker 和 OrderManager 之间的通信
顺序 broker 和顺序 manager 业务流程 (**OrderBroker**， **OrderManager**) 通过 MessageBox 数据库，而不是直接合作伙伴绑定进行通信。 这可确保，在以便它们，如有必要，可以在不同的 BizTalk 组和地理位置的位置所在松散耦合的代理和管理器。 分隔这种方式的业务流程需要仅管理配置，并不需要的任何代码更改。  
  
 在解决方案中为当前配置，顺序 broker 将消息标记为特定的顺序管理器，并将它们发送到 MessageBox。 反过来，订单管理器为适用于它的消息筛选器，并从 MessageBox 所需的这些消息。 这种间接方式 — 通过 MessageBox 通信，而不是直接绑定-可以轻松地移动到单独的组的代理和管理器。  
  
 如果没有负责维护的代理和管理器的不同组，或者如果它们需要处于不同的地理位置，设计可以轻松地适应这。 你需要执行操作的只是将业务流程移到不同的 BizTalk 组。 业务流程都位于不同的组后，重新连接它们只需创建端口。 在顺序 broker 组中，你必须创建具有相同筛选器设置为顺序管理器中，但，将消息转发到新组发送端口。 在订单管理器组中，你必须创建接收端口接收消息并将其放在 MessageBox 数据库中。  
  
 你可以通过导出创建 MSI 文件，每个代理和管理器用于移动应用程序。 有关导出应用程序的详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
## <a name="see-also"></a>另请参阅  
 [实现突出显示的业务流程管理解决方案](../core/implementation-highlights-of-the-business-process-management-solution.md)