---
title: 备份 A4SWIFT 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89e69325509131c6ea1674c3f6c3b6153f3ea2f7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378655"
---
# <a name="backing-up-the-a4swift-database"></a><span data-ttu-id="8eddd-102">备份 A4SWIFT 数据库</span><span class="sxs-lookup"><span data-stu-id="8eddd-102">Backing Up the A4SWIFT Database</span></span>
<span data-ttu-id="8eddd-103">你应定期将数据库备份 BizTalk Server 和 A4SWIFT 系统到较低的灾难性故障的风险中。</span><span class="sxs-lookup"><span data-stu-id="8eddd-103">You should routinely back up the databases in your BizTalk Server and A4SWIFT system to lower the risks of a catastrophic failure.</span></span> <span data-ttu-id="8eddd-104">这些数据库包括在 BizTalk Server 源系统和 A4SWIFT 数据库。</span><span class="sxs-lookup"><span data-stu-id="8eddd-104">These databases include those in your BizTalk Server source system, and the A4SWIFT database.</span></span> <span data-ttu-id="8eddd-105">除了降低风险，这也将启用你清除 A4SWIFT 历史记录文件可以增长到很大的大小。</span><span class="sxs-lookup"><span data-stu-id="8eddd-105">In addition to lowering risks, this will also enable you to purge A4SWIFT history files that can grow to a significant size.</span></span>  
  
 <span data-ttu-id="8eddd-106">有关 BizTalk Server 源系统中的数据库备份的详细信息，请参阅 BizTalk Server 帮助中的"备份和还原 BizTalk Server 数据库"主题。</span><span class="sxs-lookup"><span data-stu-id="8eddd-106">For more information about backing up the databases in your BizTalk Server source system, see the "Backing Up and Restoring BizTalk Server Databases" topic in the BizTalk Server Help.</span></span> <span data-ttu-id="8eddd-107">本主题介绍用于将备份 BizTalk 数据库的备份 BizTalk Server 作业。</span><span class="sxs-lookup"><span data-stu-id="8eddd-107">This topic describes the Backup BizTalk Server job that you use to back up BizTalk databases.</span></span>  
  
 <span data-ttu-id="8eddd-108">有关备份 A4SWIFT 数据库的信息，请参阅 BizTalk Server 帮助中的"如何为返回了自定义数据库"主题。</span><span class="sxs-lookup"><span data-stu-id="8eddd-108">For information about backing up the A4SWIFT database, see the "How to Back Up Custom Databases" topic in BizTalk Server Help.</span></span> <span data-ttu-id="8eddd-109">本主题介绍如何修改备份 BizTalk Server 作业，包括自定义的 A4SWIFT 数据库。</span><span class="sxs-lookup"><span data-stu-id="8eddd-109">This topic describes how to modify the Backup BizTalk Server job to include the custom A4SWIFT database.</span></span>