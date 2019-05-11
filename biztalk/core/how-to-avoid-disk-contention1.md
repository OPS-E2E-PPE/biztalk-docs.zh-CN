---
title: 如何避免磁盘 Contention1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9204fc727339a5fbab31cdf54bc8de488e588dda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342672"
---
# <a name="how-to-avoid-disk-contention"></a>如何避免磁盘争用
BizTalk Server 设计为永久性系统因而对于高吞吐量方案中，MessageBox 可能会出现严重的争用现象。 这种争用可以将变得更加严重缓慢的磁盘。 如果磁盘是缓慢 （低于 %磁盘空闲时间），则会导致 SQL 保存锁定更长 （高锁定等待时间和高锁定超时） 这可能导致 MessageBox 表 （Spool 和应用程序队列） 不断增长，引起数据库膨胀，最终限制从而导致较低的整体稳定吞吐量。  
  
 为了避免磁盘争用，建议您以下：  
  
-   使用高速 （多轴） 磁盘。  
  
-   如果可能，部署高速 SAN 上的数据库。 如果多个数据库共享相同的磁盘，建议在单独的专用磁盘上配置这些。 此外建议来分隔到不同的磁盘上的 MessageBox 数据库的 MDF 和 LDF 文件。  
  
-   如果 SQL 可用的 CPU，请考虑将 MessageBox 数据库是从跟踪数据库的单独的专用服务器上。  
  
-   设置后将 MessageBox 数据库专用服务器，请考虑通过升级 CPU 的和/或增加 CPU 的扩展。 监视 SQL Server 上的本地驱动器，因为 MSDTC 日志保存在本地驱动器 (C:\WINDOWS\system32\Msdtc)。  
  
-   如果由于页面文件或 MSDTC 日志的本地驱动器上的争用，请尝试将 PageFile 和/或 MSDTC 日志移到单独的驱动器。