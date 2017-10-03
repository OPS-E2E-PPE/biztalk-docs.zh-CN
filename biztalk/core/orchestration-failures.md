---
title: "业务流程失败 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Catch Exception block [Orchestration Designer], suspended orchestrations
- HAT, Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], HAT
- orchestrations, troubleshooting [HAT]
- orchestrations, errors
- HAT, Orchestration Debugger
- Orchestration Debugger
- errors, orchestrations
- HAT, troubleshooting orchestrations
- orchestrations, HAT
- HAT, orchestrations
ms.assetid: d0a799fb-7859-4774-b444-979f22f04215
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d95cab903ae9bf5faacdf385f667c33f9a2d5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-failures"></a>业务流程故障
业务流程的复杂性有所不同；例如，业务流程可能通过转换形状和赋值形状来调用 .NET 对象或构造消息。 因此，由于其内容的多样性以及自定义的级别，所以不可能列出每个可能出现的故障。 但是，在业务流程中发生的所有故障都表现为异常。  
  
 如果业务流程不包括任何**CatchException**形状异常，异常会导致业务流程为挂起，但不可恢复的挂起。 这意味着消息和服务实例跟踪或 WMI 脚本无法恢复该实例。 但是，您可使用跟踪（或 WMI 脚本）保存与挂起（不可恢复）实例关联的所有消息，以进行诊断和手动重试。  
  
 若要诊断此类问题，请使用业务流程调试器查看在实例挂起之前执行的最后一个形状。 也可使用业务流程调试器来查看异常的详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [调查业务流程、 端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)   
 [调试业务流程](../core/debugging-an-orchestration.md)