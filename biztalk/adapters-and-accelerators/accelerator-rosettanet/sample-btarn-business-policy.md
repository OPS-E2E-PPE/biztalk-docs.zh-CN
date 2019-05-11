---
title: 示例 BTARN 业务策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf5431fdf5bf03fd17634266528201891e2a7d30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282039"
---
# <a name="sample-btarn-business-policy"></a>BTARN 业务策略示例
此示例是与 Microsoft® 关联的 XML 代码[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]业务规则策略。  
  
 示例文件是中的 samplebtarnpolicy.xml \<*驱动器*\>: \Program Files\\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\PIPAutomation\3A4。  
  
## <a name="demonstrates"></a>演示  
 此代码显示了一个业务规则策略，使用以下规则：  
  
 如果 (传入 3A4 采购订单消息中的 AccountNumber ="111111111") 和 (MonetaryAmount 顺序 < 500) 随后会自动发送响应消息  
  
## <a name="see-also"></a>请参阅  
 [使用业务规则的 3A4 专用响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)