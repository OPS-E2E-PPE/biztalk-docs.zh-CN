---
title: MSMQ 适配器是什么？ | Microsoft Docs
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
ms.openlocfilehash: e58081f9ad39b3c8964472fda39120fa238e5397
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242934"
---
# <a name="what-is-the-msmq-adapter"></a>MSMQ 适配器是什么？
与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MSMQ （MSMQ 适配器） 的适配器，您可以发送和接收消息到使用 Microsoft 的 Microsoft 消息队列 (也称为 MSMQ) 队列[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 MSMQ 适配器支持 Message Queuing 4.0。 适配器可与事务性和非事务性、 公共和专用和本地和远程队列。 此外，MSMQ 适配器还提供对大 （大于 4 MB） 消息的支持和可以让您访问 Message Queuing 4.0 功能，例如远程事务性读取和读取队列中的消息。  
  
 如果你已升级到 BizTalk Server 的 BizTalk Server 安装，则不会删除用于 MSMQ 的 BizTalk Server 2009 适配器。 因为 BizTalk Server 安装 MSMQ 适配器的新版本，可安全卸载用于 MSMQ 的 BizTalk Server 2009 适配器，然后手动删除此版本的适配器的目录结构。