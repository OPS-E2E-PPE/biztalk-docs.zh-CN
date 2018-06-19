---
title: EDI 和 AS2 状态报告 |Microsoft 文档
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
ms.openlocfilehash: 31b08fd8222cee0cb0f04750eedcb32d06c28820
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241381"
---
# <a name="edi-and-as2-status-reporting"></a>EDI 和 AS2 状态报告
借助 EDI 状态报告，操作人员可以跟踪 EDI 和 AS2 传输的状态。 状态报告（如果已启用）提供了全面的文档交换事务状态信息，包括交换和与交换相关的确认信息。 这些报告提供与 EDI 和 AS2 消息的接收、验证、批处理和确认处理有关的数据。  
  
 可以使用这些报告获取挂起和未确认的交换、完整交换、错误方案或业务方案的状态。 使用这些报告，您可以执行以下操作：  
  
-   确认交换的接收  
  
-   列出等待确认的传出交换  
  
-   列出所有遭到拒绝的已接收交换  
  
-   列出报告为“已拒绝”或“部分接受”的传出交换。  
  
 状态报告中包含的数据是从交换控制段中获取的，如 ISA、TA1、GS、UNB 和 UNG（功能确认状态除外）。  
  
 **状态报告 UI**  
  
 从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台可以查看 EDI 和 AS2 状态报告。 从**组中心数据库**页**BizTalk 组**节点，必须指向 EDI 交换和关联的确认状态、 批处理状态和 AS2 消息和相关的 MDN 状态。 这些报告中的每个报告均提供了可包含在查询表达式中或从查询表达式中排除的一组状态参数，从而可使您生成所需的状态报告。  
  
 除了查看 EDI 交换的状态之外，还可以查看交换中的事务集。 通过在跟踪数据库 (BizTalkDTADb) 的 EDI 表中启用消息负载存储可实现这一点。 通过在状态报告 UI 中使用查看详细信息命令即可查看事务集。  
  
 您也可将出站或入站 AS2 消息或 MDN 存储在不可否认数据库中。 通过右键单击状态报告中的消息并选择相应命令即可查看事务集或 AS2 消息。  
  
 **状态报告组件**  
  
 以下是状态报告中涉及的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件：  
  
-   EDI 接收管道中的 EDI 拆装器，用于在传入交换的数据存储区中创建和更新状态条目  
  
-   EDI 发送管道中的 EDI 组装器，用于在传出交换的数据存储区中创建和更新状态条目  
  
-   用于存储状态报告条目的数据存储区。 即用于跟踪数据的 BAM 主导入数据库，以及用于 EDI 事务集和/或 AS2 消息内容的 BizTalk 跟踪数据库 (BizTalkDTADb) 中的 EDI Message Content 表  
  
-   状态报告 UI**组中心数据库**页[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，用来显示报告数据的状态  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的协议属性和后备协议属性，用于启用和配置状态报告  
  
-   可利用 BAM 基础结构的 DTA 和 SQL 分析服务器。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [EDI 和 AS2 的配置状态报告](../core/configuration-of-edi-and-as2-status-reporting.md)  
  
-   [类型的 EDI 和 AS2 状态报表](../core/types-of-edi-and-as2-status-reports.md)  
  
-   [对于 EDI 和 AS2 状态报表存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md)  
  
-   [如何将数据存储用于 EDI 和 AS2 状态报表](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)