---
title: 授权和不可否认性属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authorization properties
- non-repudiation, properties
ms.assetid: e752b95b-9dae-4403-8f3e-3a0a50acd519
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d7088b25ec2526c19c60d21c9929afb92be42a7
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752757"
---
# <a name="authorization-and-non-repudiation-properties"></a>授权和不可否认性属性
本主题介绍了合作伙伴界面进程 (PIP) 的 `Is Authorization Required` 属性、`Non-Repudiation of Origin and Content` 属性，以及 `Non-Repudiation Required (Acknowledgement of Receipt)` 属性的行为。 它还介绍了这些属性的组合，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]支持。  

 在设置这些属性**活动**选项卡的流程配置设置部分中的流程配置属性[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台。 有关详细信息，请参阅[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。  

## <a name="property-behavior"></a>属性行为  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 根据“是否要求授权”`Is Authorization Required`、“	原始消息和内容的不可否认性”`Non-Repudiation of Origin and Content`以及“要求不可否认性（确认收到）”`Non-Repudiation Required (Acknowledgement of Receipt)`属性的设置表现为以下行为。  


|                        “属性”                         |                                                                                                                                                                             为 True 时的行为                                                                                                                                                                             |                                                                               为 False 时的行为                                                                               |
|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|               `Is Authorization Required`               | 必须传入操作或信号消息进行签名;否则为[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将拒绝该消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 如果个人/角色无权执行该活动，不接受业务文档。 | 传入操作或信号消息无需必须经过签名。 但仍将使用该消息的 RNIF 头部分的合作伙伴邓氏 (DUNS) 编码来进行简单的验证。 |
|         `Non-Repudiation of Origin and Content`         |                                                                                                将对传出操作或信号消息进行签名。 操作消息将以其原始接收格式存储在 BTARNDATA 数据库的 MessageStorageOut 表中。                                                                                                 |                                                             不存储传出操作或信号消息。                                                              |
| `Non-Repudiation Required (Acknowledgement of Receipt)` |                                                                                 传入操作或信号消息必须经过签名。 传入消息将存储在 BTARNDATA 数据库的 MessageStorageIn 表中。 在确认中必须包括消息摘要。                                                                                  |                                                             不存储传入操作或信号消息。                                                              |

## <a name="property-support"></a>属性支持  
 下表介绍 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 支持的“是否要求授权”`Is Authorization Required`、“原始消息和内容的不可否认性”`Non-Repudiation of Origin and Content`以及“要求不可否认性（确认收到）”`Non-Repudiation Required (Acknowledgement of Receipt)`属性的组合。  

> [!IMPORTANT]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 必须既对同时操作的消息和信号消息或操作消息既不单独的消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 执行不支持签名操作，但未签名发出信号，反之亦然。  
> 
> [!IMPORTANT]
>  如果 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 对出站消息进行签名，它必须将该消息保存到 BTARNArchive 数据库的 MessageStorageOut 表中。  

|是否要求授权|不可否认性和内容的|要求不可否认性（确认收到）|BTARN 是否支持？|  
|-------------------------------|--------------------------------------------|--------------------------------------------------------------|-------------------------|  
|`False`|`False`|`False`|用户帐户控制|  
|`False`|`False`|`True`|不\*|  
|`False`|`True`|`False`|不\*\*|  
|`False`|`True`|`True`|不\*\*\*|  
|`True`|`False`|`False`|是的\*\*\*\*|  
|`True`|`False`|`True`|是的\*\*\*\*|  
|`True`|`True`|`False`|用户帐户控制|  
|`True`|`True`|`True`|用户帐户控制|  

 \* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持此组合，因为它要求信号经过签名而操作不经过签名。  

 \*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持此组合，因为它要求操作经过签名而信号不经过签名。  

 \*\*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不支持此组合，因为设置为不可否认`True`的操作和信号意味着[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]执行授权。 因此，此组合无效。  

 \*\*\*\* 当您将设置`Is Authorization Required`到`True`并`Non-Repudiation of Origin and Content`到`False`，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将消息存储在不可否认性表中。  

## <a name="see-also"></a>请参阅  
 [如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)