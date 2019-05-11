---
title: 部分备份集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baacc7a30a79084430ce570fc135b92e07586779
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291332"
---
# <a name="partial-backup-sets"></a>部分备份集
在源系统上备份数据库，可能发生的问题导致部分备份集。 当发生这种情况时，Master.dbo.bts_LogShippingHistory 表将包含在 0 **SetComplete**列集中的所有记录。  
  
 无法还原这些设置。 结果是日志备份集链已中断。 必须忽略集，以及所有日志备份集后，到下一个完整备份集。 还原作业将自动寻找下一个有效的完整备份集。 如果没有找到一个，它将失败，并将还原的设置，以便修复目标环境。  
  
 在大多数情况下源系统将检测部分备份集已发生，并将自动生成如果它配置为执行此操作运行下一次完整备份集。  
  
> [!NOTE]  
>  此问题的最常见原因是目标系统上的文件组没有足够的磁盘空间。  
  
## <a name="see-also"></a>请参阅  
 [日志传送疑难解答](../technical-guides/troubleshooting-log-shipping.md)