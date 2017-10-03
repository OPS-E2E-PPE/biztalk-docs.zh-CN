---
title: "威胁模型分析 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TMA, about TMA
- TMA
- TMA, procedure steps
ms.assetid: dfbf46aa-0a35-4925-8718-df8591efc279
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06f5de73434d2c3a7bf67e659c6566b530b38aeb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="threat-model-analysis"></a>威胁模型分析
威胁模型分析 (TMA) 进行分析可帮助确定到产品、 应用程序、 网络或环境中，所带来安全风险和攻击的显示方式。 目标是确定哪些威胁需要缓解以及如何缓解的方式。  
  
 本部分提供有关 TMA 过程的高级信息。 有关详细信息，请参阅的第 4 章*编写安全代码，第二版*、 Michael Howard 和 David LeBlanc 编著。  
  
 下面是一些 TMA 的好处：  
  
-   提供更好地了解你的应用程序  
  
-   可帮助你找到 bug  
  
-   可帮助了解详细信息中的应用程序的新团队成员  
  
-   包含在你的应用程序生成其他团队的重要信息  
  
-   用于测试人员  
  
 若要执行 TMA 的高级步骤有：  
  
-   步骤 1. 收集的背景信息  
  
-   步骤 2. 创建和分析的威胁模型  
  
-   步骤 3. 查看威胁  
  
-   步骤 4. 标识缓解技术和技术  
  
-   步骤 5. 文档安全模型和部署注意事项  
  
-   步骤 6. 实现和测试缓解措施  
  
-   步骤 7. 使威胁模型设计与同步  
  
## <a name="step-1-collect-background-information"></a>步骤 1. 收集的背景信息  
 要准备成功 TMA，您需要收集一些背景信息。 它可用于分析你的目标环境 （应用程序、 程序或整个基础结构），如下所示：  
  
-   标识用例方案。 有关你的目标环境每个用例方案，标识期望你的公司在目标环境上使用目标环境中，任何限制如何。 此信息可帮助定义的讨论范围之内威胁模型，并提供对资产 （任何类型的值与你的公司，比如数据和计算机） 和入口点的指针。  
  
-   创建每个方案的数据流关系图 (DFD)。 请确保你在转足够深而无法了解你的威胁。  
  
-   确定边界和目标环境的范围。  
  
-   了解受信任和不受信任的组件之间的边界。  
  
-   了解每个组件的配置和管理模型。  
  
-   创建外部依赖项的列表。  
  
-   创建假设每个组件所依赖的其他组件的列表。 这有助于验证跨组件假设、 操作项目和与其他团队的后续项。  
  
## <a name="step-2-create-and-analyze-the-threat-model"></a>步骤 2. 创建和分析的威胁模型  
 收集的背景信息后，你应具有威胁模型会议。 请确保每个开发专业 （例如，项目经理、 开发人员和测试人员） 该至少一个成员位于会议。 请确保，提醒与会者会议的目标是要查找的威胁，不来修复它们。 在威胁模型会议中，执行以下操作：  
  
-   检查每个用例 DFD。 对于每个用例确定：  
  
    -   入口点  
  
    -   信任边界  
  
    -   从入口点到最终的放置位置 （和后端） 的数据的流  
  
-   请注意所涉及的资产。  
  
-   讨论每个 DFD，并查找以下类别 DFD 中的所有条目中是否有威胁： **S**哄骗标识， **T**篡改数据， **R**epudiation， **我**璝泄露**D**的服务，用以和**E**提升的权限。  
  
-   创建标识的威胁的列表。 我们建议，此列表包括以下： 标题、 （包括威胁树） 的简要说明、 资产 （资产）、 impact(s)、 风险、 缓解技术、 缓解状态和大量 bug。  
  
    > [!NOTE]
    >  查看威胁，可以添加风险、 缓解技术和缓解状态。 不占用太多时间这些区域中在威胁模型会议过程。  
  
## <a name="step-3-review-threats"></a>步骤 3. 查看威胁  
 确定威胁到你的环境后，你必须排名每种威胁的风险，并确定你想要对每种威胁做出响应。 与其他团队会议或通过电子邮件时，可以执行此操作。 您可以使用以下的效果类别来计算风险暴露程度： **D**amage 潜在， **R**eproducibility， **E**xploitability， ffected 用户和**D**iscoverability。  
  
 对你按风险设置优先级的目标环境的威胁的列表后，你必须确定将如何响应每种威胁。 您的响应可以是不执行任何操作 （极少数情况下是一个不错的选择）、 用户有关的潜在问题，则发出警告，删除此问题，或解决此问题。  
  
## <a name="step-4-identify-mitigation-techniques-and-technologies"></a>步骤 4. 标识缓解技术和技术  
 确定哪些威胁将修复后，你必须确定用于每种威胁，并最适合的技术降低的每种威胁的影响的可用缓解技术。  
  
 例如，具体取决于你的目标环境的详细信息，可以通过使用授权技术来减少数据篡改威胁的效果。 然后，你需要确定适当的授权技术来使用 （针对示例、 自定义访问控制列表 (Dacl)、 权限或 IP 限制）。  
  
> [!IMPORTANT]
>  缓解技术和技术以使用计算时，你必须考虑什么合理业务的公司和你的公司有可能会影响缓解技术，若要选择的任何策略。  
  
 完成 TMA 后，请执行以下操作：  
  
-   文档的安全模型和部署注意事项  
  
-   实现和测试的缓解措施  
  
-   保留与设计保持同步的威胁模型  
  
## <a name="step-5-document-security-model-and-deployment-considerations"></a>步骤 5. 文档安全模型和部署注意事项  
 很有价值文档期间 TMA 发现和您决定如何减少对你的目标环境的威胁的效果。 本文档可以是对质量保证 (QA)、 测试、 支持和操作人员有用的。 包含有关其他应用程序进行交互或与你的目标环境，以及防火墙和拓扑的建议和要求的接口。  
  
## <a name="step-6-implement-and-test-mitigations"></a>步骤 6. 实现和测试缓解措施  
 时你的团队已准备好修复过程 TMA 中标识的威胁，请确保使用开发和部署清单来遵循安全代码和部署标准，将帮助最大程度减少引入新的威胁。  
  
 实现一种缓解措施后，请确保测试它以确保它提供的威胁所需的保护级别。  
  
## <a name="step-7-keep-the-threat-model-in-sync-with-design"></a>步骤 7. 使威胁模型设计与同步  
 当添加新的应用程序时，服务器和其他元素添加到你的环境，请确保你重新访问的威胁模型分析结果，并执行的任何新功能的 TMAs。  
  
## <a name="see-also"></a>另请参阅  
[对于小型到中型公司的安全案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)