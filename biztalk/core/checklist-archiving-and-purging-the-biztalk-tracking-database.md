---
title: "清单： 存档和清除跟踪数据库 BizTalk |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22e97ac12e6b6b304318f57f309767ec7c63815f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a><span data-ttu-id="44bda-102">清单： 存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="44bda-102">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>
|<span data-ttu-id="44bda-103">步骤</span><span class="sxs-lookup"><span data-stu-id="44bda-103">Step</span></span>|<span data-ttu-id="44bda-104">参考</span><span class="sxs-lookup"><span data-stu-id="44bda-104">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="44bda-105">阅读存档和清除概述，以便进一步熟悉存档和清除跟踪数据的过程。</span><span class="sxs-lookup"><span data-stu-id="44bda-105">Read the Archiving and Purging overview to become more familiar with the process of archiving and purging tracking data.</span></span>|[<span data-ttu-id="44bda-106">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="44bda-106">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="44bda-107">尽管可以使用您的登录凭据来运行 DTA 清除和存档作业，但为了提高安全性，应该配置具有所需 SQL Server 凭据的 BTS_BACKUP_USERS 角色来运行 DTA 清除和存档作业。</span><span class="sxs-lookup"><span data-stu-id="44bda-107">Although you can run the DTA Purge and Archive job using your logon credentials, for added security, you should configure the BTS_BACKUP_USERS role with the necessary SQL Server credentials to run the DTA Purge and Archive job.</span></span> <span data-ttu-id="44bda-108">这样有助于防止特权提升。</span><span class="sxs-lookup"><span data-stu-id="44bda-108">This helps to prevent elevation of privileges.</span></span>|[<span data-ttu-id="44bda-109">如何配置用于存档和清除数据从跟踪数据库 BizTalk BTS_BACKUP_USERS 角色</span><span class="sxs-lookup"><span data-stu-id="44bda-109">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|<span data-ttu-id="44bda-110">配置 DTA 清除和存档作业。</span><span class="sxs-lookup"><span data-stu-id="44bda-110">Configure the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="44bda-111">如何配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="44bda-111">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|<span data-ttu-id="44bda-112">运行 DTA 清除和存档作业，该作业会将数据存档到 BizTalk 跟踪 (BizTalkDTADb) 数据库中并清除旧的数据。</span><span class="sxs-lookup"><span data-stu-id="44bda-112">Run the DTA Purge and Archive job, which archives the data in your BizTalk Tracking (BizTalkDTADb) database and purges old data.</span></span>|[<span data-ttu-id="44bda-113">如何从 BizTalk 跟踪数据库清除数据</span><span class="sxs-lookup"><span data-stu-id="44bda-113">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="44bda-114">另外，可以从 BizTalk 跟踪 (BizTalkDTADb) 数据库中手动清除数据。</span><span class="sxs-lookup"><span data-stu-id="44bda-114">Optionally, you can manually purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="44bda-115">如何从 BizTalk 跟踪数据库手动清除数据</span><span class="sxs-lookup"><span data-stu-id="44bda-115">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="44bda-116">对 BizTalk 跟踪 (BizTalkDTADb) 数据库中的存档数据启用自动验证。</span><span class="sxs-lookup"><span data-stu-id="44bda-116">Enable automatic validation of the archived data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="44bda-117">如何启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="44bda-117">How to Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)|  
|<span data-ttu-id="44bda-118">将跟踪的消息复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库中。</span><span class="sxs-lookup"><span data-stu-id="44bda-118">Copy tracked messages into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="44bda-119">使用 DTA 清除和存档作业清除数据时，要求进行此操作。</span><span class="sxs-lookup"><span data-stu-id="44bda-119">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="44bda-120">如何将跟踪的消息复制到跟踪数据库 BizTalk</span><span class="sxs-lookup"><span data-stu-id="44bda-120">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  
  
## <a name="see-also"></a><span data-ttu-id="44bda-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44bda-121">See Also</span></span>  
 [<span data-ttu-id="44bda-122">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="44bda-122">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)