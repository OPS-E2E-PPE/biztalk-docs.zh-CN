---
title: 贸易合作伙伴和业务配置文件 |Microsoft 文档
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
ms.openlocfilehash: 0fff632199d3acd8be4ade7724eaa49748dab5db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279533"
---
# <a name="trading-partners-and-business-profiles"></a>贸易合作伙伴和业务配置文件

## <a name="overview"></a>概述
业务关系中的每个参与组织均为贸易合作伙伴。 贸易合作伙伴也称为“贸易参与方”或“参与方”，位于根级别并形成贸易合作伙伴解决方案的基础。 贸易合作伙伴是正在进行的业务关系的两个或多个参与者中的一个。 贸易合作伙伴是任何单个企业实体，可以从任何其他合作伙伴接收消息或发送消息到这些合作伙伴。  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 可以用于 TPM 解决方案进行建模和存储的任何贸易合作伙伴的信息，例如发送端口关联和用于验证的参与方的标识的证书。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用此信息用于处理收到的消息和发送的消息。 每个组织参与商业关系，其中包括主组织 (运行本地主机组织[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机)，表示为贸易合作伙伴。
  
 ![贸易方](../core/media/tradingparties.gif "TradingParties")  
  
 例如，考虑两个组织： Fabrikam 和 Contoso。 使用 Fabrikam [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 若要使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 来管理全部与 Contoso 进行交换的业务数据，Fabrikam 必须创建两个贸易合作伙伴，一个自己使用，另一个供 Contoso 使用。 在创建参与方时，你提供某些详细信息，如合作伙伴名称，依次类推。  
 
## <a name="business-profiles"></a>业务配置文件

贸易合作伙伴的业务简介（也称为业务简介）是一个组织的业务方面。 在 TPM 解决方案中，与另一组织中的另一业务部分进行贸易的组织中的每个业务部门都表示为业务简介。 在其业务简介中捕获定义特定于业务部门、业务单位或业务系统的 B2B 消息传送参数的所有属性。 例如，假定 Fabrikam 具有两个业务部门:"付款"和"Shipping"。 Contoso 包含业务部门"发票"。 使用考虑 Fabrikam [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它必须创建：  
  
-   两个业务简介，一个用于贸易合作伙伴 Fabrikam 下的“付款”和“运输”。  
  
-   一个业务简介用于贸易合作伙伴 Contoso 下的“发票”。  
  
 下图演示了如何在 TPM 解决方案中管理合作伙伴和业务简介。  
  
 ![贸易合作伙伴的业务配置文件](../core/media/businessprofile.gif "BusinessProfile")  
  
 定义业务简介之后，业务部门可以定义业务部门在发送和接收 B2B 消息时遵循的消息编码格式和传输。 这些业务配置文件之间的通信模式中讨论了[协议设置](../core/protocol-settings.md)。  
  
### <a name="why-do-i-need-business-profiles"></a>为什么我需要业务简介？  
 业务简介使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用户能够在 TPM 解决方案中更好地表示其业务模型。 具有多个业务部门的企业可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中单独表示。 更重要的是，此模型使用户能够为每个业务简介设置定义业务简介如何与其他简介交易的属性。 例如，考虑一个在美国和欧洲具有部门的企业。 在美国除法需要 EDI 消息仅 X12 标准，而在欧洲除法需要 EDI 消息仅在 EDIFACT 标准。 通过创建方，企业可以设置的配置文件级别，以及在同一时间的消息属性，可以使用合作伙伴级别已设置的属性的权限。 如果业务配置文件，没有企业都不得不创建贸易合作伙伴的所有业务部门，并跨这些贸易合作伙伴复制的主机属性。  
  
 还可以将业务标识与业务简介相关联以拥有唯一标识。 这些业务标识可以由标准机构提供，也可以是相互达成协议的业务标识。  
  
> [!IMPORTANT]
>  如果同一组织内的两个业务部门需要在各自部门内进行交易，则必须将它们创建为单独的贸易合作伙伴。 同一合作伙伴下的两个简介无法彼此交易，因为仅管理明确的合作伙伴之间的贸易合作伙伴关系。  
  
## <a name="learn-next"></a>了解下一步

[协议设置](../core/protocol-settings.md)  
[贸易合作伙伴协议](../core/trading-partner-agreement.md)  
[综合： 定义一个贸易合作伙伴管理解决方案](../core/putting-it-all-together-defining-a-trading-partner-management-solution.md)
 
## <a name="see-also"></a>另请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)