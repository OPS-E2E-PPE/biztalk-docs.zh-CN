---
title: 贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e40a3847-ee36-4a75-ab50-def9b0caf07e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d86151e43b6a441b5ce4c48f4ba5ec2b0f29005
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313405"
---
# <a name="trading-partner-agreement"></a>贸易合作伙伴协议
## <a name="overview"></a>概述
贸易合作伙伴协议 (TPA) 被指通过特定 B2B 协议处理消息的两个贸易合作伙伴之间的权威且绑定协议。 协议将来自两个合作伙伴的特定业务配置文件的组合在一起的常见双向消息处理属性。 它是用于管理两个贸易合作伙伴之间业务事务的所有方面的全面集合。 TPA 通常源自每个合作伙伴，能够自定义并覆盖所需的设置的配置文件。  
  
 简言之，TPA 是一种了解两个业务配置文件使用特定的消息编码协议或特定的传输协议交换 B2B 消息彼此之间。  
  
 ![合作伙伴配置文件与协议](../core/media/tradingpartneragreement.gif "TradingPartnerAgreement")  
  
 在上图中，没有 Fabrikam 的"发运"和"发票"配置文件和 Contoso 之间分别向使用 X12 编码的业务消息的协议 (**编码协议**) 和 AS2 传输交换消息 (**传输协议**)。 可以有各种业务配置文件之间的许多此类协议。 例如，可以是要使用的 EDIFACT 消息编码标准的"付款"和"发票"配置文件之间的协议。 所有此类为所有配置文件的协议对贸易合作伙伴构成**合作关系**之间这两个贸易合作伙伴。  
  
## <a name="bi-directional-agreements"></a>双向协议  
 两个业务配置文件之间的每个协议是双向的。 例如，"发运"和"发票"业务配置文件之间的协议将包含用于处理消息属性：  
  
- 收到的"发票"配置文件中的"发运"配置文件和  
  
- 发送到"发票"配置文件的"发运"配置文件  
  
  更简单的说，双向协议是两个单向协议的集合。 一个单向协议可被视为一系列定义消息事务如何从参与方 A 的参与方 b。 发生的属性其他单向协议可被视为一系列属性用于定义如何消息事务发生从参与方 B 到参与方 a。  
  
## <a name="considerations-when-defining-an-agreement"></a>定义一个协议时的注意事项  
 创建贸易合作伙伴协议时，必须考虑以下几点：  
  
-   对于交换 B2B 消息与每个其他的两个业务配置文件，定义一个消息编码协议是必需的。 部门可以选择他们想要使用 AS2 协议传输消息的情况下，才有 AS2 协议。 例如，如果业务部门选择通过电子邮件传输消息，则不需要 AS2 协议。  
  
-   如果两个业务配置文件支持 X12 和 EDIFACT 编码，并且这两个业务配置文件同意使用这两种编码协议交换消息时，应单独针对每个协议的协议。 应该有一个协议适用于 X12 协议和适用于 EDIFACT 协议的一个协议。 不能有可用于这两种协议的单个协议。  
  
-   为 X12 和 EDIFACT 消息编码协议和传输协议 （适用于 AS2) 不能为一个协议的一部分。 必须创建两个单独的协议。  
  
## <a name="global-or-fallback-agreement"></a>全局或后备协议  
 特定的业务组织可能选择 B2B 处理机制，而不区分特定 B2B 消息传递中涉及的合作伙伴的单数集。 实际上，这类业务组织具有只是一个常见 B2B 协议设置与所有其他贸易合作伙伴共享。 此外，因为此类组织不需要具有特定设置的特定合作伙伴，为贸易合作伙伴本身而不是针对贸易业务配置文件定义 B2B 协议设置。 在中[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，这样的业务部门反映为**全球贸易合作伙伴**。 需要表示为全球贸易合作伙伴业务交易其他企业使用称为全球贸易合作伙伴协议**全球贸易合作伙伴协议**。 这些协议符合为全球贸易合作伙伴定义的消息编码和协议设置。  
  
 当两个贸易合作伙伴之间的特定于配置文件的协议设置，没有制订一个贸易合作伙伴协议时，在全局级别定义的设置也可以是在方案中有用。 在此方案中，组织承载[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]可以使用为合作伙伴定义的协议设置来制订与其他贸易业务配置文件。 在这种情况下，抵达的协议使用的全球协议设置定义的名为合作伙伴**备选贸易合作伙伴协议**。  

## <a name="learn-next"></a>接下来了解

[将所有组合在一起：定义贸易合作伙伴管理解决方案](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
  
## <a name="see-also"></a>请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)