---
title: "备份 A4SWIFT 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up A4SWIFT database
- A4SWIFT database, backing up
ms.assetid: 53e46380-5be7-4d4c-b04c-d917ab40c07c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4102d459d5b579491f42747f1d3fe0dd3d381b71
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="backing-up-the-a4swift-database"></a><span data-ttu-id="8d590-102">备份 A4SWIFT 数据库</span><span class="sxs-lookup"><span data-stu-id="8d590-102">Backing Up the A4SWIFT Database</span></span>
<span data-ttu-id="8d590-103">你应定期备份数据库中您的 BizTalk Server 和 A4SWIFT 系统，从而降低灾难性故障的风险。</span><span class="sxs-lookup"><span data-stu-id="8d590-103">You should routinely back up the databases in your BizTalk Server and A4SWIFT system to lower the risks of a catastrophic failure.</span></span> <span data-ttu-id="8d590-104">这些数据库包括在 BizTalk Server 源系统和 A4SWIFT 数据库。</span><span class="sxs-lookup"><span data-stu-id="8d590-104">These databases include those in your BizTalk Server source system, and the A4SWIFT database.</span></span> <span data-ttu-id="8d590-105">除了降低风险，这还将使你能够清除 A4SWIFT 历史记录文件可以增长到很大的大小。</span><span class="sxs-lookup"><span data-stu-id="8d590-105">In addition to lowering risks, this will also enable you to purge A4SWIFT history files that can grow to a significant size.</span></span>  
  
 <span data-ttu-id="8d590-106">有关备份 BizTalk Server 源系统中的数据库的详细信息，请参阅 BizTalk Server 帮助中的"备份和还原 BizTalk Server 数据库"主题。</span><span class="sxs-lookup"><span data-stu-id="8d590-106">For more information about backing up the databases in your BizTalk Server source system, see the "Backing Up and Restoring BizTalk Server Databases" topic in the BizTalk Server Help.</span></span> <span data-ttu-id="8d590-107">本主题介绍用于将 BizTalk 数据库备份的备份 BizTalk Server 作业。</span><span class="sxs-lookup"><span data-stu-id="8d590-107">This topic describes the Backup BizTalk Server job that you use to back up BizTalk databases.</span></span>  
  
 <span data-ttu-id="8d590-108">有关将 A4SWIFT 数据库备份的信息，请参阅 BizTalk Server 帮助中的"如何为返回向上自定义数据库"主题。</span><span class="sxs-lookup"><span data-stu-id="8d590-108">For information about backing up the A4SWIFT database, see the "How to Back Up Custom Databases" topic in BizTalk Server Help.</span></span> <span data-ttu-id="8d590-109">本主题介绍如何修改备份 BizTalk Server 作业，以包括自定义的 A4SWIFT 数据库。</span><span class="sxs-lookup"><span data-stu-id="8d590-109">This topic describes how to modify the Backup BizTalk Server job to include the custom A4SWIFT database.</span></span>