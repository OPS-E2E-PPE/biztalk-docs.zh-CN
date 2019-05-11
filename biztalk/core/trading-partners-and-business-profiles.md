---
title: 贸易合作伙伴和业务配置文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbeac421-c319-4a60-a188-28f7268888fc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 194388ddbd4fe2b39987e11a45e4bf87d71dfcff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313361"
---
# <a name="trading-partners-and-business-profiles"></a>贸易合作伙伴和业务配置文件

## <a name="overview"></a>概述
业务关系中的每个参与组织均为贸易合作伙伴。 贸易合作伙伴，也称为"贸易参与方"或"参与方"，在根级别并形成贸易合作伙伴解决方案的基础。 贸易合作伙伴是一个正在进行的业务关系中两个或多个参与者。 贸易合作伙伴是任何单个企业实体，可以发送或接收到或从其他合作伙伴的消息。  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以使用 TPM 解决方案进行建模和存储任何贸易合作伙伴的信息，如发送端口关联和使用证书来验证参与方的标识。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用此信息来处理接收的消息和发送的消息。 每个组织参与业务关系，包括本组织 (运行的本地主机组织[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机)，表示为贸易合作伙伴。
  
 ![贸易参与方](../core/media/tradingparties.gif "TradingParties")  
  
 例如，考虑两个组织：Fabrikam 和 Contoso。 使用 Fabrikam [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 若要使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]对于管理所有业务数据交换与 Contoso，Fabrikam 必须创建两个贸易合作伙伴，一个用于本身，一个供 Contoso。 在创建参与方时，提供某些详细信息，如合作伙伴名称，等等。  
 
## <a name="business-profiles"></a>业务配置文件

贸易合作伙伴的业务配置文件，也称为业务配置文件，是组织的业务方面。 使用另一组织中的另一个业务部门进行贸易的组织中每个业务部门表示为 TPM 解决方案中的业务配置文件。 在其业务配置文件中捕获到业务部门、 业务部门或业务系统中定义特定的 B2B 消息传递参数的所有属性。 例如，假定 Fabrikam 具有两个业务部门："付款"和"发货"。 Contoso 有一个业务部门"发票"。 考虑 Fabrikam 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，必须创建：  
  
- 两个业务配置文件，分别用于支付和配送，在贸易合作伙伴 Fabrikam。  
  
- 一个业务配置文件的发票贸易合作伙伴 Contoso 下。  
  
  下图说明了如何在 TPM 解决方案中管理合作伙伴和业务配置文件：  
  
  ![贸易合作伙伴的业务配置文件](../core/media/businessprofile.gif "BusinessProfile")  
  
  定义业务配置文件之后, 的业务部门可以定义消息编码格式和传输的业务部门时发送和接收 B2B 消息遵循。 这些业务配置文件之间的通信模式中讨论[协议设置](../core/protocol-settings.md)。  
  
### <a name="why-do-i-need-business-profiles"></a>为什么需要业务配置文件？  
 业务配置文件启用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用户以更好地表示其业务模型在 TPM 解决方案中的。 可以单独在表示多个业务部门与企业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 更重要的是，此模型使用户能够设置为每个业务配置文件的属性，用于定义业务配置文件与其他配置文件的处理方式。 例如，考虑具有在美国和欧洲的部门的企业。 在美国的部门预计 EDI 消息仅采用 X12 标准，而欧洲的部门预计 EDI 消息仅采用 EDIFACT 标准。 通过创建聚会，企业可以设置的正确的消息传送属性在配置文件级别，而是在相同时使用已在合作伙伴级设置的属性。 如果没有业务配置文件，企业将必须创建贸易合作伙伴为所有业务部门，然后跨这些贸易合作伙伴复制属性的主机。  
  
 此外可以将业务标识与业务配置文件，以拥有唯一标识相关联。 这些业务标识可以由标准机构提供，也可以是相互达成协议业务标识。  
  
> [!IMPORTANT]
>  如果同一组织中的两个业务部门需要本身内进行交易，则必须创建它为单独的贸易合作伙伴。 同一合作伙伴下的两个配置文件不能作为贸易合作伙伴关系管理明确的合作伙伴之间彼此通讯。  
  
## <a name="learn-next"></a>接下来了解

[协议设置](../core/protocol-settings.md)  
[贸易合作伙伴协议](../core/trading-partner-agreement.md)  
[配合使用：定义贸易合作伙伴管理解决方案](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
 
## <a name="see-also"></a>请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)