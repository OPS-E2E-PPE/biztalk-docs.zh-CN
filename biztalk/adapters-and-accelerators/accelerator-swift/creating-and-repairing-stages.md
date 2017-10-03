---
title: "创建和修复阶段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stages, repair
- stages, create
ms.assetid: 07d7ce7b-ed15-40a7-9c85-280a1d38985b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb87112775b9664badf319796e1a6243cf6eb082
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-and-repairing-stages"></a><span data-ttu-id="31719-102">创建和修复阶段</span><span class="sxs-lookup"><span data-stu-id="31719-102">Creating and Repairing Stages</span></span>
<span data-ttu-id="31719-103">任何工作流中的第一个阶段可以在创建或修复阶段，具有定义为功能的角色，即创建或修复。</span><span class="sxs-lookup"><span data-stu-id="31719-103">The first stage in any workflow can be either a Create or Repair stage, that is, roles that have a capability defined as create or repair.</span></span> <span data-ttu-id="31719-104">消息源自失败消息的 BizTalk MessageBox 或[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户手动创建的任何消息通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。</span><span class="sxs-lookup"><span data-stu-id="31719-104">The message originates from the BizTalk MessageBox as a failed message or an [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] user manually creates a message through the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms.</span></span>  
  
 <span data-ttu-id="31719-105">原始消息创建者或 repairer 是第一个数字签名程序的消息，并添加到他或她的数字签名[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]之后创建或修复消息的窗体。</span><span class="sxs-lookup"><span data-stu-id="31719-105">The original message creator or repairer is the first digital signer of the message, and adds his or her digital signature to the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form after creating or repairing the message.</span></span> <span data-ttu-id="31719-106">此第一个签名不仅证明身份的消息创建者或 repairer，而且还会锁定处于其当前状态消息的内容。</span><span class="sxs-lookup"><span data-stu-id="31719-106">This first signature not only proves the identity of the message creator or repairer, but also locks the contents of the message in its current state.</span></span> <span data-ttu-id="31719-107">如果第一个登录后更改了消息，数字签名堆栈已断开，且向指出窗体上的数字签名无效的用户不会显示警告。</span><span class="sxs-lookup"><span data-stu-id="31719-107">If the message is altered after the first signing, the digital signature stack is broken and warnings are shown to the user stating that the digital signatures on the form are invalid.</span></span>