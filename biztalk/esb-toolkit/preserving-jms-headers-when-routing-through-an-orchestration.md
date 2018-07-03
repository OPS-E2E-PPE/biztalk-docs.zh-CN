---
title: 路由经过业务流程时保留 JMS 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9a59ff3-0cbf-499f-92b2-cf5b808d8b3f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 142bd0d2e5ff86362fe3c3ffa7ef8ec256202708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979710"
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a>路由经过业务流程时保留 JMS 标头
在此用例，组件提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]从传入消息中提取 Java 消息服务 (JMS) 标头，然后将它们重新构造在传出消息中。 本示例演示 JMS 消息标头保留和访问从业务流程中的标头上下文中图 1 所示。  
  
 ![保留 JMS](../esb-toolkit/media/ch3-preservingjms.gif "Ch3-PreservingJMS")  
  
 **图 1**  
  
 **保留 JMS 标头信息的整个 ESB 业务流程和处理**  
  
 JMS MQRFH2 组件示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例和以下三个部分组成：  
  
- 第 1 部分演示完全保真的标头保留，因为在 IBM WebSphere MQ，通过 ESB 和 BizTalk Server 中，并返回到 IBM WebSphere MQ 间传递消息。  
  
- 第 2 部分演示如何在 ESB 业务流程中的代码可以访问 MQRFH2 标头属性。 在这种情况下，代码修改 JMS 标头属性指定目标队列名称。  
  
- 第 3 部分演示大容量加载具有消息的队列，并演示如何在应用程序将消息路由到目标队列指定消息内容的一部分。  
  
  有关详细信息，请参阅[安装和运行 JMS MQRFH2 组件示例](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md)。