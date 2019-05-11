---
title: BAM 事件总线服务存储过程 |Microsoft Docs
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
ms.openlocfilehash: 138ca26becc8b35207219dd050e13c8557066301
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358526"
---
# <a name="bam-event-bus-service-stored-procedures"></a>BAM 事件总线服务存储过程
使用以下存储的过程来管理 BAM 事件总线服务：  
  
-   若要暂停 BAM 事件总线服务，执行 （不带提交事务） 的 BAM 数据库的事务中 TDDS_BlockTDDS 存储过程。 若要恢复 BAM 事件总线服务，请提交 TDDS_BlockTDDS 事务。  
  
-   若要启用多台计算机上的 BAM 事件总线服务，标识要用于跟踪的主机，然后将这些计算机加入到跟踪主机。  
  
-   若要设置会话超时和检测信号间隔，请使用 TDDS_UpdateSettings 存储过程。 只有 BTS_ADMIN_USERS 组的成员有权执行此存储的过程。  
  
     TDDS_UpdateSettings 存储过程具有以下参数：  
  
    -   @RefreshInterval int。设置为大于 60 秒。  
  
    -   @SqlCommandTimeout int。设置为小于 RefreshInterval。  
  
    -   @SessionTimeout int。设置为大于 RefreshInterval 两次。  
  
    -   @EventLoggingInterval nvarchar(16)。 设置为大于 60 秒。  
  
    -   @RetryCount int。设置为大于 60 秒  
  
    -   @ThreadPerSession int。此参数是已过时。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)