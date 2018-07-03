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
ms.openlocfilehash: eaad102db33b4967c89cb78f944b93a688e4c213
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982318"
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a>如何使用自相关直接绑定端口
自相关直接绑定端口是自引用的。 这表明自相关直接绑定端口提供了可用于将消息发送回其封闭业务流程的信息。 使用自相关直接绑定时，业务流程引擎对特定于业务流程实例的消息生成一个相关标记。 这提供了在不使用相关集的情况下将消息返回到特定业务流程实例的能力。  
  
 例如，可以创建自相关直接绑定的端口在业务流程 A 中通过指定接收**直接**有关**端口绑定**，然后选择**自相关**端口配置向导中。 然后，在业务流程 B 中，将某个端口声明为业务流程 A 中定义的具有相同端口类型的发送端口业务流程参数。为此，请执行以下操作：  
  
1. 在业务流程视图窗口中，右键单击**业务流程参数**，然后单击**新建端口参数**。  
  
2. 在属性窗口中的**通信方向**，选择**发送**，并为**端口类型**，选择相同的端口类型，如业务流程 A 中定义  
  
   该声明将在业务流程设计器中的端口图面上创建一个逻辑发送端口。 业务流程 A 调用业务流程 B 使用**启动业务流程**形状并将新端口作为参数，以及其他业务流程参数，传递给业务流程 b。 业务流程 B，然后执行其业务逻辑并将消息传递的新端口上向其发送。 此消息发送到启动了业务流程 B 的业务流程 A 实例的用于接收的自相关直接绑定端口。  
  
   尽管也可以使用实现事件的上述顺序**调用业务流程**形状，它仅使用时非常有用**启动业务流程**形状。 这是因为使用时**调用业务流程**形状，端口按引用传递。 端口的极性在这两个业务流程中必须相同。 因此，从一个业务流程中传入的端口的通信方向必须与所调用业务流程中端口引用的方向相同。 但是，使用时**启动业务流程**形状，生成的业务流程异步实例化，而且不能包含**Out**或**Ref**参数;因此，自相关直接绑定的端口提供业务流程将响应返回至其进行实例化的业务流程实例的方法。  
  
   有关如何使用自相关直接绑定的端口的示例，请参阅 SDK 示例"实现分散和收集模式"网址[ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>请参阅  
 [如何使用 MessageBox 直接绑定端口](../core/how-to-use-messagebox-direct-bound-ports.md)   
 [如何使用合作伙伴业务流程直接绑定端口](../core/how-to-use-partner-orchestration-direct-bound-ports.md)