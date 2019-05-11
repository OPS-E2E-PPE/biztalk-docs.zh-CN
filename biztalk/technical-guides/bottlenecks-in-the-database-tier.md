---
title: 数据库层的瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55b37393-32dc-4717-bf62-48588c23dd78
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f8dbf3a1d1360bc552344eb989fccf239fc6f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400442"
---
# <a name="bottlenecks-in-the-database-tier"></a><span data-ttu-id="f2265-102">数据库层的瓶颈</span><span class="sxs-lookup"><span data-stu-id="f2265-102">Bottlenecks in the Database Tier</span></span>
<span data-ttu-id="f2265-103">本部分介绍如何找出瓶颈为 BizTalk MessageBox 数据库、 跟踪数据库和 BAM 主导入数据库中。</span><span class="sxs-lookup"><span data-stu-id="f2265-103">This section explains how to identify bottlenecks in the BizTalk MessageBox database, Tracking database, and BAM Primary Import database.</span></span> <span data-ttu-id="f2265-104">它还介绍了如何避免磁盘争用。</span><span class="sxs-lookup"><span data-stu-id="f2265-104">It also explains how to avoid disk contention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2265-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="f2265-105">In This Section</span></span>  
  
-   [<span data-ttu-id="f2265-106">如何找出 MessageBox 数据库 1 的瓶颈</span><span class="sxs-lookup"><span data-stu-id="f2265-106">How to Identify Bottlenecks in the MessageBox Database1</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)  
  
-   [<span data-ttu-id="f2265-107">如何找出跟踪数据库数据库的瓶颈</span><span class="sxs-lookup"><span data-stu-id="f2265-107">How to Identify Bottlenecks in the Tracking Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)  
  
-   [<span data-ttu-id="f2265-108">如何找出 BAM 主导入数据库的瓶颈</span><span class="sxs-lookup"><span data-stu-id="f2265-108">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-bam-primary-import-database.md)  
  
-   [<span data-ttu-id="f2265-109">如何避免磁盘 Contention2</span><span class="sxs-lookup"><span data-stu-id="f2265-109">How to Avoid Disk Contention2</span></span>](../technical-guides/how-to-avoid-disk-contention2.md)