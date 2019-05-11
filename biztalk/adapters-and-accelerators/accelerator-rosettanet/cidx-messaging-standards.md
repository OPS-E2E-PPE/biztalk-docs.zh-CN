---
title: CIDX 消息传送标准 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a39b76ef67374796d9ba569a50e7d5357dac819d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284858"
---
# <a name="cidx-messaging-standards"></a>CIDX 消息传送标准
CIDX （化工行业数据交换） 表示，它支持和维护的标准化的消息交换 Chem eStandards 的标准组织。 化工行业中的公司对其特定于行业的消息传送需求都使用这些标准。  
  
 CIDX 已采用 RosettaNet 实现框架 (RNIF) 消息传递层来实现 XML 文档的交换。 CIDX 不已采用的 RNIF 标准的公用流程层。  
  
 Chem eStandards 定义描述系统交换的消息的服务内容的 XML 文档类型定义 (Dtd)。 该消息是在结构中，具有服务内容和一些标头值之间的差异的 RNIF 1.1 RosettaNet 对象相同。 当有标准 CIDX 与 RosettaNet 消息相匹配时，CIDX 标准采用 RosettaNet 元素名称和数据结构。  
  
 CIDX 具有传统上用于电子文档交换 (EDI) 消息交换，但具有格式正确的一组新的基于 XML 技术的文档。 Chem eStandards 提供 EDI 消息的 XML 的副本。  
  
 Chem eStandards 创建各个消息的每个业务事务。 Chem eStandards 使用两种类型的消息响应： 技术响应以及事务响应。 对于安全和可靠消息传送，Chem eStandards 仅使用 RNIF 1.1 的通知类型处理。 Chem eStandards 不要使用合作伙伴接口流程 (PIP) 0A1。  
  
## <a name="cidx-and-rosettanet-differences"></a>CIDX 与 RosettaNet 差异  
 下表显示了一些 RosettaNet 和 CIDX 之间的差异。  
  
|RosettaNet 实现|CIDX 实现|  
|-------------------------------|-------------------------|  
|RosettaNet 使用"应用程序/X-rosettanet"作为多用途 Internet 邮件扩展 (MIME) 类型。|CIDX 使用"应用程序/X-chemxml"作为 MIME 类型。|  
|RosettaNet 标头的 RosettaNet 使用 GlobalAdministeringAuthorityCode = RosettaNet|CIDX 使用 GlobalAdministeringAuthorityCode = CIDX|  
|RosettaNet 支持单操作和双操作消息。|CIDX 支持仅单操作消息。|  
|RosettaNet 支持的 PIP 0A1 （失败通知）。|CIDX 不支持的 PIP 0A1。|  
|RosettaNet 消息可以是事务或通知的类型。|所有 CIDX 消息都都会的通知类型。|  
|在 RosettaNet，必须从 PIP 规范派生 PIP 配置设置。|在 CIDX，必须从 CIDX Chem eStandards 规范派生 PIP 配置设置。|  
  
## <a name="see-also"></a>请参阅  
 [RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RNIF 标准](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)   
 [RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)   
 [CIDX 支持](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)