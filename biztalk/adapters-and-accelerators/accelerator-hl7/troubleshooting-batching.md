---
title: 批处理疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, troubleshooting
- troubleshooting, batching
ms.assetid: f47e1a16-47fd-4bd8-8dad-fcdba31a833e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de82fb536dcd23410b485a12eccba1592ccebbe2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286504"
---
# <a name="troubleshooting-batching"></a>批处理疑难解答
解决了与相关的问题[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理。  
  
## <a name="error-activating-batch"></a>错误激活批处理  
  
### <a name="symptom"></a>故障现象  
 无法激活批处理。 您收到常规网络错误。  
  
**可能的原因**:[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]重新启动，但[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器不是。  
  
**解析**:重新启动[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a>消息不进行批处理时的目标命名空间不是默认值  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 未对消息进行批处理。  
  
**可能的原因**:源和目标参与方不是同一架构命名空间中。  
  
**解析**:如果需要验证源和目标参与方必须使用相同的架构命名空间。 请确保源和目标参与方都使用相同的架构命名空间。  
  
## <a name="see-also"></a>请参阅  
 [HL7 的疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)