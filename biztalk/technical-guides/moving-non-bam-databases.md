---
title: 移动非 BAM 数据库 |Microsoft 文档
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
ms.openlocfilehash: c836840fef8b49cb907e7ac039612c68c1f6fd6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298221"
---
# <a name="moving-non-bam-databases"></a><span data-ttu-id="4ff79-102">移动非 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="4ff79-102">Moving Non-BAM Databases</span></span>
<span data-ttu-id="4ff79-103">此过程可用于将主 BizTalk Server 数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="4ff79-103">You can use this procedure to move the primary BizTalk Server databases to another server.</span></span> <span data-ttu-id="4ff79-104">此相同的基本过程还可用来将 BizTalk Server 数据库从本地 SQL Server 移到远程 SQL Server 或 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="4ff79-104">This same basic procedure can also be used to move the BizTalk Server databases from a local SQL Server to a remote SQL Server or to a SQL Server cluster.</span></span> <span data-ttu-id="4ff79-105">本部分介绍如何将移动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不相关的 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="4ff79-105">This section describes how to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases that are not BAM related.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ff79-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="4ff79-106">In This Section</span></span>  
 <span data-ttu-id="4ff79-107">要移动非 BAM 数据库，请按照本主题中的步骤[如何将 BizTalk Server 数据库移](http://go.microsoft.com/fwlink/?LinkId=210646)(http://go.microsoft.com/fwlink/?LinkId=210646) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="4ff79-107">To move the non BAM databases follow the steps in the topic [How to Move the BizTalk Server Databases](http://go.microsoft.com/fwlink/?LinkId=210646) (http://go.microsoft.com/fwlink/?LinkId=210646) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] help.</span></span>  
  
 <span data-ttu-id="4ff79-108">本部分还包含本主题介绍了在移动特定之后必须遵循的过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="4ff79-108">This section also contains a topic that describes procedures that must be followed after moving particular [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="4ff79-109">完成为适合你的环境主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="4ff79-109">Complete the steps in the topic as appropriate for your environment.</span></span>  
  
-   [<span data-ttu-id="4ff79-110">如果不移动 MessageBox 数据库移动跟踪数据库时的注意事项</span><span class="sxs-lookup"><span data-stu-id="4ff79-110">Considerations When Moving the Tracking Database if the MessageBox Database Is Not Being Moved</span></span>](../technical-guides/before-you-move-the-tracking-database-if-messagebox-database-is-not-moving.md)