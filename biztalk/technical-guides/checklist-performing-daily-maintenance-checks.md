---
title: 清单：执行每日维护检查 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1abae6fb-abce-4f23-a07d-b32ba58cd070
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d72fdb8a52d24129c695287334af248bf3e015d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242672"
---
# <a name="checklist-performing-daily-maintenance-checks"></a>清单：执行每日维护检查
本主题介绍了一些应检查每日来帮助监视的状态的项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。 必须一致地执行这些检查的大部分，并将结果存档一段时间来获取最大的好处。 我们建议你自动执行日常维护检查只要有可能。  
  
|步骤|参考|  
|-----------|---------------|  
|检查硬件 RAID （可靠性检查） 中失败的磁盘。|[管理磁盘](http://go.microsoft.com/fwlink/?LinkId=158666)(http://go.microsoft.com/fwlink/?LinkId=158666)。|  
|检查消息需要手动干预，例如挂起的消息 （可靠性检查）。|有关手动检查挂起的消息的信息，请参阅[调查业务流程、 端口和消息失败](http://go.microsoft.com/fwlink/?LinkId=154512)(http://go.microsoft.com/fwlink/?LinkId=154512)。|  
|检查任何错误或问题与各种数据库与 BizTalk Server，尤其是 MessageBox 数据库相关联。|运行 BizTalk MsgBoxViewer 工具可从[BizTalk MsgBoxViewer-在此处下载该工具的最新版本](http://go.microsoft.com/fwlink/?LinkId=151930)(http://go.microsoft.com/fwlink/?LinkId=151930)。 此工具会分析 BizTalk MessageBox 和其他数据库，并生成包含警告，如果有一份 HTML 报告以及与数据库相关的其他信息。 **提示：** 此外可以保存以供将来使用的报表。 BizTalk 应用程序的问题进行故障排除时，这些报表可能很有用。 **注意：** 使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。|  
|解决问题，如果任何，标识由 BizTalk MsgBoxViewer 工具。|运行终结器工具，网址[终止符](http://go.microsoft.com/fwlink/?LinkId=151931)(http://go.microsoft.com/fwlink/?LinkId=151931)。 此工具使用户能够轻松地解决由 BizTalk MsgBoxViewer 工具标识的任何问题。 有关如何使用 BizTalk MsgBoxViewer 工具相集成的终结器工具的详细信息，请参阅[使用 BizTalk 终止符，以解决问题由 BizTalk MsgBoxViewer](http://go.microsoft.com/fwlink/?LinkId=151932) (http://go.microsoft.com/fwlink/?LinkId=151932)。 **注意：** 使用此工具不受 Microsoft，因此 Microsoft 不保证此程序的适用性。 使用此程序是完全由您自己承担。|  
|检查事件日志中的错误和警告 （管理检查）。|BizTalk Server 错误和警告事件保存在应用程序日志中。 事件源，"BizTalk Server"。|  
  
## <a name="see-also"></a>请参阅  
 [维护可靠性](../technical-guides/maintaining-reliability.md)   
 [监视 BizTalk Server2](../technical-guides/monitoring-biztalk-server2.md)