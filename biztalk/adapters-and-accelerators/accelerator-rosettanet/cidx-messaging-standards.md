---
title: "消息传送标准 CIDX |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CIDX, RosettaNet
- RosettaNet, CIDX
ms.assetid: 6f70fa56-1fc3-4016-ac9e-6af18026292a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d37cd02f92a8a13857071d0b3d84ab40c480787
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="cidx-messaging-standards"></a>CIDX 消息传送标准
作为标准组织支持和维护的标准化的消息交换 Chem eStandards 操作 CIDX （筛选行业数据交换）。 筛选行业中的公司为其特定于行业的消息传递需求使用这些标准。  
  
 CIDX 已采用 RosettaNet 实现框架 (RNIF) 在消息传递层实现 XML 文档的交换。 CIDX 未采用 RNIF 标准公共进程层。  
  
 Chem eStandards 定义描述系统交换的消息的服务内容的 XML 文档类型定义 (Dtd)。 消息已在结构中，具有服务内容和某些标头值之间的差异的 RNIF 1.1 RosettaNet 对象相同。 如果没有 CIDX 标准和 RosettaNet 消息之间匹配，CIDX 标准采用 RosettaNet 元素名称和数据结构。  
  
 CIDX 具有传统上用于电子文档交换 (EDI) 消息交换，但建立了一组新的基于 XML 技术的文档。 Chem eStandards 提供 XML 的 EDI 消息的副本。  
  
 Chem eStandards 创建每个业务事务的单个的消息。 Chem eStandards 使用两种类型的消息响应： 技术响应和事务响应。 对于安全、 可靠消息传递，Chem eStandards 只能使用 RNIF 1.1 的通知类型进程。 Chem eStandards 不使用合作伙伴接口过程 (PIP) 0A1。  
  
## <a name="cidx-and-rosettanet-differences"></a>CIDX 和 RosettaNet 差异  
 下表显示了一些 RosettaNet 和 CIDX 之间的差异。  
  
|RosettaNet 实现|CIDX 实现|  
|-------------------------------|-------------------------|  
|RosettaNet 使用“Application/x-RosettaNet”作为多用途 Internet 邮件扩展 (MIME) 类型。|CIDX 使用“Application/x-ChemXML”作为 MIME 类型。|  
|有关 RosettaNet 标头，RosettaNet 使用 GlobalAdministeringAuthorityCode = RosettaNet|CIDX 使用 GlobalAdministeringAuthorityCode = CIDX|  
|RosettaNet 支持单操作和双操作的消息。|CIDX 支持仅单操作的消息。|  
|RosettaNet 支持 PIP 0A1 （故障通知）。|CIDX 不支持 PIP 0A1。|  
|RosettaNet 消息可以为事务或通知类型。|所有 CIDX 消息都都的通知类型。|  
|在 RosettaNet，必须从 PIP 规范派生 PIP 配置设置。|在 CIDX，必须从 CIDX Chem eStandards 规范派生 PIP 配置设置。|  
  
## <a name="see-also"></a>另请参阅  
 [RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md)   
 [RNIF 标准](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)   
 [RosettaNet Pip](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)   
 [CIDX 支持](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)