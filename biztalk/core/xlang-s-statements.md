---
title: Xlang-s 语句 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 620d0452-a8da-4285-b8b2-5a932ffcde28
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d8abe5514d34bb8fdeb8e465c4c3f30278c4c6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244096"
---
# <a name="xlang-s-statements"></a>Xlang-s 语句
XLANG/s 语句通常分为两个类别之一： 简单语句，对其自身，例如**接收**或**发送**，并包含或组是简单的语句的复杂语句或其他复杂语句，如**作用域**，**并行**，并**侦听**。 每个语句对应于在 BizTalk 业务流程设计器中的业务流程形状。 XLANG/s 定义了以下语句：  
  
-   **group.** 为了方便使用将操作分组为单个可折叠或展开的单元。  
  
-   **send.** 使用指定的消息发送到指定的端口。  
  
-   **receive.** 用于等待接收来自指定端口指定的消息。  
  
-   **端口。** 定义位置和方式传输消息。  
  
-   **角色链接。** 用来创建与同一个逻辑合作伙伴，可能通过不同的传输或终结点进行通信的端口的集合  
  
-   **转换。** 用于将字段从现有消息映射到新消息。  
  
-   **消息赋值。** 使用指定的消息发送到指定的端口。  
  
-   **构造消息。** 定义其中一条消息是创建和初始化的 XLANG/s 代码的块。 现有的消息可以发送到 XLANG/s 程序，但不能构造外创建。 此机制提供消息分发和提供丰富的消息跟踪，因为在所有已知消息状态时间。  
  
-   **调用业务流程。** 以同步方式从一个业务流程调用另一个业务流程。 可以传递参数，并将其返回。  
  
-   **启动业务流程。** 用于启用您的业务流程以异步方式调用其他业务流程。  
  
-   **调用规则。** 可以配置业务规则策略以在您的业务流程中执行。  
  
-   **expression.** XLANG/s 支持丰富的表达式语法，以支持各种使用方案所需的协议定义。 此语句用于分配端口属性、 服务链接属性、 消息、 变量和对象，并调用方法、 属性或静态数据字段。  
  
-   **decide.** 用于有条件地执行多个路径的执行，具体取决于其关联的条件的值之一。  
  
-   **delay.** 用于等待，直到达到一个绝对时间或相对时间。  
  
-   **listen.** 如同**并行**语句**侦听**语句具有多个分支执行路径。 但是，分支必须以开头**延迟**语句或**接收**语句。 执行接收第一次调用的分支。 其他分支**侦听**永远不会执行语句。  
  
-   **并行操作。** 同时执行多个分支的业务流程。 所有分支都处理并行语句后面的任何语句执行之前都完成。  
  
-   **loop.** 重复执行，而其关联的条件将保持为 true。  
  
-   **scope.** 定义变量和将应用于该代码块中的事务性语义的代码块提供上下文。 变量的生存期可限制为该作用域。 事务性语义，如长时间运行，原子的或都不可以应用于一个作用域以影响其行为。  
  
-   **引发异常。** 用于显式调用当前代码块中的异常/错误处理程序。  
  
-   **补偿。** 用于显式调用与给定作用域相关联的补偿模块。 一个**作用域**语句可能拥有与之关联的一个或多个补偿模块。 **补偿**语句将执行定向到所选的补偿模块。  
  
-   **suspend.** 暂时停止执行进程，但可以通过运算符或应用程序重新启动。 与关联的字符串表达式**终止**语句可人员/管理员通过适当的日志或通过用户界面。  
  
-   **终止。** 强制，且不可撤销停止计划中的所有处理。 与关联的字符串表达式**终止**语句可向操作员和管理员通过适当的日志或通过用户界面。  
  
## <a name="see-also"></a>请参阅  
 [业务流程形状](../core/orchestration-shapes.md)   
 [Xlang-s 数据类型](../core/xlang-s-data-types.md)   
 [Xlang-s 变量和运算符](../core/xlang-s-variables-and-operators.md)   
 [Xlang-s 表达式](../core/xlang-s-expressions.md)   
 [Xlang-s 保留字](../core/xlang-s-reserved-words.md)   
 [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)