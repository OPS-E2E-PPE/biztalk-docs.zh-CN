---
title: "示例业务方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a74fafbac364469b1afdba5365c2af87cc4fa2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-business-scenario"></a>示例业务方案
卫生保健进程通常很复杂且涉及许多系统。 一个示例是一个患者进入医院时发生的过程并医生发送实验室测试将患者。 在此过程中涉及是五个方：  
  
-   越过医生  
  
-   医院注册系统  
  
-   临床订单输入系统  
  
-   与实验室系统  
  
-   计费系统  
  
 在此过程中可能会执行以下步骤：  
  
1.  越过 doctor 注册患者。  
  
    1.  ADT ^ O04 注册消息广播医院注册系统。  
  
    2.  ADT ^ O04 消息接收的所有订阅的消息，包括临床订单输入系统和与实验室系统的部门。  
  
2.  Doctor 排序从实验室设施诊断研究。  
  
    1.  ORM ^ O01 订单消息的业务规则验证之后，从临床订单输入系统，发送。  
  
    2.  ORM ^ 与实验室系统收到 O01 消息。  
  
3.  实验室接收顺序，并返回一条确认消息。  
  
    1.  ORR ^ O02 订单确认消息发送实验室系统，指示可以执行顺序。  
  
    2.  ORR ^ 临床订单输入系统收到 O02 消息。  
  
4.  在完成的测试实验室将结果发送到 doctor 和其他部门。  
  
    1.  ORU ^ 从与实验室系统发送 R01 测试结果消息。  
  
    2.  ORU ^ R01 消息接收临床订单输入系统和计费系统。  
  
    3.  接口引擎将出一封电子邮件发送到 doctor，接收其无线 PDA 上的实验室结果。  
  
## <a name="the-btahl7-solution"></a>BTAHL7 解决方案  
 上述示例业务方案是卫生保健系统集成所需的一个示例。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]与[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 为此应用场景，具有以下功能提供了解决方案：  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成所有中心辐射型结构中所涉及的系统。 每个系统直接与通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 它们无需直接相互通信。  
  
2.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]本机处理 HL7 编码消息。 无需进行自定义编码是必需的。  
  
3.  ADT ^ O04 注册消息广播到所有订阅它的系统。 有关的发行者-订户消息传送模型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以灵活地设置和维护订阅到消息的系统的列表。 你可以添加到系统，或将其从订阅列表删除而不会影响系统的其余部分。  
  
4.  用于验证 ORM 的业务规则 ^ O01 订单消息可以动态更改而不会影响系统的其余部分。  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以配置为自动生成 ORR ^ O02 订单确认 (ACK) 消息。  
  
6.  如有必要，你可以批处理任何用于发送，与其他消息，然后在批处理中从回执上处理它们。  
  
7.  你可以验证所有消息在引擎和针对[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 X 架构发布的 HL7 组织。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 如何解决的业务需要](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)