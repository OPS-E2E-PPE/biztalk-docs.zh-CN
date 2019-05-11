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
# <a name="creating-and-repairing-stages"></a>创建和修复阶段
所有工作流中的第一个阶段可以在创建或修复阶段，可以定义为一项功能的角色，即创建或修复。 消息源自失败消息作为 BizTalk MessageBox 或[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]用户手动创建一条消息通过[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体。  
  
 原始消息创建者或 repairer 是第一个数字签名者的消息，并添加到其数字签名[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体后创建或修复该消息。 此第一个签名不仅能证明身份的消息创建者或 repairer，而且还会锁定其当前状态中的消息的内容。 如果首次登录后更改该消息数字签名堆栈已损坏，警告将显示向用户指示窗体上的数字签名将无效。