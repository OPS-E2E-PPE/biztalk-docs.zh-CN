---
title: 审批阶段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stages, approval
ms.assetid: a3d36956-dabc-4f8c-b61d-d7665289ca76
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de1010d70d407468247f56afe26256d420204123
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378686"
---
# <a name="approval-stage"></a><span data-ttu-id="eea11-102">审批阶段</span><span class="sxs-lookup"><span data-stu-id="eea11-102">Approval Stage</span></span>
<span data-ttu-id="eea11-103">第一次签名并提交以供审核条消息后，批准链中的每个审批者评审和副署的消息，将其数字签名添加到堆栈。</span><span class="sxs-lookup"><span data-stu-id="eea11-103">After the message is first signed and submitted for approval, each approver in the approval chain reviews and countersigns the message, adding his or her digital signature to the stack.</span></span> <span data-ttu-id="eea11-104">审批者只能查看和消息进行副署。</span><span class="sxs-lookup"><span data-stu-id="eea11-104">Approvers can only review and countersign the message.</span></span> <span data-ttu-id="eea11-105">它们不能更改它而不会中断的数字签名堆栈。</span><span class="sxs-lookup"><span data-stu-id="eea11-105">They cannot change it without breaking the digital signature stack.</span></span>