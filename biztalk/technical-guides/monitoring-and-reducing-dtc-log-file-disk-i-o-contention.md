---
title: 监视和减少 DTC 日志文件的磁盘 I/O 争用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8b968dd-216e-454f-9224-aaf92ffd363b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca71b55c2f9e18875ef67e840e8dac18a81dddac
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007414"
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a>监视和减少 DTC 日志文件的磁盘 I/O 争用
分布式事务处理协调器 (DTC) 日志文件可以成为大型事务环境中的磁盘 I/O 瓶颈。 这在使用支持事务，如 SQL Server、 MSMQ 或 MQSeries，或在多 MessageBox 环境中的适配器时尤其如此。 事务的适配器使用 DTC 事务，以及多 MessageBox 环境广泛利用 DTC 事务。  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a>监视群集和非群集环境中的使用情况  
 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘 DTC 日志文件驻留在 SQL Server 数据库服务器上的磁盘 I/O 使用情况。  
  
 在环境中在群集 SQL Server，这是不尽可能考虑因为日志文件已将共享的驱动器，可能会具有多个轴的快速 SAN 驱动器上。 由于它可能成为瓶颈在非群集环境或 DTC 日志文件时与其他占用大量磁盘的文件的共享磁盘上，不过仍应监视磁盘 I/O 使用情况。  
  
## <a name="troubleshooting-dtc"></a>故障排除 DTC  
 有关故障排除 DTC 的信息，请参阅"故障排除问题与 MSDTC"在 BizTalk Server 帮助中[http://go.microsoft.com/fwlink/?LinkId=153237](http://go.microsoft.com/fwlink/?LinkId=153237)。  
  
## <a name="see-also"></a>另请参阅  
 [清单：配置 Windows Server](../technical-guides/checklist-configuring-windows-server.md)