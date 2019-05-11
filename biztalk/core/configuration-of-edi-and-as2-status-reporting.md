---
title: 配置 EDI 和 AS2 状态报告 |Microsoft Docs
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
ms.openlocfilehash: 7bf9108b2302097373f2930c8408fda13b787842
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391498"
---
# <a name="configuration-of-edi-and-as2-status-reporting"></a>配置 EDI 和 AS2 状态报告
本主题介绍的 EDI 和 AS2 状态报告，请启用和配置状态报告筛选器和显示列的 EDI、 批处理和 AS2 状态报告。  
  
## <a name="enabling-status-reporting"></a>启用状态报告  
 EDI 状态报告功能只能在服务器上提供如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]带有 EDI 和 BAM 子系统是该服务器上安装。 如果未安装 BAM 基础结构，不能启用 EDI/AS2 状态报告。 服务器还必须是 EDI 处理的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]分组，以便它有权访问 EDI 状态报告数据存储区。  
  
 如果将状态报告 UI 中的参与方的交换输入 EDI 消息条目**打开报告**中选择属性**常规属性**页**常规**选项卡中**协议属性**对话框。 仅当，如果未确定交换发送方或接收，将对这些交换中输入 EDI 消息条目**激活 EDI 报告**为 X12 和 EDIFACT 后备协议中选择属性。 这适用于 EDI 交换和相关 ACK 状态报表。 仅当已确定协议时，才启用批处理状态报表并**打开报告**中选择属性**常规属性**页**常规**在选项卡**协议属性**对话框。  
  
 将跟踪数据库中存储事务集，如果**存储消息负载以用于报告**中选择属性**常规属性**页**常规**在选项卡**协议属性**对话框中或**存储事务集/负载以用于报告**在后备协议属性中设置属性。 事务集详细信息和消息内容状态报告才可用，如果选择此属性。  
  
 如果将状态报告 UI 中输入 AS2 消息条目**打开报告**中选择属性**常规属性**页**常规**中的选项卡**协议属性**对话框。 若要将 AS2 消息或 Mdn 存储在不可否认数据库中，您必须选择中的相应属性**发送方不可否认**或**接收方不可否认**页的单向 AS2 协议在选项卡**协议属性**对话框。 这些属性启用的 AS2 消息和相关 MDN 状态报告。  
  
 会提供可靠的消息传送状态报告如果**MDN 未收到时重新发送 AS2 消息**上启用属性**发送方 MDN 设置**的单向AS2协议选项卡页**协议属性**对话框。  
  
 有关启用状态报告的详细信息，请参阅[启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md)。  
  
## <a name="status-report-filters-and-display-columns"></a>状态报告筛选器和显示列  
 EDI 和 AS2 状态报告，可自定义保存为状态报表数据的范围。 此，请在**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 显示状态报告窗格的任何状态报告之后, 您可以选择你想要在报表中看到的数据的范围。 为此，选择要包括在状态报告查询表达式中的筛选器值。  
  
 此外可以自定义状态报告中显示的数据的类型。  
  
> [!NOTE]
>  每当启用状态报告后，所有状态都将都保存在存储中。 通过自定义查询表达式或状态列，可以定义显示的已保存的数据。  
  
 有关详细信息，请参阅[配置 EDI 和 AS2 状态报告](../core/configuring-an-edi-and-as2-status-report.md)。  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [EDI 交换和相关 ACK 状态报告](../core/edi-interchange-and-correlated-ack-status-report.md)   
 [批处理状态报告](../core/batch-status-report.md)   
 [交换聚合报告](../core/interchange-aggregation-report.md)   
 [事务集聚合报告](../core/transaction-set-aggregation-report.md)   
 [AS2 消息和相关 MDN 状态报告](../core/as2-message-and-correlated-mdn-status-report.md)