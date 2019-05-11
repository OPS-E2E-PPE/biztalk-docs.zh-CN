---
title: 监视和降低 DTC 日志文件的磁盘 I/O 争用 |Microsoft Docs
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
ms.openlocfilehash: 31168bd5b5643c6f60dec408c46e520d55b9a976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379422"
---
# <a name="monitoring-and-reducing-dtc-log-file-disk-io-contention"></a>监视和降低 DTC 日志文件磁盘 I/O 争用
大型事务环境中的磁盘 I/O 瓶颈可能会导致分布式事务处理协调器 (DTC) 日志文件。 使用支持事务，例如 SQL Server、 MSMQ 或 MQSeries，或在多 MessageBox 环境中的适配器时，也是如此。 事务性适配器使用 DTC 事务，多 MessageBox 环境进行广泛使用 DTC 事务。  
  
## <a name="monitoring-usage-in-clustered-and-non-clustered-environments"></a>监视群集和非群集环境中的使用情况  
 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘用于 DTC 日志文件驻留在 SQL Server 数据库服务器的磁盘 I/O 使用情况。  
  
 在 SQL Server 已群集的环境中，这是不需考虑尽可能因为日志文件将可能会具有多个心轴的快速 SAN 驱动器的共享驱动器。 因为它可以成为 DTC 日志文件时与其他占用大量磁盘的文件的共享磁盘上或非群集环境中的瓶颈，不过仍应监视磁盘 I/O 使用情况。  
  
## <a name="troubleshooting-dtc"></a>故障排除的 DTC  
 有关故障排除 DTC 的信息，请参阅"故障排除问题与 MSDTC"BizTalk Server 帮助中[ http://go.microsoft.com/fwlink/?LinkId=153237 ](http://go.microsoft.com/fwlink/?LinkId=153237)。  
  
## <a name="see-also"></a>请参阅  
 [清单：配置 Windows Server](../technical-guides/checklist-configuring-windows-server.md)