---
title: "如何避免磁盘 Contention1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8b4f8e10-16b0-45f9-8787-da16266da980
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 702665046dbaee77412675e4be0edc602dd9e7e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-disk-contention"></a>如何避免磁盘争用
BizTalk Server 是一种持久性的系统，因而对于高吞吐量的情况，MessageBox 可能会出现严重的资源争用。 缓慢的磁盘速度会进一步加重这种争用状况。 如果磁盘速度缓慢（低于 % 磁盘空闲时间），则会导致 SQL 保存锁定的时间较长（锁定等待时间长，锁定超时时间长），从而导致 MessageBox 表（Spool 和应用程序队列）变大，引起数据库膨胀，阻止功能被启用，最终导致较低的整体稳定吞吐量。  
  
 为避免磁盘争用，建议您采取以下措施：  
  
-   使用高速（多轴）磁盘。  
  
-   如果可能，在高速 SAN 上部署数据库。 如果多个数据库共享相同的磁盘，则建议在不同的专用磁盘上分别配置这些数据库。 此外，建议将 MessageBox 数据库的 MDF 文件和 LDF 文件分别放在不同的磁盘中。  
  
-   如果 SQL 可用的 CPU 资源严重不足，请考虑将 MessageBox 数据库部署到跟踪数据库所在服务器之外的其他专用服务器上。  
  
-   在设置之后 MessageBox 数据库的专用服务器，请考虑向上扩展通过升级 CPU 的和/或添加更多的 CPU。 MSDTC 日志保存在本地驱动器 (C:\WINDOWS\system32\Msdtc) 进行监视 SQL Server 上的本地驱动器。  
  
-   如果因 PageFile 或 MSDTC 日志而在本地驱动器上出现争用情况，请尝试将 PageFile 和/或 MSDTC 日志移到不同的驱动器上。