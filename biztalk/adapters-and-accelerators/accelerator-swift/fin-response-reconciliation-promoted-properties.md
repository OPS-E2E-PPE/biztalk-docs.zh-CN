---
title: "FIN 响应对帐提升属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, FIN Response Reconciliation
- FIN Response Reconciliation, promoted properties
ms.assetid: 1a638e9e-61eb-482c-8856-b1aea36c449c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14a3e3a004dcb9e58abde08345352c02f0914801
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fin-response-reconciliation-promoted-properties"></a>FIN 响应对帐升级的属性
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 响应对帐功能包括以下提升的属性。  
  
|提升的名称|Description|数据类型|值范围|用法示例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_FRRFailed**|发送出主消息时，此属性提升负方案中。|Boolean|True<br /><br /> False|FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。|  
|**A4SWIFT_FrrFailedReason**|指示原始消息已不成功的方式处理 SAA/SWIFT。|字符串|-   \<NAKErrorCode ><br />-超时<br />-TransportError<br />-Delayed_NAK<br />-AbortReceived|FRR 发送端口的筛选器表达式中用于将失败的消息发送到自定义处理程序。|  
|**A4SWIFT_FRRCorrelationToken**|指示唯一相关标记的出站 MT*xxx*消息。|字符串|-|FRR 比较到此属性**MQMD_CorrelID** FIN 响应上下文属性。|  
|**A4SWIFT_SendingServiceType**|指示 FRR 服务发送消息。|字符串|A4SWIFT_FrrService|提升时**A4SWIFT_FRRFailed**设置为 True。|  
  
## <a name="see-also"></a>另请参阅  
 [A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   
 [消息修复和新提交提升属性](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission-promoted-properties.md)