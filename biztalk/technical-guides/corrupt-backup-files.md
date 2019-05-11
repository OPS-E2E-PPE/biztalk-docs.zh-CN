---
title: 损坏的备份文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 155c7ab792dd77918561f3ebf630f6e13956d3e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306054"
---
# <a name="corrupt-backup-files"></a>损坏的备份文件
备份文件可能已损坏、 损坏或缺失。 如果发生这种情况，则无法还原至少一个文件。 还原作业之间发生故障的系统上搜索下一个有效的完整备份集。 在大多数情况下将需要强制源系统上执行完整备份。 如果没有此类集存在，还原作业失败，并且还每次运行时失败，直到到达时有效的完全备份集。 如果一组不存在，它用于修复环境。  
  
> [!NOTE]
>  考虑在其中方式[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]将备份数据写入到文件中，可能的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]即使备份失败，在实际写入的数据将报告已成功完成。 正在写入到的磁盘不在本地计算机和网络故障或中断发生时主要出现这种情况。 作为常规的预防措施，如果备份作业运行时出现网络故障，强制完整备份后解决网络连接问题。  
  
## <a name="see-also"></a>请参阅  
 [日志传送疑难解答](../technical-guides/troubleshooting-log-shipping.md)