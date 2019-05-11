---
title: 创建和修复阶段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stages, repair
- stages, create
ms.assetid: 07d7ce7b-ed15-40a7-9c85-280a1d38985b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9f26752fce0da2290892a46c051652001493bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378443"
---
# <a name="creating-and-repairing-stages"></a><span data-ttu-id="a12bd-102">创建和修复阶段</span><span class="sxs-lookup"><span data-stu-id="a12bd-102">Creating and Repairing Stages</span></span>
<span data-ttu-id="a12bd-103">所有工作流中的第一个阶段可以在创建或修复阶段，可以定义为一项功能的角色，即创建或修复。</span><span class="sxs-lookup"><span data-stu-id="a12bd-103">The first stage in any workflow can be either a Create or Repair stage, that is, roles that have a capability defined as create or repair.</span></span> <span data-ttu-id="a12bd-104">消息源自失败消息作为 BizTalk MessageBox 或[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户手动创建一条消息通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。</span><span class="sxs-lookup"><span data-stu-id="a12bd-104">The message originates from the BizTalk MessageBox as a failed message or an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user manually creates a message through the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms.</span></span>  
  
 <span data-ttu-id="a12bd-105">原始消息创建者或 repairer 是第一个数字签名者的消息，并添加到其数字签名[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体后创建或修复该消息。</span><span class="sxs-lookup"><span data-stu-id="a12bd-105">The original message creator or repairer is the first digital signer of the message, and adds his or her digital signature to the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form after creating or repairing the message.</span></span> <span data-ttu-id="a12bd-106">此第一个签名不仅能证明身份的消息创建者或 repairer，而且还会锁定其当前状态中的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="a12bd-106">This first signature not only proves the identity of the message creator or repairer, but also locks the contents of the message in its current state.</span></span> <span data-ttu-id="a12bd-107">如果首次登录后更改该消息数字签名堆栈已损坏，警告将显示向用户指示窗体上的数字签名将无效。</span><span class="sxs-lookup"><span data-stu-id="a12bd-107">If the message is altered after the first signing, the digital signature stack is broken and warnings are shown to the user stating that the digital signatures on the form are invalid.</span></span>