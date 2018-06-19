---
title: 在业务流程中的持久性 |Microsoft 文档
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
ms.openlocfilehash: af73db551ced1206ac316f0ba15b8c90a7d5053f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264589"
---
# <a name="persistence-in-orchestrations"></a>在业务流程中的持久性
业务流程引擎将保存业务流程实例在不同持久化点时的整个状态，以便可以解除冻结业务流程实例。 该状态包括可在业务流程中使用的所有基于 .NET 的组件以及消息和变量。 该引擎存储处于以下持久化点时的状态：  
  
-   事务作用域（原子事务或长期事务）结束时  
  
-   在调试断点时  
  
-   在通过启动业务流程形状执行其他业务流程时  
  
-   在发送形状上（原子事务中除外）  
  
-   在挂起业务流程实例时  
  
-   在系统以可控方式关闭时  
  
-   在引擎确定它要解除冻结时  
  
-   在业务流程实例完成时  
  
 引擎在持久化点占用高昂系统资源（尤其是在处理大消息）时优化持久化点的数目。 如下面的两个业务流程实例所示，在原子作用域中含发送形状的业务流程中，引擎确定事务作用域结束和业务流程结束之间的单个持久化点。 在其他业务流程中，存在两个持久化点，一个用于第一个发送形状，第二个用于发送形状外加业务流程结束。  
  
 **业务流程持久性**  
  
 ![业务流程持久性](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")  
  
 在业务流程中使用的任何基于 .NET 的对象（无论是直接的还是间接的）都必须标记为可序列化，但以下情况除外：对象在原子作用域中被调用，或者对象是无状态的并且只通过静态方法调用。 **System.Xml.XmlDocument**是一种特殊情况，不需要将标记为可序列化而不考虑一个作用域的事务属性。  
  
 如何进行特殊处理**System.Xml.XmlDocument**工作：  
  
 当用户定义变量**X**类型的**T**，其中**T**是**System.Xml.XmlDocument**或从派生的类**System.Xml.XmlDocument**则编译器会将**X**作为可序列化对象。  
  
 在序列化时**X**，运行时将保留以下几部分信息: （a） 的实际类型**Tr**的对象**X**引用 （b) **OuterXml**文档的字符串。  
  
 在反序列化时**X**，运行时将创建的实例**Tr** （假设不采用任何参数的构造函数），将调用**LoadXml**提供使用已保存的实例**OuterXml。X**然后将设置为指向新创建的实例的**Tr**。  
  
## <a name="see-also"></a>另请参阅  
 [中的](../core/transactions.md)