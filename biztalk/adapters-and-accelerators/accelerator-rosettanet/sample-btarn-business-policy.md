---
title: "示例 BTARN 业务策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfe0bd746894106fc7ac9ebeaae600fe7344ba18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-btarn-business-policy"></a>示例 BTARN 业务策略
此示例是与 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 业务规则策略相关联的 XML 代码。  
  
 示例文件是在 samplebtarnpolicy.xml \<*驱动器*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本 > RosettaNet\SDK\PIPAutomation\3A4 快捷键。  
  
## <a name="demonstrates"></a>演示  
 此代码给出具有以下规则的业务规则策略：  
  
 IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message  
  
## <a name="see-also"></a>另请参阅  
 [使用业务规则 3A4 私有响应方业务流程](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)