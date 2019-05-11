---
title: OrderBroker 和 OrderManager 之间的通信 |Microsoft Docs
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
ms.openlocfilehash: 43af6f47a53f28875b77b5089ffe2d343681f140
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357109"
---
# <a name="communication-between-orderbroker-and-ordermanager"></a>OrderBroker 和 OrderManager 之间的通信
Orderbroker 和订单管理器业务流程 (**OrderBroker**， **OrderManager**) 通过 MessageBox 数据库，而不是直接合作伙伴绑定进行通信。 这可确保，将 broker 与 manager 松散耦合的以便它们，如有必要，可以位于单独的 BizTalk 组和地理位置上相隔位置。 这种方式分离业务流程要求仅管理配置，不需要更改任何代码。  
  
 在目前配置解决方案中，顺序 broker 将消息标记为特定订单管理器，并将它们发送到 MessageBox。 反过来，订单管理器筛选的消息发送给它，并从 MessageBox 获取这些消息。 这种间接方式 — 通过 MessageBox 进行通信，而不是直接绑定 — 轻松地移动到单独的组的代理和管理器。  
  
 如果负责维护将 broker 与 manager 是不同的组，或者它们必须能够在不同的地理位置，设计轻松为解决此问题。 需要做的就是将业务流程移到不同的 BizTalk 组。 业务流程都位于单独的组后，重新连接它们只需要创建端口。 在顺序 broker 组中，必须创建具有相同的筛选器为订单管理器，但是，将消息转发到新组的发送端口。 在订单管理器组中，必须创建接收端口的接收消息，并将其放入 MessageBox 数据库。  
  
 可以通过导出创建 MSI 文件，分别用于将 broker 与 manager 移动应用程序。 有关导出应用程序的详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [业务流程管理解决方案的实施重点](../core/implementation-highlights-of-the-business-process-management-solution.md)