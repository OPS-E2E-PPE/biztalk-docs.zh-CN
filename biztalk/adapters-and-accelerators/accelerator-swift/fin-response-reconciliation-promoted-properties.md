---
title: FIN 响应对帐的已提升属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23d1460163b67618c3f7e15f1c8bd14ecdd97556
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377878"
---
# <a name="fin-response-reconciliation-promoted-properties"></a>FIN 响应对帐的已提升属性
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 响应对帐功能包括以下升级的属性。  
  
|升级的名称|Description|数据类型|值范围|用法示例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_FRRFailed**|主要消息发送时，在负方案中升级此属性。|Boolean|True<br /><br /> False|FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。|  
|**A4SWIFT_FrrFailedReason**|指示未成功处理原始消息，通过 SAA/SWIFT。|String|-   \<NAKErrorCode\><br />-   TimedOut<br />-TransportError<br />-   Delayed_NAK<br />-   AbortReceived|FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。|  
|**A4SWIFT_FRRCorrelationToken**|指示唯一相关标记的出站 MT*xxx*消息。|String|-|FRR 将此属性设置为进行比较**MQMD_CorrelID** FIN 响应上下文属性。|  
|**A4SWIFT_SendingServiceType**|指示发送该消息的 FRR 服务。|String|A4SWIFT_FrrService|升级时**A4SWIFT_FRRFailed**设置为 True。|  
  
## <a name="see-also"></a>请参阅  
 [A4SWIFT_ * 的已提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [消息回复和新提交的已提升属性](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)