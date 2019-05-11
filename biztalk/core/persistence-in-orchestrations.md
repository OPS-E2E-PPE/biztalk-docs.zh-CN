---
title: 业务流程的持久性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, persistence
- persistence
- BizTalk Server Orchestration Engine
ms.assetid: 2f79d294-f7df-4d84-ba76-50618506b6c6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee984e3dab85cf9a1efb7a28864c85c9abac918
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395799"
---
# <a name="persistence-in-orchestrations"></a>业务流程的持久性
业务流程引擎将保存在不同持久化点，以便可以解除冻结的业务流程实例的业务流程实例的整个状态。 状态包括任何。可以用于在业务流程，此外消息和变量的基于网络的组件。 该引擎存储在以下持久化点的状态：  
  
- 事务作用域 （原子或长时间运行） 的末尾  
  
- 在调试断点  
  
- 在执行其他业务流程通过启动业务流程形状  
  
- 在发送形状 （原子事务中除外）  
  
- 挂起业务流程实例时  
  
- 当系统关闭以受控的方式  
  
- 在引擎确定它要解除冻结  
  
- 完成业务流程实例  
  
  引擎会暂留点的数量进行优化，因为它们是开销很大，尤其是在处理大消息大小。 下面，使用原子作用域中的发送形状在业务流程中的两个业务流程实例中所示，引擎确定事务作用域结束和业务流程结束之间的单个持久化点。 在另一个业务流程，将有两个持久化点，一个用于第一个发送形状，第二个用于发送形状外加业务流程结束。  
  
  **业务流程持久化**  
  
  ![业务流程持久化](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")  
  
  任何。在业务流程中使用的基于网络的对象直接或间接必须标记为可序列化除非在原子作用域中调用它们，或如果对象是无状态，并且只通过静态方法调用。 **System.Xml.XmlDocument**是一种特殊情况，不需要将标记为可序列化而不考虑作用域的事务属性。  
  
  如何进行特殊处理**System.Xml.XmlDocument**工作：  
  
  当用户定义的变量**X**类型的**T**，其中**T**是**System.Xml.XmlDocument**派生一个类或**System.Xml.XmlDocument**然后，编译器会将**X**作为可序列化对象。  
  
  序列化时**X**，运行时将保留以下几部分信息: （a） 的实际类型**Tr**对象的**X**引用的 （b) **OuterXml**文档的字符串。  
  
  当反序列化**X**，在运行时将创建的一个实例**Tr** （假设不采用任何参数的构造函数），并将调用**LoadXml**提供使用已保存的实例**OuterXml。X**然后将设置为指向新创建的实例**Tr**。  
  
## <a name="see-also"></a>请参阅  
 [中的](../core/transactions.md)