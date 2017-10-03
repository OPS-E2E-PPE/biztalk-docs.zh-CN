---
title: "部分备份集 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b9f15c0-4d31-4322-ac0a-8efdeed6f71e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9740cb0f45d6bb46c13a95e50e4717ef142b164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="partial-backup-sets"></a>部分备份集
在源系统上备份数据库，可能发生的问题导致部分的备份集。 当发生这种情况时，Master.dbo.bts_LogShippingHistory 表将包含在 0 **SetComplete**集中的所有记录的列。  
  
 无法还原这些设置。 因此，日志备份集链已中断。 设置必须忽略，作为以及所有日志备份集后，到下一步的完整备份集。 还原作业将自动查找下一个有效的完整备份集。 如果它未找到一个，它无法正常工作，并将还原的设置，以便修复目标环境。  
  
 在大多数情况下的源系统将检测部分的备份集发生，并将自动生成的下次运行如果它被配置为这样做完整备份集。  
  
> [!NOTE]  
>  此问题的最常见原因是目标系统上的文件组的磁盘空间不足。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除日志传送](../technical-guides/troubleshooting-log-shipping.md)