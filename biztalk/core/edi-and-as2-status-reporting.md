---
title: EDI 和 AS2 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a9e58b29-9be0-41d6-ad35-1aae28e1a784
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bf0f3f5b5e6c50a02451215f56dbc3ec4c2939a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350582"
---
# <a name="edi-and-as2-status-reporting"></a>EDI 和 AS2 状态报告
EDI 状态报告，操作人员可以跟踪 EDI 和 AS2 传输的状态。 如果启用，则状态报告提供的文档交换事务，包括交换和与交换的任何确认的全面状态。 这些报表提供有关回执、 验证、 批处理和确认处理有关 EDI 和 AS2 消息的数据。  
  
 这些报表可用于获取挂起的状态和未确认的交换、 完整交换、 错误方案或业务方案。 使用这些报表，可以执行以下操作：  
  
- 确认交换的接收  
  
- 列出等待确认的传出交换  
  
- 列出所有拒绝收到的交换  
  
- 接受列表作为被拒绝或部分报告的传出交换。  
  
  状态报告中包含的数据是从交换控制段，例如 ISA、 TA1、 GS、 UNB 和 UNG （除了功能确认状态中） 获取。  
  
  **状态报告 UI**  
  
  EDI 和 AS2 状态报告中有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 从**组中心**页**BizTalk 组**节点，设有指向 EDI 交换和相关的确认状态、 批处理状态以及 AS2 消息和相关的 MDN 状态。 每个报告提供了一系列可以包括或排除在查询表达式中，因此可以生成所需的状态报告的状态参数。  
  
  除了查看 EDI 交换的状态，还可以将交换中查看事务集。 则执行操作来启用消息跟踪 (BizTalkDTADb) 数据库的 EDI 表中的有效负载的存储。 可以通过使用状态报告 UI 中查看详细信息命令来查看事务集。  
  
  此外可以在不可否认数据库中存储入站或出站 AS2 消息或 Mdn。 可以通过右键单击状态报表中的消息并选择相应的命令来查看事务集或 AS2 消息。  
  
  **状态报告组件**  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]状态报告中涉及的组件如下：  
  
- EDI 拆装器在 EDI 接收管道，用于创建和更新状态条目将传入交换的数据存储中  
  
- EDI 组装器中的 EDI 发送管道，用于创建和更新在传出交换的数据存储中的状态条目  
  
- 数据存储的存储状态报告条目。 这些是用于跟踪数据和 BizTalk 跟踪数据库 (BizTalkDTADb) 的 EDI 事务集和/或 AS2 消息内容的 EDI Message Content 表的 BAM 主导入数据库  
  
- 状态报告 UI**组中心**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，用于显示状态报告数据  
  
- 协议属性和后备协议属性中的选项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，用于启用和配置状态报告  
  
- DTA 和 SQL 分析服务器利用 BAM 基础结构。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置 EDI 和 AS2 状态报告功能](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [EDI 和 AS2 状态报告的类型](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [为 EDI 和 AS2 状态报告存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [如何为 EDI 和 AS2 状态报告存储数据](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)