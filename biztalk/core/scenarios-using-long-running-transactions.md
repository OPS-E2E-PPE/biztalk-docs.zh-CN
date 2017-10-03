---
title: "使用长时间运行事务的方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transactions, long-running
- long-running transactions, timeouts
- transactions, examples
- long-running transactions, examples
- long-running compensations
- examples, long-running transactions
- examples, custom compensations
ms.assetid: 76b3e0f8-44dc-419e-a73a-c2908b1d8795
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05ac14bc6e333f963dda7cb9b33d1ebf371c0546
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenarios-using-long-running-transactions"></a>使用长期事务的方案
下面的方案介绍如何使用长期事务。  
  
## <a name="scenario-1-using-long-running-transactions-with-timeouts"></a>方案 1： 使用与超时长时间运行事务  
 长期作用域可与某一超时关联，超时是长期工作必须在此时间范围内完成的逻辑时间。 如果未指定的时间，预定义的系统异常内完成，作用域**TimeoutException**引发。  
  
 您可以通过将整个业务流程标记为长期的，或者通过让外部长期作用域嵌套任何其他作用域，创建长期进程。 在前一个方案中，系统提供的异常处理程序将运行，而后一个方案则允许特定的异常处理程序与外部作用域相关联。 默认的系统提供的异常处理程序将为每个成功完成的嵌套事务性作用域（如果有）运行补偿处理程序，运行顺序与其完成顺序相反。 您可以通过在异常处理程序中将补偿形状用于长期事务，通过自补偿实现同一任务。  
  
 下面的业务流程介绍如何将超时与长期事务相关联。  
  
 **使用超时值的长时间运行事务**  
  
 ![使用超时长时间运行事务](../core/media/bts-trans-orch-fig7.gif "BTS_Trans_Orch_Fig7")  
  
 有时候，您可能需要连接以批处理形式操作的旧式系统。 此方案显示了一个要接收并发送到旧式系统的采购订单。 此旧式系统处理该采购订单，并且发送回采购订单确认。 该发送操作采用采购订单号初始化某一相关集，并且接收操作将遵循该相关集。 该接收操作还处于具有超时值的长期作用域中。  
  
 业务流程引擎将冻结正等待接收的业务流程实例。 相关将确保在接收消息后调用同一业务流程实例。 如果购买订单确认没有超时值，通过指定的时间间隔内到达**TimeoutException**将引发。  
  
## <a name="scenario-2-using-long-running-transactions-with-custom-compensation"></a>方案 2： 使用与自定义补偿长时间运行事务  
 以下业务流程阐释如何关联自定义补偿以及调用与整个业务流程相关联的自定义补偿。 此方案将插入一个新客户以及插入该客户的订单明细。 业务流程的逻辑规定如果订单插入失败，您应该回滚该客户插入。 该客户插入可由旧式系统执行，因此，在单独的可调用业务流程中阐释。 调用的业务流程已**自定义**属性设置为提供单独的工作表进行补偿过程的补偿。 该补偿是要删除新插入的客户。  
  
 调用业务流程具有要执行订单插入的长期作用域。 此作用域嵌套在某一外部长期作用域中。 该外部作用域具有关联的异常处理程序，以便捕获任何异常。 该处理程序使用补偿形状来定义与调用的业务流程相关联的自定义异常，以便回滚在对业务流程的调用中可能发生的任何更改。  
  
 **使用自定义补偿的长时间运行事务**  
  
 ![长时间运行事务，使用自定义补偿](../core/media/bts-trans-orch-fig8.gif "BTS_Trans_Orch_Fig8")  
  
 **调用的业务流程 （主）**  
  
 ![调用 orchestration &#40; main &#41;] (../core/media/bts-trans-orch-fig9.gif "BTS_Trans_Orch_Fig9")  
  
 **调用的业务流程 （补偿）**  
  
 ![调用 orchestration &#40; 补偿 &#41;] (../core/media/bts-trans-orch-fig10.gif "BTS_Trans_Orch_Fig10")