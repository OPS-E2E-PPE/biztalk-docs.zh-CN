---
title: EDI 和 AS2 的配置状态报告 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c7fa76d-0d03-4b74-9a3a-60f4bd0534ff
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051a03b735f3714910b415d5418ff84089c57940
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233613"
---
# <a name="configuration-of-edi-and-as2-status-reporting"></a>配置 EDI 和 AS2 状态报告功能
本主题说明启用 EDI 和 AS2 状态报告功能和配置状态报告筛选器，并显示 EDI、批处理和 AS2 状态报告的列。  
  
## <a name="enabling-status-reporting"></a>启用状态报告  
 EDI 状态报告功能只能在安装了带有 EDI 和 BAM 子系统的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的服务器上可用。 如果未安装 BAM 基础结构，则无法启用 EDI/AS2 状态报告功能。 该服务器还必须是 EDI 处理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组的成员，这样才能访问 EDI 状态报告数据存储区。  
  
 将为状态报表 UI 中的参与方的交换输入 EDI 消息条目，如果**打开 reporting**中选择属性**常规属性**页**常规**选项卡中**协议属性**对话框。 仅当，如果发送方或正在发送不确定的交换，将为这些交换中输入 EDI 消息条目**激活 EDI 报告**回退 X12 和 EDIFACT 协议中选择属性。 这适用于“EDI 交换和相关 ACK 状态”报告。 仅当协议已确定时，才会启用批处理状态报表和**打开 reporting**中选择属性**常规属性**页**常规**选项卡中**协议属性**对话框。  
  
 将跟踪数据库中存储的事务集，如果**用于报告的应用商店消息负载**中选择属性**常规属性**页**常规**选项卡中**协议属性**对话框或**存储事务的一组负载，可用于报告**回退协议属性中设置属性。 仅当选择了此属性时，才能使用“事务集详细信息”和“消息内容”状态报告。  
  
 将在状态报表 UI 中输入 AS2 消息条目，如果**打开 reporting**中选择属性**常规属性**页**常规**中的选项卡**协议属性**对话框。 若要将 AS2 消息或 Mdn 存储在不可否认性数据库中，你必须选择中的相应属性**发件人不可否认性**或**接收方不可否认性**单向的 AS2 协议页选项卡中**协议属性**对话框。 这些属性将启用“AS2 消息和相关 MDN 状态”报告。  
  
 将可用的可靠消息传送状态报告如果**重新发送 AS2 消息如果未收到 MDN**上启用属性**发件人 MDN 设置**的单向AS2协议选项卡页**协议属性**对话框。  
  
 有关启用状态报告的详细信息，请参阅[启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md)。  
  
## <a name="status-report-filters-and-display-columns"></a>状态报告筛选器和显示列  
 使用 EDI 和 AS2 状态报告功能，可以自定义为状态报告保存的数据范围。 因此在执行**组中心数据库**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 显示出任何状态报告的状态报告窗格后，就可以选择要在报告中查看的数据范围。 您可通过选择包括在状态报告查询表达式中的筛选器值来执行此操作。  
  
 您还可以自定义状态报告中显示的数据类型。  
  
> [!NOTE]
>  如果启用了状态报告，则所有状态都将保存在存储区中。 通过自定义查询表达式或状态列，可以定义要显示的保存数据。  
  
 有关详细信息，请参阅[配置 EDI 和 AS2 状态报表](../core/configuring-an-edi-and-as2-status-report.md)。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [EDI 交换和关联的 ACK 状态报表](../core/edi-interchange-and-correlated-ack-status-report.md)   
 [Batch 状态报表](../core/batch-status-report.md)   
 [交换聚合报表](../core/interchange-aggregation-report.md)   
 [事务集聚合报表](../core/transaction-set-aggregation-report.md)   
 [AS2 消息和相关的 MDN 状态报表](../core/as2-message-and-correlated-mdn-status-report.md)