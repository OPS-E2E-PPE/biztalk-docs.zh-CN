---
title: 示例业务方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c84acde2b7d3049c415954a561c1a53edb16a0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289941"
---
# <a name="sample-business-scenario"></a>示例业务方案
卫生保健进程通常很复杂，涉及到许多系统。 示例是一个患者进入医院，时发生的过程和一名医生将发送的实验室测试患者。 在此过程中所涉及是五个参与方：  
  
- 参加医生  
  
- 医院注册系统  
  
- 临床订单输入系统  
  
- 与实验室系统  
  
- 计费系统  
  
  在此过程中可能会执行以下步骤：  
  
1.  参加医生注册患者。  
  
    1.  ADT ^ O04 注册消息广播的医院注册系统。  
  
    2.  ADT ^ O04 消息接收按订阅消息，包括临床订单输入系统和实验室系统的所有部门。  
  
2.  医生排序从实验室设施诊断研究。  
  
    1.  ORM ^ O01 订单消息的业务规则验证后，从临床订单输入系统中，发送。  
  
    2.  ORM ^ O01 消息由与实验室系统接收。  
  
3.  实验室接收订单，并返回一条确认消息。  
  
    1.  ORR ^ O02 订单确认消息发送实验室系统中，指明可以执行顺序。  
  
    2.  ORR ^ 临床订单输入系统收到 O02 消息。  
  
4.  测试完成后，实验室将结果发送到医生和其他部门。  
  
    1.  ORU ^ 从实验室系统发送 R01 测试结果消息。  
  
    2.  ORU ^ 临床订单输入系统和计费系统接收 R01 消息。  
  
    3.  接口引擎会将电子邮件消息将发送到博士，接收无线 PDA 的实验室结果。  
  
## <a name="the-btahl7-solution"></a>BTAHL7 解决方案  
 上面所述的示例业务方案是卫生保健系统集成所需的示例。 使用 Microsoft BizTalk Accelerator for HL7 MicrosoftBizTalk 服务器 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 为此方案中，具有以下功能提供了解决方案：  
  
1. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 集成的所有参与中心辐射型结构系统。 直接与每个系统进行通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。 它们不需要直接彼此进行通信。  
  
2. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 本机处理 HL7 编码的消息。 无自定义编码是必需的。  
  
3. ADT ^ O04 注册消息广播到所有订阅它的系统。 有关的发布程序-订阅消息传送模型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以灵活地设置和维护系统订阅消息的列表。 可以添加到系统，或将其从删除的订阅列表而不会影响系统的其余部分。  
  
4. 业务规则用于验证 ORM ^ O01 订单消息可以动态更改而不会影响系统的其余部分。  
  
5. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 可以配置为自动生成 ORR ^ O02 订单确认 (ACK) 消息。  
  
6. 如有必要，可以任何用于发送，与其他人的消息进行批处理和批处理内从回执上处理这些事件。  
  
7. 你可以验证所有消息引擎中和对[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]HL7 组织发布 2 X 架构。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何满足业务需求](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)