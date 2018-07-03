---
title: 自定义处理程序的消息的 FRR 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8ba2b085268f2c0c272b81b27768db716b63c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996150"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a>自定义处理程序的消息的 FRR 发送端口
若要启用 FRR 自定义处理程序，必须创建一系列的 FRR 发送端口，每个将某一类型的原始消息的副本路由到自定义处理程序。 这些发送端口都必须具有以下管道组件：  

- SWIFT 汇编程序的组装阶段中  

- SWIFTSendFrrComponent 管道组件中的编码阶段  

  对于除类别 0 到 9 SWIFT FIN 消息未成功发送的所有消息，发送端口必须具有以下筛选器：  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType = = [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  

- BTS。操作设置为每种消息类型所需的值。 有关可能的值为 BTS。操作属性，请参阅中的表[为发送到自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。  

  对于未成功发送的类别 0 到 9 SWIFT FIN 消息，发送端口必须具有以下筛选器：  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceTyp = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrFailed = = true  

- BTS。操作 = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason 设置为每种消息类型所需的值。 有关可能的值为 BTS。操作属性，请参阅中的表[为发送到自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。
