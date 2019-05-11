---
title: 维护 BizTalk Server1 |Microsoft Docs
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
ms.openlocfilehash: 73b8697d197a5888fd3ea7da378523014170c3e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329077"
---
# <a name="maintaining-biztalk-server1"></a><span data-ttu-id="cac10-102">维护 BizTalk Server1</span><span class="sxs-lookup"><span data-stu-id="cac10-102">Maintaining BizTalk Server1</span></span>
<span data-ttu-id="cac10-103">本部分提供有关如何备份和还原 BizTalk Server 和 Microsoft BizTalk Server 的信息的数据库、 如何存档和清除 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据以及如何移动一些较常用移动的 BizTalk服务器数据库。</span><span class="sxs-lookup"><span data-stu-id="cac10-103">This section provides information about how to back up and restore BizTalk Server and the Microsoft BizTalk Server databases, how to archive and purge data from the BizTalk Tracking (BizTalkDTADb) database, and how to move some of the more commonly moved BizTalk Server databases.</span></span> <span data-ttu-id="cac10-104">它提供备份和还原过程，以及建议用于维护 BizTalk 跟踪数据库的概述。</span><span class="sxs-lookup"><span data-stu-id="cac10-104">It provides an overview of the backup and restoration process, as well as recommendations for maintaining the BizTalk Tracking database.</span></span> <span data-ttu-id="cac10-105">它介绍了在手动从测试环境中 BizTalk MessageBox 数据库中清除数据。</span><span class="sxs-lookup"><span data-stu-id="cac10-105">It provides information on manually purging data from the BizTalk MessageBox database in a test environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cac10-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="cac10-106">In This Section</span></span>  
  
-   [<span data-ttu-id="cac10-107">备份和还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="cac10-107">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)  
  
-   [<span data-ttu-id="cac10-108">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="cac10-108">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [<span data-ttu-id="cac10-109">移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="cac10-109">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)  
  
-   [<span data-ttu-id="cac10-110">如何从 MessageBox 数据库中的测试环境中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="cac10-110">How to Manually Purge Data from the MessageBox Database in a Test Environment</span></span>](../core/how-to-manually-purge-data-from-the-messagebox-database-in-a-test-environment.md)