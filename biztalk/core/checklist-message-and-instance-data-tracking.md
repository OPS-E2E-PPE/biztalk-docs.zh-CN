---
title: 清单： 消息和实例数据跟踪 |Microsoft 文档
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
ms.openlocfilehash: e17f9dabce292e043d1698b4f34a13e89d779d14
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710400"
---
# <a name="checklist-message-and-instance-data-tracking"></a>清单： 消息和实例数据跟踪
|步骤|參考|  
|----------|---------------|  
|查看跟踪的安全注意事项的消息和服务实例数据|[消息和实例数据跟踪的安全注意事项](../core/security-considerations-for-message-and-instance-data-tracking.md)|  
|查看跟踪的最佳做法的消息和服务实例数据|[消息和实例数据跟踪的最佳做法](../core/best-practices-for-message-and-instance-data-tracking.md)|  
|确保所有 MessageBox 数据库上均运行 SQL Server 代理服务|通过 SQL Server 代理，消息正文可用于消息跟踪和 WMI，从而允许您运行清理 MessageBox 数据库的作业。<br /><br /> 有关 SQL Server 代理和 SQL Server 代理服务的详细信息，请参阅 SQL Server 联机丛书。|  
|在 BizTalk Server 管理控制台中的项目上配置跟踪|[跟踪的业务流程](how-to-configure-tracking-for-an-orchestration.md)<br/>[发送端口跟踪](how-to-configure-tracking-for-a-send-port.md)<br/>[接收端口跟踪](how-to-configure-tracking-for-a-receive-port.md)<br/>[跟踪的策略](how-to-configure-tracking-for-a-policy.md)<br/>[跟踪的架构](how-to-configure-tracking-for-a-schema.md)<br/>[跟踪的管道](how-to-configure-tracking-for-a-pipeline.md)|  
  
## <a name="see-also"></a>另请参阅  
 [消息和实例数据跟踪的最佳做法](../core/best-practices-for-message-and-instance-data-tracking.md)
