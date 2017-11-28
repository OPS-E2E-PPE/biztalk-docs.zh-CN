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
# <a name="rekey-verification-stage"></a><span data-ttu-id="533b9-102">重新生成密钥验证阶段</span><span class="sxs-lookup"><span data-stu-id="533b9-102">Rekey Verification Stage</span></span>
<span data-ttu-id="533b9-103">重新生成密钥验证阶段发生在消息修复工作流，由消息修复和新的提交和消息的一个精确副本维护原始消息的副本发送到的验证收件箱时重新生成验证密钥。</span><span class="sxs-lookup"><span data-stu-id="533b9-103">When a Rekey Verification stage occurs in the message repair workflow, a copy of the original message is maintained by Message Repair and New Submission and an exact copy of the message is sent to the verifier's inbox for rekey verification.</span></span> <span data-ttu-id="533b9-104">在重新生成密钥验证[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新提交清除手动重新输入的指定的字段。</span><span class="sxs-lookup"><span data-stu-id="533b9-104">In rekey verification, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission clears specified fields for manual re-entry.</span></span>  
  
 <span data-ttu-id="533b9-105">这一概念中进一步说明[服务器运行时安全性](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md)主题。</span><span class="sxs-lookup"><span data-stu-id="533b9-105">This concept is explained further in the [Server Runtime Security](../../adapters-and-accelerators/accelerator-swift/server-runtime-security.md) topic.</span></span> <span data-ttu-id="533b9-106">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]参与重新生成密钥验证阶段的用户必须手动重新输入到已清除的字段中，通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体中，完全匹配 （从创建或修复阶段） 为原始消息中的值。</span><span class="sxs-lookup"><span data-stu-id="533b9-106">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user participating in the Rekey Verification stage must manually re-enter into the cleared fields, through the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form, values that exactly match those in the original message (from either the Create or Repair stage).</span></span> <span data-ttu-id="533b9-107">然后，验证程序进行签名的有效证书的消息，并将消息提交。</span><span class="sxs-lookup"><span data-stu-id="533b9-107">The verifier then signs the message with a valid certificate and submits the message.</span></span>  
  
 <span data-ttu-id="533b9-108">如果 rekeyed 字段的值不完全匹配的原始消息字段，消息修复和新提交重置工作流中的阶段，并将消息发送回 repairer 的收件箱。</span><span class="sxs-lookup"><span data-stu-id="533b9-108">If the values of the rekeyed fields do not match the original message fields exactly, Message Repair and New Submission resets the stage in the workflow and sends the message back to the repairer's inbox.</span></span> <span data-ttu-id="533b9-109">它还将验证用户重新生成字段的验证的签名。</span><span class="sxs-lookup"><span data-stu-id="533b9-109">It also validates the signature of the verifier who rekeyed the fields.</span></span> <span data-ttu-id="533b9-110">如果未通过验证验证程序，它会将消息发送回的验证收件箱中。</span><span class="sxs-lookup"><span data-stu-id="533b9-110">If the verifier is not validated, it sends the message back to the verifier's inbox.</span></span>