---
title: BAM 事件总线服务存储过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stored procedures, Even Bus Service [BAM]
- Event Bus Service [BAM], stored procedures
ms.assetid: 18a7bd40-50ce-44f2-88ae-45a2e3c8d3f4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f44dce10113b8a3a85b7c1dd177f637933b582ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230333"
---
# <a name="bam-event-bus-service-stored-procedures"></a>BAM 事件总线服务存储过程
使用以下存储的过程来管理与 BAM 事件总线服务：  
  
-   若要暂停 BAM 事件总线服务，在事务中的 TDDS_BlockTDDS 存储过程 （不带提交事务） 对 BAM 数据库执行。 若要恢复 BAM 事件总线服务，提交 TDDS_BlockTDDS 事务。  
  
-   若要启用多台计算机上的 BAM 事件总线服务，确定哪些主机用于对其进行跟踪，然后将这些计算机加入到跟踪主机。  
  
-   若要设置会话超时和检测信号间隔，请使用 TDDS_UpdateSettings 存储过程。 只有 BTS_ADMIN_USERS 组的成员有权执行此存储的过程。  
  
     TDDS_UpdateSettings 存储过程具有以下参数：  
  
    -   @RefreshIntervalint。设置为大于 60 秒。  
  
    -   @SqlCommandTimeoutint。设置为小于号 RefreshInterval。  
  
    -   @SessionTimeoutint。设置为大于 RefreshInterval 两次。  
  
    -   @EventLoggingIntervalnvarchar(16)。 设置为大于 60 秒。  
  
    -   @RetryCountint。将设置为大于 60 秒  
  
    -   @ThreadPerSessionint。此参数已废弃不用。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM](../core/managing-bam.md)