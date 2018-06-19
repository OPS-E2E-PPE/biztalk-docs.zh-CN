---
title: 维护 BizTalk Server1 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, maintaining
ms.assetid: dd1e4497-839a-4686-b213-da100b6b5226
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e56d1cb915a91136058a6c1d4a670416903e8aef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262013"
---
# <a name="maintaining-biztalk-server1"></a><span data-ttu-id="c49c7-102">维护 BizTalk Server1</span><span class="sxs-lookup"><span data-stu-id="c49c7-102">Maintaining BizTalk Server1</span></span>
<span data-ttu-id="c49c7-103">本部分介绍有关如何备份和还原 BizTalk Server 和 Microsoft BizTalk Server 数据库、如何存档和清除 BizTalk 跟踪数据库 (BizTalkDTADb) 中的数据以及如何移动某些较频繁移动的 BizTalk Server 数据库的信息。</span><span class="sxs-lookup"><span data-stu-id="c49c7-103">This section provides information about how to back up and restore BizTalk Server and the Microsoft BizTalk Server databases, how to archive and purge data from the BizTalk Tracking (BizTalkDTADb) database, and how to move some of the more commonly moved BizTalk Server databases.</span></span> <span data-ttu-id="c49c7-104">本部分概述了备份和还原过程，以及维护 BizTalk 跟踪数据库的建议。</span><span class="sxs-lookup"><span data-stu-id="c49c7-104">It provides an overview of the backup and restoration process, as well as recommendations for maintaining the BizTalk Tracking database.</span></span> <span data-ttu-id="c49c7-105">它提供有关在测试环境中手动从 BizTalk MessageBox 数据库清除数据的信息。</span><span class="sxs-lookup"><span data-stu-id="c49c7-105">It provides information on manually purging data from the BizTalk MessageBox database in a test environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c49c7-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="c49c7-106">In This Section</span></span>  
  
-   [<span data-ttu-id="c49c7-107">备份和还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c49c7-107">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)  
  
-   [<span data-ttu-id="c49c7-108">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="c49c7-108">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="c49c7-109">将 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="c49c7-109">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="c49c7-110">如何手动清除数据，从测试环境中的 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="c49c7-110">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>](../core/how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment.md)