---
title: 如何使用自相关直接绑定端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb651fa-3e35-4598-b229-335448f6919c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fb70074983ed41bb3d5397d08156b6db1201080
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383326"
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a>如何使用自相关直接绑定端口
自相关直接绑定的端口是自引用。 这意味着自相关直接绑定的端口提供了可用于将消息发送回其封闭的业务流程到业务流程的信息。 使用自相关直接绑定时，业务流程引擎将生成消息的特定于业务流程实例的相关的令牌。 这提供了将消息返回到特定的业务流程实例，而无需使用相关集的功能。  
  
 例如，可以创建自相关直接绑定的端口在业务流程 A 中通过指定接收**直接**有关**端口绑定**，然后选择**自相关**端口配置向导中。 然后，在业务流程 B 中，声明为发送端口业务流程的参数相同的端口类型的端口在业务流程 A 中定义为此，请执行以下操作：  
  
1. 在业务流程视图窗口中，右键单击**业务流程参数**，然后单击**新建端口参数**。  
  
2. 在属性窗口中的**通信方向**，选择**发送**，并为**端口类型**，选择相同的端口类型，如业务流程 A 中定义  
  
   此声明在业务流程设计器中的端口图面上创建逻辑发送端口。 业务流程 A 调用业务流程 B 使用**启动业务流程**形状并将新端口作为参数，以及其他业务流程参数，传递给业务流程 b。 业务流程 B，然后执行其业务逻辑并将消息传递的新端口上向其发送。 将消息发送到接收自相关直接绑定端口的实例的业务流程的启动业务流程 b。  
  
   尽管也可以使用实现事件的上述顺序**调用业务流程**形状，它仅使用时非常有用**启动业务流程**形状。 这是因为使用时**调用业务流程**形状，端口按引用传递。 该端口的极性必须在两个业务流程相同。 因此，从一个业务流程中传递的端口通信方向必须与调用的业务流程中的端口引用的方向相同。 但是，使用时**启动业务流程**形状，生成的业务流程异步实例化，而且不能包含**Out**或**Ref**参数;因此，自相关直接绑定的端口提供业务流程将响应返回至其进行实例化的业务流程实例的方法。  
  
   有关如何使用自相关直接绑定的端口的示例，请参阅 SDK 示例"实现分散和收集模式"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 MessageBox 直接绑定端口](../core/how-to-use-messagebox-direct-bound-ports.md)   
 [如何使用合作伙伴业务流程直接绑定端口](../core/how-to-use-partner-orchestration-direct-bound-ports.md)