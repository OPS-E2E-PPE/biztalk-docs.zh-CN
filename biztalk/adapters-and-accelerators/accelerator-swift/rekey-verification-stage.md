---
title: 重新生成密钥验证阶段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- rekey verification
- stages, rekey verification
ms.assetid: 8a2880b6-bb25-4af5-9f51-d0b090ca38c8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18f0d6acc7621ac50ef257c481d8ce7486ad74bf
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529994"
---
# <a name="rekey-verification-stage"></a>重新生成密钥验证阶段
重新生成密钥验证阶段发生在消息修复工作流，由消息修复和新提交和消息的一个精确副本维护一份原始消息发送到验证器的收件箱时重新生成密钥验证。 在重新生成密钥验证[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新提交清除手动记载的指定的字段。  
  
 这一概念中进一步说明[Server 运行时安全性](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)主题。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]参与的重新生成密钥验证阶段的用户必须手动重新输入到已清除的字段中，通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，与原始消息 （从创建或修复阶段） 中的完全相同的值。 验证工具然后对消息使用有效的证书进行签名，并将该消息提交。  
  
 如果 rekeyed 字段的值不完全匹配的原始消息字段，消息修复和新提交重置工作流中的阶段，并将消息发送回 repairer 的收件箱。 它还可验证的用户重新生成字段的验证程序的签名。 如果不验证验证程序，它将消息发送回的验证程序收件箱。