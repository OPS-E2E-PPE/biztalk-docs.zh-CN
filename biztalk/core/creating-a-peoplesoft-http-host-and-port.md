---
title: 创建 PeopleSoft HTTP 主机和端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP port
- HTTP host
ms.assetid: 3e1ce5fd-32ee-409f-b4c8-f2bc68470f17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d991642b45a636c50ea12148d07efd8b93917754
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997158"
---
# <a name="creating-a-peoplesoft-http-host-and-port"></a>创建 PeopleSoft HTTP 主机和端口
PeopleSoft 中的消息发布体系结构称为 Integration Broker。 Integration Broker 的主要组件如下所示：  
  
- 网关  
  
- 发布节点  
  
- 订户节点  
  
  这三个组件协同工作将消息发布到 HTTP 侦听器的 URL。 您必须设置发布节点。 PeopleSoft 有一个默认发布节点，也称为本地消息节点。 您必须激活该节点和发布节点事务。 您必须将订阅节点的类型设置为外部节点，然后激活该节点和事务。 对于该节点，也可以将类型设置为 HTTP 并设置连接信息。  
  
  可使用 PeopleSoft Integration Broker 创建 PeopleSoft 用来发送事件的 PeopleSoft HTTP 主机和端口。 请确保消息处于活动状态且路由，通过使用中的过程[如何验证消息的活动状态](../core/how-to-verify-activity-status-of-a-message.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何验证消息的活动状态](../core/how-to-verify-activity-status-of-a-message.md)  
  
-   [如何配置集成网关和 HTTP 输出连接器](../core/how-to-configure-the-integration-gateway-and-http-output-connector.md)  
  
-   [如何创建新的网关节点](../core/how-to-create-a-new-gateway-node.md)  
  
-   [如何添加事务](../core/how-to-add-a-transaction.md)  
  
-   [如何测试 HTTP 节点](../core/how-to-test-the-http-node.md)