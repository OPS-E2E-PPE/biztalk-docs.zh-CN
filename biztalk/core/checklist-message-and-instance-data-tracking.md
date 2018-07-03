---
title: 清单： 消息和实例数据跟踪 |Microsoft Docs
description: 跟踪消息、 实例和 BizTalk Server 中的项目时的最佳做法
ms.custom: ''
ms.date: 02/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4b5b614-23e5-4895-9c66-417b55dee43c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 353f3669f79bb7481dd5588105dab59e83b011ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984950"
---
# <a name="checklist-message-and-instance-data-tracking"></a>清单： 消息和实例数据跟踪

|步骤|参考|  
|----------|---------------|  
|查看消息和服务实例数据跟踪的安全注意事项|[消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)|  
|查看消息和服务实例数据跟踪的最佳实践|[消息和实例数据跟踪的最佳做法](../core/best-practices-for-message-and-instance-data-tracking.md)|  
|确保所有 MessageBox 数据库上均运行 SQL Server 代理服务|通过 SQL Server 代理，消息正文可用于消息跟踪和 WMI，从而允许您运行清理 MessageBox 数据库的作业。<br /><br /> 有关 SQL Server 代理和 SQL Server 代理服务的详细信息，请参阅 SQL Server 联机丛书。|  
|在 BizTalk Server 管理控制台中的项目配置跟踪|[业务流程跟踪](how-to-configure-tracking-for-an-orchestration.md)<br/>[发送端口跟踪](how-to-configure-tracking-for-a-send-port.md)<br/>[接收端口跟踪](how-to-configure-tracking-for-a-receive-port.md)<br/>[策略跟踪](how-to-configure-tracking-for-a-policy.md)<br/>[跟踪架构](how-to-configure-tracking-for-a-schema.md)<br/>[跟踪的管道](how-to-configure-tracking-for-a-pipeline.md)|  

## <a name="see-also"></a>请参阅  
 [消息和实例数据跟踪的最佳做法](../core/best-practices-for-message-and-instance-data-tracking.md)
