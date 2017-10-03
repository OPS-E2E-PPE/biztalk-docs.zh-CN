---
title: "损坏的备份文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc48197c-944a-4f0a-ba01-8e1d91c88ad3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fda5acae756fd2c4d0afc0263bc723af3ba77e15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="corrupt-backup-files"></a>损坏的备份文件
备份文件可能已损坏、 损坏或缺失。 如果发生这种情况，则无法还原至少一个文件。 遇到的失败的系统上的还原作业搜索下一个有效的完整备份集。 在大多数情况下它将需要强制源系统上进行完整备份。 如果没有此类集存在，恢复作业将失败并有效的完整备份集到达之前，每次后续运行也会失败。 如果存在一组，它用于修复环境。  
  
> [!NOTE]  
>  由于在其中的方式[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]备份数据写入到文件，它是可能的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]将报告成功完成，即使数据实际写入期间备份失败。 主要，都将写入到的磁盘不是为本地计算机和网络故障或中断发生时，将出现这种情况。 作为常规的预防措施，如果备份作业运行时，将发生网络故障，强制完整备份后解决网络连接问题。  
  
## <a name="see-also"></a>另请参阅  
 [故障排除日志传送](../technical-guides/troubleshooting-log-shipping.md)