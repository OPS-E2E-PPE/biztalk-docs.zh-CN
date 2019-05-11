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
# <a name="checklist-archiving-and-purging-the-biztalk-tracking-database"></a>清单：存档和清除 BizTalk 跟踪数据库

|步骤|参考|  
|----------|---------------|  
|阅读存档和清除概述，若要进一步熟悉存档和清除跟踪数据的过程。|[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)|  
|尽管您可以运行 DTA 清除和存档作业，为了提高安全性，使用您的登录凭据，但应具有所需的 SQL Server 凭据来运行 DTA 清除和存档作业来配置 BTS_BACKUP_USERS 角色。 这有助于防止特权提升。|[如何配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)|  
|配置 DTA 清除和存档作业。|[如何配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)|  
|运行 DTA 清除和存档作业，该存档 BizTalk 跟踪 (BizTalkDTADb) 数据库中的数据和清除旧数据。|[如何从 BizTalk 跟踪数据库中清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)|  
|（可选） 可以从 BizTalk 跟踪 (BizTalkDTADb) 数据库手动清除数据。|[如何从 BizTalk 跟踪数据库中手动清除数据](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)|  
|启用自动存档 BizTalk 跟踪 (BizTalkDTADb) 数据库中数据验证。|[如何启用自动存档验证](../core/how-to-enable-automatic-archive-validation.md)|  
|将跟踪的消息复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库。 这是为了清除数据使用 DTA 清除和存档作业所必需的。|[如何将跟踪的消息复制到 BizTalk 跟踪数据库](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)|  

## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)