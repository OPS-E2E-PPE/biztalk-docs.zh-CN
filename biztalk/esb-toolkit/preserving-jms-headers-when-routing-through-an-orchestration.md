---
title: "通过业务流程路由时保留 JMS 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9a59ff3-0cbf-499f-92b2-cf5b808d8b3f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362f41919a050b08bdba9c70c7771698ab71ce33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a>通过业务流程路由时保留 JMS 标头
在使用这种情况下，组件提供与[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]从传入消息中提取 Java 消息服务 (JMS) 标头，然后将它们重新构造传出消息中。 此示例演示 JMS 消息标头保留并且有权标头的上下文从内部业务流程，如图 1 中所示。  
  
 ![保留 JMS](../esb-toolkit/media/ch3-preservingjms.gif "Ch3 PreservingJMS")  
  
 **图 1**  
  
 **保留在 ESB 业务流程和处理整个 JMS 标头信息**  
  
 附带 JMS MQRFH2 组件示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例，由以下三个部分组成：  
  
-   第 1 部分演示完全保真的标头保留为从 IBM WebSphere MQ，通过 ESB 和 BizTalk Server 中，并返回到 IBM WebSphere MQ 传输一条消息。  
  
-   第 2 部分演示如何 ESB 业务流程中的代码可以访问 MQRFH2 标头属性。 在这种情况下，代码修改 JMS 标头属性指定的目标队列名称。  
  
-   第 3 部分演示大容量加载具有消息的队列，并演示如何应用程序将消息路由到指定的消息内容一部分的目标队列。  
  
 有关详细信息，请参阅[安装和运行 JMS MQRFH2 组件示例](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)。