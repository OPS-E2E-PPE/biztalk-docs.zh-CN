---
title: 配合使用： 定义贸易合作伙伴管理解决方案 |Microsoft Docs
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
ms.openlocfilehash: 4846df26680fa547a81c9136dfc2fd92fb95ee96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001222"
---
# <a name="putting-it-all-together-defining-a-trading-partner-management-solution"></a>配合使用： 定义贸易合作伙伴管理解决方案
既然我们已经了解了构建 TPM 解决方案所需的不同类型的组件，现在让我们再了解一下典型 TPM 解决方案流以及不同的生成块如何一起工作。 此部分还列出了一些用于对 TPM 解决方案建模的最佳做法。  
  
 用于创建 TPM 解决方案的典型流程包括以下内容：  
  
1. 创建表示业务交易中涉及的所有组织的合作伙伴。 例如，如果业务交易中涉及两个业务组织，您必须为每个业务组织创建一个贸易合作伙伴。 有关如何创建贸易合作伙伴的说明，请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md)或[配置常规参与方属性 (AS2)](../core/configuring-general-party-properties-as2.md)  
  
2. 对于组织中的每个业务部门，在代表业务部门的合作伙伴内创建一个配置文件。 例如，如果某个组织有“采购”和“供应”业务部门，则每个部门都必须表示为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的业务配置文件。 另外，您不但要为代表组织的合作伙伴创建业务配置文件，还要为您与之进行交易的合作伙伴创建业务配置文件。 有关如何创建业务配置文件的说明，请参阅[配置业务配置文件属性](../core/configuring-business-profile-properties.md)。  
  
3. 对于每个业务配置文件，定义包含消息编码设置和消息协议设置的 B2B 协议设置。 这些设置定义如何对 B2B 消息进行编码以及如何在两个业务配置文件之间传输 B2B 消息。  
  
   > [!NOTE]
   >  指定协议设置在此阶段是可选的。 您可以直接将协议设置添加为贸易合作伙伴协议的一部分。  
  
4. 在定义编码的业务配置文件和/或两个业务配置文件同意在交换消息时使用的消息传递协议之间创建贸易合作伙伴协议 (TPA)。 有关如何创建协议的说明，请参阅[配置特定于 X12 的协议属性](../core/configuring-x12-specific-agreement-properties.md)，[配置特定于 EDIFACT 的协议属性](../core/configuring-edifact-specific-agreement-properties.md)，或[配置 AS2协议属性](../core/configuring-as2-agreement-properties.md)。  
  
   通过执行上述的任务，您已经创建 TPM 解决方案以与您的贸易合作伙伴交换 B2B 消息。  
  
## <a name="where-do-i-start"></a>如何开始？  
 您可以通过浏览以下部分开始：  
  
-   在特定于 X12 的教程[教程 2: EDI 接口开发人员教程](../core/tutorial-2-edi-interface-developer-tutorial.md)。  
  
-   在特定于 AS2 的教程[教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)。  
  
-   X12-和 EDIFACT-在特定演练[开发和配置 BizTalk Server EDI 解决方案](../core/developing-and-configuring-biztalk-server-edi-solutions.md)。  
  
-   在特定于 AS2 的演练[开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)。  
  
-   创建参与方、 配置文件和协议用于 X12 和 EDIFACT 消息传送在按照的说明[配置 EDI 属性](../core/configuring-edi-properties.md)。  
  
-   创建参与方、 配置文件，以及按说明操作，在消息传送 as2 协议[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [贸易合作伙伴管理解决方案的构建基块](../core/building-blocks-of-a-trading-partner-management-solution.md)