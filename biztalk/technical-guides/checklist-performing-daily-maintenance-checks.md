---
title: "清单： 执行日常维护检查 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1abae6fb-abce-4f23-a07d-b32ba58cd070
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 281f33f0d880fdd217f3cac303526d7cfc0802f7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="checklist-performing-daily-maintenance-checks"></a>清单： 执行日常维护检查
本主题介绍了一些你应每天来帮助监视的状态检查的项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 必须一致地执行大部分这些检查，并将结果存档一段时间来获取最大的好处。 我们建议你自动执行日常维护检查尽可能。  
  
|步骤|参考|  
|-----------|---------------|  
|检查故障磁盘的硬件 RAID （可靠性检查）。|[管理磁盘](http://go.microsoft.com/fwlink/?LinkId=158666)(http://go.microsoft.com/fwlink/?LinkId=158666)。|  
|检查需要手动干预，例如挂起的消息 （可靠性检查） 的消息。|有关手动检查挂起的消息的信息，请参阅[调查业务流程、 端口和消息故障](http://go.microsoft.com/fwlink/?LinkId=154512)(http://go.microsoft.com/fwlink/?LinkId=154512)。|  
|检查任何错误或与各种数据库与 BizTalk Server 中，尤其是 MessageBox 数据库关联的问题。|运行 BizTalk MsgBoxViewer 工具，可从[BizTalk MsgBoxViewer-从此处下载该工具的最新版本](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。 此工具可分析 BizTalk MessageBox 和其他数据库并生成包含警告，如果任何 HTML 报表和与数据库相关的其他信息。 **提示：**还可以保存以供将来使用的报表。 与 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。|  
|如果任何，由 BizTalk MsgBoxViewer 工具，请解决问题。|运行终结器工具，可在[终止符](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。 此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。 有关如何使用 BizTalk MsgBoxViewer 工具相集成终止符工具的详细信息，请参阅[使用 BizTalk 终止符，若要解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。 **注意：** Microsoft，不支持使用此工具和 Microsoft 则没有此程序的适用性的保证。 使用此程序风险自负。|  
|检查事件日志中的错误和警告 （管理检查）。|BizTalk Server 错误和警告事件保存在应用程序日志中。 事件源，则"BizTalk Server"。|  
  
## <a name="see-also"></a>另请参阅  
 [维护可靠性](../technical-guides/maintaining-reliability.md)   
 [监视 BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)