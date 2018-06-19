---
title: FIN 响应对帐疑难解答 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FIN Response Reconciliation, troubleshooting
- troubleshooting, FIN Response Reconciliation
ms.assetid: f62326aa-9a4e-4941-a9bb-20bde980f99e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a92812086f191d5777b387d9861b32a3147c1e96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207413"
---
# <a name="fin-response-reconciliation-troubleshooting"></a>FIN 响应对帐故障排除
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a>FRR BAM 视图不显示一条消息的消息类型  
  
### <a name="symptom"></a>故障现象  
 MRSR 站点中的 FRR BAM 视图不显示一个或多个消息的消息类型。 显示的消息或消息的所有其他数据，并为显示的消息类型的所有其他消息类型的实例。  
  
### <a name="possible-cause"></a>可能的原因  
 FRRMessageOut 活动不会记录 F21 消息 (Ack/NAKs) 的消息类型。  
  
### <a name="solution"></a>解决方案  
 如果你遇到此问题，解释没有作为 F21 消息 MRSR 站点中的 FRR BAM 视图中列出的消息类型的任何消息。  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a>部署项目中的系统级架构生成一个错误  
  
### <a name="symptom"></a>故障现象  
 当你尝试部署中 FrrSchemas.dll 项目中的系统级架构时，你将收到一个错误。 有关这些架构的列表，请参阅[FIN 响应类型](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)。  
  
### <a name="possible-cause"></a>可能的原因  
 FrrSchemas.dll 中的系统级架构已部署在 FrrSchemas.dll。 尝试将它们部署再次导致错误。  
  
### <a name="solution"></a>解决方案  
 没有无需部署中 FrrSchemas.dll 的系统级架构。  
  
## <a name="see-also"></a>另请参阅  
 [疑难解答： 问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)