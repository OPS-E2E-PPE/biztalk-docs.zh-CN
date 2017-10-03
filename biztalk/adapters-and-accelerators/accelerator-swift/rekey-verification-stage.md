---
title: "重新生成密钥验证阶段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rekey verification
- stages, rekey verification
ms.assetid: 8a2880b6-bb25-4af5-9f51-d0b090ca38c8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9fe163a8351b0edc904f81d77a7ea341de13df6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="rekey-verification-stage"></a>重新生成密钥验证阶段
重新生成密钥验证阶段发生在消息修复工作流，由消息修复和新的提交和消息的一个精确副本维护原始消息的副本发送到的验证收件箱时重新生成验证密钥。 在重新生成密钥验证[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新提交清除手动重新输入的指定的字段。  
  
 这一概念中进一步说明[服务器运行时安全性](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)主题。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]参与重新生成密钥验证阶段的用户必须手动重新输入到已清除的字段中，通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，完全匹配 （从创建或修复阶段） 为原始消息中的值。 然后，验证程序进行签名的有效证书的消息，并将消息提交。  
  
 如果 rekeyed 字段的值不完全匹配的原始消息字段，消息修复和新提交重置工作流中的阶段，并将消息发送回 repairer 的收件箱。 它还将验证用户重新生成字段的验证的签名。 如果未通过验证验证程序，它会将消息发送回的验证收件箱中。