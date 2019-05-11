---
title: 清单：存档和清除 BizTalk 跟踪数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- archiving [Tracking database], checklist
- checklists, purging [Tracking database]
- purging, checklist
- checklists, archiving [Tracking database]
ms.assetid: dccbf471-2add-498e-b292-287d9a94161b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ceb1ed0c31f3b984a38f4a6890e42e289d10dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357459"
---
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a><span data-ttu-id="f7ce1-102">清单：存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="f7ce1-102">Checklist: Archiving and Purging the BizTalk Tracking Database</span></span>

|<span data-ttu-id="f7ce1-103">步骤</span><span class="sxs-lookup"><span data-stu-id="f7ce1-103">Step</span></span>|<span data-ttu-id="f7ce1-104">参考</span><span class="sxs-lookup"><span data-stu-id="f7ce1-104">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="f7ce1-105">阅读存档和清除概述，若要进一步熟悉存档和清除跟踪数据的过程。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-105">Read the Archiving and Purging overview to become more familiar with the process of archiving and purging tracking data.</span></span>|[<span data-ttu-id="f7ce1-106">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="f7ce1-106">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="f7ce1-107">尽管您可以运行 DTA 清除和存档作业，为了提高安全性，使用您的登录凭据，但应具有所需的 SQL Server 凭据来运行 DTA 清除和存档作业来配置 BTS_BACKUP_USERS 角色。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-107">Although you can run the DTA Purge and Archive job using your logon credentials, for added security, you should configure the BTS_BACKUP_USERS role with the necessary SQL Server credentials to run the DTA Purge and Archive job.</span></span> <span data-ttu-id="f7ce1-108">这有助于防止特权提升。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-108">This helps to prevent elevation of privileges.</span></span>|[<span data-ttu-id="f7ce1-109">如何配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="f7ce1-109">How to Configure the BTS_BACKUP_USERS Role for Archiving and Purging Data from the BizTalk Tracking Database</span></span>](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|<span data-ttu-id="f7ce1-110">配置 DTA 清除和存档作业。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-110">Configure the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="f7ce1-111">如何配置 DTA 清除和存档作业</span><span class="sxs-lookup"><span data-stu-id="f7ce1-111">How to Configure the DTA Purge and Archive Job</span></span>](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|<span data-ttu-id="f7ce1-112">运行 DTA 清除和存档作业，该存档 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据和清除旧数据。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-112">Run the DTA Purge and Archive job, which archives the data in your BizTalk Tracking (BizTalkDTADb) database and purges old data.</span></span>|[<span data-ttu-id="f7ce1-113">如何从 BizTalk 跟踪数据库中清除数据</span><span class="sxs-lookup"><span data-stu-id="f7ce1-113">How to Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="f7ce1-114">（可选） 可以从 BizTalk 跟踪 (BizTalkDTADb) 数据库手动清除数据。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-114">Optionally, you can manually purge data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="f7ce1-115">如何从 BizTalk 跟踪数据库中手动清除数据</span><span class="sxs-lookup"><span data-stu-id="f7ce1-115">How to Manually Purge Data from the BizTalk Tracking Database</span></span>](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|<span data-ttu-id="f7ce1-116">启用自动存档 BizTalk 跟踪 (BizTalkDTADb) 数据库中数据验证。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-116">Enable automatic validation of the archived data from the BizTalk Tracking (BizTalkDTADb) database.</span></span>|[<span data-ttu-id="f7ce1-117">如何启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="f7ce1-117">How to Enable Automatic Archive Validation</span></span>](../core/how-to-enable-automatic-archive-validation.md)|  
|<span data-ttu-id="f7ce1-118">将跟踪的消息复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-118">Copy tracked messages into the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="f7ce1-119">这是为了清除数据使用 DTA 清除和存档作业所必需的。</span><span class="sxs-lookup"><span data-stu-id="f7ce1-119">This is required in order to purge data using the DTA Purge and Archive job.</span></span>|[<span data-ttu-id="f7ce1-120">如何将跟踪的消息复制到 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="f7ce1-120">How to Copy Tracked Messages into the BizTalk Tracking Database</span></span>](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  

## <a name="see-also"></a><span data-ttu-id="f7ce1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7ce1-121">See Also</span></span>  
 [<span data-ttu-id="f7ce1-122">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="f7ce1-122">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)