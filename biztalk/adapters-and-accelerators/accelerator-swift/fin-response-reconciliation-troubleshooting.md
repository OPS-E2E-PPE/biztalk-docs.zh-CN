---
title: FIN 响应对帐疑难解答 |Microsoft Docs
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
ms.openlocfilehash: f9fa60b9b9f3034e795c191cc6a40e7288f195ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377800"
---
# <a name="fin-response-reconciliation-troubleshooting"></a>FIN 响应对帐疑难解答
## <a name="the-frr-bam-view-does-not-show-the-message-type-of-a-message"></a>FRR BAM 视图不显示一条消息的消息类型  
  
### <a name="symptom"></a>故障现象  
 MRSR 站点中的 FRR BAM 视图不显示一个或多个消息的消息类型。 显示为消息或消息的所有其他数据，并且消息类型显示的所有其他消息类型的实例。  
  
### <a name="possible-cause"></a>可能的原因  
 FRRMessageOut 活动不会记录 F21 消息 (Ack/NAKs) 的消息类型。  
  
### <a name="solution"></a>解决方案  
 如果遇到此问题，将不具有作为 F21 消息 MRSR 站点中的 FRR BAM 视图中列出的消息类型的任何消息。  
  
## <a name="deploying-system-level-schemas-in-a-project-generates-an-error"></a>部署项目中的系统级架构将生成错误  
  
### <a name="symptom"></a>故障现象  
 当你尝试部署 FrrSchemas.dll 中在项目中的系统级架构时，您将收到错误。 有关这些架构中的列表，请参阅[FIN 响应类型](../../adapters-and-accelerators/accelerator-swift/fin-response-types.md)。  
  
### <a name="possible-cause"></a>可能的原因  
 已部署在 FrrSchemas.dll FrrSchemas.dll 中的系统级架构。 尝试将其部署再次导致错误。  
  
### <a name="solution"></a>解决方案  
 没有必要部署 FrrSchemas.dll 中的系统级架构。  
  
## <a name="see-also"></a>请参阅  
 [故障排除：问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)