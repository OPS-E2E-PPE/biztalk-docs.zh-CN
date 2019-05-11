---
title: 配合使用：定义贸易合作伙伴管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4219312a-c4b5-45f3-b77b-d5cc4f1a1ca4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b56ba4f5bf6918f9a2499135c25ad7526a90c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398338"
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a>配合使用：定义贸易合作伙伴管理解决方案
现在，我们已经了解不同类型的构建 TPM 解决方案中的组件，让我们了解一下典型 TPM 解决方案和其他构建基块如何协同工作的流。 本部分还列出了对 TPM 解决方案建模一些最佳的做法。  
  
 用于创建 TPM 解决方案的典型流包括以下：  
  
1. 创建合作伙伴，用于表示参与商业贸易的的所有组织。 例如，如果有业务交易中涉及的两个业务组织，您必须创建为每个贸易合作伙伴。 有关如何创建贸易合作伙伴的说明，请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md)或[配置常规参与方属性 (AS2)](../core/configuring-general-party-properties-as2.md)  
  
2. 对于组织中每个业务部门，创建代表业务部门的合作伙伴内的配置文件。 例如，如果组织有"购买"和"供应"业务部门，每个部门必须表示为业务配置文件中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此外，您必须不只是为表示你的组织，但也与之进行交易的合作伙伴的合作伙伴创建业务配置文件。 有关如何创建业务配置文件的说明，请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。  
  
3. 对于每个业务配置文件中，定义包含消息编码设置和消息协议设置的 B2B 协议设置。 这些设置定义如何编码和两个业务配置文件之间传输 B2B 消息。  
  
   > [!NOTE]
   >  指定协议设置在此阶段是可选。 作为贸易合作伙伴协议的一部分，可以直接添加协议设置。  
  
4. 定义两个业务配置文件都同意交换消息时使用的编码和/或消息传送协议的业务配置文件之间创建贸易合作伙伴协议 (TPA)。 有关如何创建协议的说明，请参阅[配置特定于 X12 的协议属性](../core/configuring-x12-specific-agreement-properties.md)，[配置特定于 EDIFACT 的协议属性](../core/configuring-edifact-specific-agreement-properties.md)，或[配置 AS2协议属性](../core/configuring-as2-agreement-properties.md)。  
  
   通过执行上述任务应已创建 TPM 解决方案以与您的贸易合作伙伴交换 B2B 消息。  
  
## <a name="where-do-i-start"></a>如何开始？  
 您可以首先通过以下各节：  
  
-   在特定于 X12 的教程[教程 2:EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)。  
  
-   在特定于 AS2 教程[教程 3:AS2 教程](../core/tutorial-3-as2-tutorial.md)。  
  
-   X12-和 EDIFACT-在特定演练[开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)。  
  
-   在特定于 AS2 的演练[开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)。  
  
-   创建参与方、 配置文件和协议用于 X12 和 EDIFACT 消息传送在按照的说明[配置 EDI 属性](../core/configuring-edi-properties.md)。  
  
-   创建参与方、 配置文件，以及按说明操作，在消息传送 as2 协议[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)