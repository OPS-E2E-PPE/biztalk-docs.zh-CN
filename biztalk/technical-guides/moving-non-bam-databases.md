---
title: 移动非 BAM 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e548e72-db0e-4f07-a07a-8d210425dfa5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f6d5c4555620b2ea51a176e153dc5acdcbfabd8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400180"
---
# <a name="moving-non-bam-databases"></a><span data-ttu-id="045bd-102">移动非 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="045bd-102">Moving Non-BAM Databases</span></span>
<span data-ttu-id="045bd-103">可以使用此过程将主要 BizTalk Server 数据库移动到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="045bd-103">You can use this procedure to move the primary BizTalk Server databases to another server.</span></span> <span data-ttu-id="045bd-104">此外可以使用此相同的基本过程将 BizTalk Server 数据库从本地 SQL Server 移到远程 SQL Server 或 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="045bd-104">This same basic procedure can also be used to move the BizTalk Server databases from a local SQL Server to a remote SQL Server or to a SQL Server cluster.</span></span> <span data-ttu-id="045bd-105">本部分介绍如何将移动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不相关的 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="045bd-105">This section describes how to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that are not BAM related.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="045bd-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="045bd-106">In This Section</span></span>  
 <span data-ttu-id="045bd-107">要移动非 BAM 数据库，请按照本主题中的步骤[如何将 BizTalk Server 数据库移出](http://go.microsoft.com/fwlink/?LinkId=210646)(<http://go.microsoft.com/fwlink/?LinkId=210646>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="045bd-107">To move the non BAM databases follow the steps in the topic [How to Move the BizTalk Server Databases](http://go.microsoft.com/fwlink/?LinkId=210646) (<http://go.microsoft.com/fwlink/?LinkId=210646>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help.</span></span>  
  
 <span data-ttu-id="045bd-108">本部分还包含本主题介绍了必须遵循特定的移动后的过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="045bd-108">This section also contains a topic that describes procedures that must be followed after moving particular [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="045bd-109">完成为适合您的环境主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="045bd-109">Complete the steps in the topic as appropriate for your environment.</span></span>  
  
-   [<span data-ttu-id="045bd-110">在未移动 MessageBox 数据库的前提下移动跟踪数据库时的注意事项</span><span class="sxs-lookup"><span data-stu-id="045bd-110">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>](../technical-guides/before-you-move-the-tracking-database-if-messagebox-database-is-not-moving.md)