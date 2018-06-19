---
title: 数据库层中的瓶颈 |Microsoft 文档
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
ms.openlocfilehash: b741f1ffcd68f7a5c739731e5aa9a1db55be34c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299941"
---
# <a name="bottlenecks-in-the-database-tier"></a><span data-ttu-id="776c3-102">数据库层中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="776c3-102">Bottlenecks in the Database Tier</span></span>
<span data-ttu-id="776c3-103">本部分说明如何确定 BizTalk MessageBox 数据库、 跟踪数据库和 BAM 主导入数据库中的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="776c3-103">This section explains how to identify bottlenecks in the BizTalk MessageBox database, Tracking database, and BAM Primary Import database.</span></span> <span data-ttu-id="776c3-104">它还说明了如何避免磁盘争用。</span><span class="sxs-lookup"><span data-stu-id="776c3-104">It also explains how to avoid disk contention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="776c3-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="776c3-105">In This Section</span></span>  
  
-   [<span data-ttu-id="776c3-106">如何确定 MessageBox Database1 中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="776c3-106">How to Identify Bottlenecks in the MessageBox Database1</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-messagebox-database1.md)  
  
-   [<span data-ttu-id="776c3-107">如何确定跟踪数据库中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="776c3-107">How to Identify Bottlenecks in the Tracking Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-tracking-database.md)  
  
-   [<span data-ttu-id="776c3-108">如何确定 BAM 主导入数据库中的瓶颈</span><span class="sxs-lookup"><span data-stu-id="776c3-108">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>](../technical-guides/how-to-identify-bottlenecks-in-the-bam-primary-import-database.md)  
  
-   [<span data-ttu-id="776c3-109">如何避免磁盘 Contention2</span><span class="sxs-lookup"><span data-stu-id="776c3-109">How to Avoid Disk Contention2</span></span>](../technical-guides/how-to-avoid-disk-contention2.md)