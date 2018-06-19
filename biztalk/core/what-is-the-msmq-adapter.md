---
title: MSMQ 适配器概述 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, about MSMQ adapters
- MSMQ adapters
ms.assetid: 4f4bfe49-19fc-4195-8826-0329f17cbe94
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: caeac28ce33e2f5eeacbb73b03d9873ec1e74c92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008398"
---
# <a name="what-is-the-msmq-adapter"></a>MSMQ 适配器概述
与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]msmq （MSMQ 适配器） 的适配器，你可以发送和接收到使用 Microsoft 的 Microsoft 消息队列 (也称为 MSMQ) 队列消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 MSMQ 适配器支持 Message Queuing 4.0。 该适配器使用事务性和非事务性队列、公用和专用队列、以及本地和远程队列。 此外，MSMQ 适配器还提供对大消息（大于 4 MB）的支持；使用该适配器，您可以访问 Message Queuing 4.0 的功能，例如远程事务性读取和从子队列读取。  
  
 如果你的 BizTalk Server 安装升级到 BizTalk Server，则不会删除 MSMQ 了 BizTalk Server 2009 适配器。 因为 BizTalk Server 安装 MSMQ 适配器的新版本，你可以安全地卸载 msmq 的 BizTalk Server 2009 适配器，然后手动删除适配器的此版本的目录结构。