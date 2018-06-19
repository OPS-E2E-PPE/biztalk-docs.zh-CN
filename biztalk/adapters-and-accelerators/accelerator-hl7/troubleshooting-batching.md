---
title: 故障排除批处理 |Microsoft 文档
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
ms.openlocfilehash: 94c8413a8022529e6ace56c50d5e6d75267a72e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206301"
---
# <a name="troubleshooting-batching"></a>故障排除批处理
解决与相关的问题，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理。  
  
## <a name="error-activating-batch"></a>错误激活批处理  
  
### <a name="symptom"></a>故障现象  
 无法激活一批。 获取一般网络错误。  
  
**可能的原因**:[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]已重新启动，但[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器不是。  
  
**解析**： 重新启动[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="messages-are-not-batched-when-the-target-namespace-is-not-the-default"></a>批处理消息一次不时的目标命名空间不是默认值  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]未对消息进行批处理。  
  
**可能的原因**： 源和目标方不在相同的架构命名空间。  
  
**解析**： 源和目标方必须使用相同的架构命名空间，如果需要验证。 请确保源和目标方使用相同的架构命名空间。  
  
## <a name="see-also"></a>另请参阅  
 [在 HL7 疑难解答和已知问题](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)