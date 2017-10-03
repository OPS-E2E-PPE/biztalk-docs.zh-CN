---
title: "MSMQ 适配器概述 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, about MSMQ adapters
- MSMQ adapters
ms.assetid: 4f4bfe49-19fc-4195-8826-0329f17cbe94
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d5a543e2fc5db228d249b2db2c445e254384d03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-msmq-adapter"></a><span data-ttu-id="a78f2-103">MSMQ 适配器概述</span><span class="sxs-lookup"><span data-stu-id="a78f2-103">What Is the MSMQ Adapter?</span></span>
<span data-ttu-id="a78f2-104">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]msmq （MSMQ 适配器） 的适配器，你可以发送和接收到使用 Microsoft 的 Microsoft 消息队列 (也称为 MSMQ) 队列消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a78f2-104">With the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Adapter for MSMQ (the MSMQ adapter), you can send and receive messages to Microsoft Message Queuing (also known as MSMQ) queues using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a78f2-105">MSMQ 适配器支持 Message Queuing 4.0。</span><span class="sxs-lookup"><span data-stu-id="a78f2-105">The MSMQ adapter supports Message Queuing 4.0.</span></span> <span data-ttu-id="a78f2-106">该适配器使用事务性和非事务性队列、公用和专用队列、以及本地和远程队列。</span><span class="sxs-lookup"><span data-stu-id="a78f2-106">The adapter works with transactional and non-transactional, public and private, and local and remote queues.</span></span> <span data-ttu-id="a78f2-107">此外，MSMQ 适配器还提供对大消息（大于 4 MB）的支持；使用该适配器，您可以访问 Message Queuing 4.0 的功能，例如远程事务性读取和从子队列读取。</span><span class="sxs-lookup"><span data-stu-id="a78f2-107">Additionally, the MSMQ adapter provides large (greater than 4 MB) message support and gives you access to Message Queuing 4.0 features such as remote transactional reads and reading from subqueues.</span></span>  
  
 <span data-ttu-id="a78f2-108">如果你已升级到 BizTalk Server 安装[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，MSMQ 了 BizTalk Server 2009 适配器不会删除。</span><span class="sxs-lookup"><span data-stu-id="a78f2-108">If you have upgraded your BizTalk Server installation to [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], the BizTalk Server 2009 Adapter for MSMQ is not removed.</span></span> <span data-ttu-id="a78f2-109">由于 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 安装了新版本的 MSMQ 适配器，因此可安全卸载用于 MSMQ 的 BizTalk Server 2009 适配器，然后手动删除此版本适配器的目录结构。</span><span class="sxs-lookup"><span data-stu-id="a78f2-109">Because [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] installs a new version of the MSMQ adapter, you can safely uninstall the BizTalk Server 2009 Adapter for MSMQ and then manually remove the directory structure for this version of the adapter.</span></span>