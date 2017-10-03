---
title: "贸易合作伙伴协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e40a3847-ee36-4a75-ab50-def9b0caf07e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a62ada3317bc347a6d39af9fb2f983e02647e5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="trading-partner-agreement"></a>贸易合作伙伴协议
## <a name="overview"></a>概述
贸易合作伙伴协议 (TPA) 将在两个贸易合作伙伴之间被定义为一个确定且具有约束力的协议，以便通过特定的 B2B 协议处理消息。 协议集中了处理各种属性（来自合作伙伴双方的特定业务配置文件）的常见双向消息。 这是控制两个贸易合作伙伴之间业务事务的所有方面的全面集合。 TPA 通常源自每个合作伙伴的配置文件，可以自定义并覆盖需要的设置。  
  
 用更简单的术语说，TPA 是两个业务配置文件之间的一种了解，用于在双方互相交换 B2B 消息时使用特定的消息编码协议或特定的传输协议。  
  
 ![合作伙伴签订的协议的配置文件](../core/media/tradingpartneragreement.gif "TradingPartnerAgreement")  
  
 在上图中，没有分别到业务消息编码使用 X12 Fabrikam 的"Shipping"和"发票"配置文件和 Contoso 之间的协议 (**编码协议**) 和 AS2 传输交换消息 (**传输协议**)。 在各种业务配置文件之间可以存在许多此类协议。 例如，在“付款”和“发票”之间存在一个可使用 EDIFACT 消息编码标准的协议。 所有此类协议为所有配置文件用于贸易合作伙伴一对构成**合作关系**两者之间贸易合作伙伴。  
  
## <a name="bi-directional-agreements"></a>双向协议  
 两个业务配置文件之间的每个协议都是双向的。 例如，“发运”和“发票”业务配置文件之间的协议将包含可处理消息的属性。  
  
-   由“发运”配置文件从“发票”配置文件接收，并且  
  
-   由“发运”配置文件发送到“发票”配置文件  
  
 用更简单的术语说，双向协议就是两个单向协议的集合。 一个单向协议可被视作定义消息事务如何从参与方 A 发生到参与方 B 的属性集合。另一个单向协议可被视作定义消息事务如何从参与方 B 发生到参与方 A 的属性集合。  
  
## <a name="considerations-when-defining-an-agreement"></a>定义一个协议时的注意事项  
 在创建贸易合作伙伴协议时，您必须考虑以下几点：  
  
-   对于彼此互相交换 B2B 消息的两个业务配置文件，定义一个消息编码协议是必需的。 各部门可能只选择 AS2 协议，只要他们希望使用 AS2 协议传输消息。 例如当业务部门选择通过电子邮件传输消息，则不需要 AS2 协议。  
  
-   如果两个业务配置文件同时支持 X12 和 EDIFACT 编码，并且两个业务配置文件都同意在交换消息时使用两种编码协议，则每一个协议应当有单独的协议。 应当有一个适用于 X12 协议的协议，一个适用于 EDIFACT 协议的协议。 不能有一个可用于这两个协议的单个协议。  
  
-   适用于 X12 和 EDIFACT 消息的编码协议和传输协议（适用于 AS2）都不能成为协议的一部分。 您必须为两者创建单独的协议。  
  
## <a name="global-or-fallback-agreement"></a>全局或后备协议  
 特定的业务组织可能选择 B2B 处理机制的单数集，而不区分参与特定 B2B 消息传输的合作伙伴。 实际上，这类业务组织只有一个与所有其他贸易合作伙伴共享的常见 B2B 协议设置。 此外，由于这类组织不需要特定合作伙伴的特定设置，因此 B2B 协议设置视为贸易合作伙伴本身而不是为贸易业务配置文件定义的。 在[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，此类企业组织反映为**全局贸易合作伙伴**。 需要表示为全局贸易合作伙伴的企业与之有交易其他企业使用称为全局贸易合作伙伴协议**全局贸易合作伙伴协议**。 这些协议符合为全球贸易合作伙伴定义的消息编码与协议设置。  
  
 在全球级别定义的设置在以下情况下也很有用，当两个贸易合作伙伴之间的特定于配置文件的协议设置，没有制订一个贸易合作伙伴协议时。 在这一情况下，驻留 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] 的组织可使用为合作伙伴定义的协议设置，来制订与其他贸易业务配置文件的协议。 在这种情况下，协议到达使用全局协议设置为伙伴称为定义**回退贸易合作伙伴协议**。  

## <a name="learn-next"></a>了解下一步

[总结： 定义贸易合作伙伴管理解决方案](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
  
## <a name="see-also"></a>另请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)