---
title: 威胁模型分析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TMA, about TMA
- TMA
- TMA, procedure steps
ms.assetid: dfbf46aa-0a35-4925-8718-df8591efc279
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e16ae71495980e3897ab1e847600222b1c276d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399986"
---
# <a name="threat-model-analysis"></a>威胁模型分析
威胁模型分析 (TMA) 是可以帮助您确定对产品、 应用程序、 网络或环境中，带来安全风险分析和攻击可以出现。 目标是确定哪些威胁需要迁移以及如何缓解这些问题。  
  
 本部分提供有关 TMA 过程的高级信息。 有关详细信息，请参阅的第 4 章*Writing Secure Code，Second edition*，作者为 Michael Howard 和 David LeBlanc。  
  
 下面是一些 TMA 的好处：  
  
- 提供了更好地了解你的应用程序  
  
- 可帮助你发现 bug  
  
- 可帮助了解详细信息中的应用程序的新团队成员  
  
- 包含在你的应用程序上生成的其他团队的重要信息  
  
- 适用于测试人员  
  
  若要执行 TMA 的高级步骤有：  
  
- 步骤 1. 收集背景信息  
  
- 步骤 2. 创建和分析威胁模型  
  
- 步骤 3. 查看威胁  
  
- 步骤 4. 确定缓解措施  
  
- 步骤 5. 文档安全模型和部署注意事项  
  
- 步骤 6. 实现和测试缓解措施  
  
- 步骤 7. 使威胁模型与设计保持同步  
  
## <a name="step-1-collect-background-information"></a>步骤 1. 收集背景信息  
 若要准备成功 TMA，必须收集一些背景信息。 它可用于分析目标环境 （应用程序、 程序或整个基础结构），如下所示：  
  
-   确定用例场景。 每个用例方案的目标环境，识别期望在目标环境中使用目标环境中，任何限制你公司的方式。 此信息可帮助定义的作用域的威胁模型讨论，并提供对资产 （任何类型的值与你的公司，如数据和计算机） 和入口点的指针。  
  
-   创建每个方案的数据数据流关系图 (DFD)。 请确保你在转足够深入，若要了解您的威胁。  
  
-   确定边界和目标环境的范围。  
  
-   了解受信任和不受信任的组件之间的边界。  
  
-   了解每个组件的配置和管理模型。  
  
-   创建外部依赖关系的列表。  
  
-   创建一系列有关每个组件所依赖的其他组件的假设。 这有助于验证跨组件假设、 操作项和与其他团队的后续项。  
  
## <a name="step-2-create-and-analyze-the-threat-model"></a>步骤 2. 创建和分析威胁模型  
 收集背景信息后，应具有威胁模型会议。 请确保每个开发部门 （例如，项目经理、 开发人员和测试人员） 的至少一个成员是在会议上。 请确保，提醒与会者会议旨在找出威胁，不希望修复问题。 在威胁模型会议中，执行以下步骤：  
  
-   检查每个用例的 dfd:。 对于每个用例确定：  
  
    -   入口点  
  
    -   信任边界  
  
    -   将数据从入口点到最终静止的位置 （和后端） 的流  
  
-   请注意所涉及的资产。  
  
-   讨论每个 DFD 和威胁的 DFD 中的所有条目的以下类别中查找：**S**poofing 标识，请**T**篡改数据， **R**epudiation，**我**表示信息泄露**D**表示拒绝服务，并**E**表示特权提升。  
  
-   创建威胁分类列表。 我们建议，此列表包括以下： 标题、 简要说明 （包括威胁树）、 资产 （资产）、 impact(s)、 风险、 缓解措施，缓解状态和 bug 数。  
  
    > [!NOTE]
    >  查看威胁，可以添加风险、 缓解措施和缓解状态。 不占用太多时间在这些领域在威胁模型会议。  
  
## <a name="step-3-review-threats"></a>步骤 3. 查看威胁  
 确定对你的环境的威胁后，必须对每个威胁的风险并确定你想要对每个威胁做出响应。 与其他团队会议或通过电子邮件时，可以执行此操作。 可以使用以下影响类别来计算风险危害：**D**潜在，损害**R**再现， **E**xploitability，**一个**可用户并**D**iscoverability。  
  
 对你按风险设置优先级的目标环境的威胁的列表后，您必须确定将如何应对每个威胁。 您的响应可以是不执行任何操作 （很少是一个不错的选择）、 有关潜在问题的用户，则发出警告，删除该问题，或解决该问题。  
  
## <a name="step-4-identify-mitigation-techniques-and-technologies"></a>步骤 4. 确定缓解措施  
 确定将修复哪些威胁后，您必须确定每种威胁，并减少每个威胁的影响最合适的技术可缓解措施。  
  
 例如，具体取决于你的目标环境的详细信息，可以通过使用授权技术降低数据篡改威胁的影响。 您然后必须确定要使用 （如自由访问控制列表 (Dacl) 中，权限或 IP 限制） 的相应授权技术。  
  
> [!IMPORTANT]
>  当你评估缓解措施和技术来使用时，必须考虑适合业务的公司和你的公司有可能会影响要选择的缓解技术的任何策略。  
  
 完成 TMA 后，请执行以下操作：  
  
-   文档的安全模型和部署注意事项  
  
-   实现和测试的缓解措施  
  
-   保留与设计保持同步的威胁模型  
  
## <a name="step-5-document-security-model-and-deployment-considerations"></a>步骤 5. 文档安全模型和部署注意事项  
 它是有价值记录期间 TMA 发现和您决定如何降低对你的目标环境的威胁的影响。 本文档可为质量保证 (QA)、 测试、 支持和运营人员。 包含有关其他交互的应用程序或使用你的目标环境，以及防火墙和拓扑的建议和要求的接口。  
  
## <a name="step-6-implement-and-test-mitigations"></a>步骤 6. 实现和测试缓解措施  
 当你的团队已准备好修复 TMA 期间识别的威胁时，请确保使用开发和部署检查表遵循安全的代码和部署标准，可帮助最大程度减少引入了新的威胁。  
  
 实现一种缓解后，请确保测试，以确保它提供的威胁所需的保护级别。  
  
## <a name="step-7-keep-the-threat-model-in-sync-with-design"></a>步骤 7. 使威胁模型与设计保持同步  
 添加新的应用程序时，服务器和其他元素添加到你的环境，请确保你重新访问了威胁模型分析的发现结果并执行 TMAs 任何新功能。  
  
## <a name="see-also"></a>请参阅  
[对于小型到中型公司的安全性案例研究](../core/security-case-studies-for-small-to-medium-sized-companies.md)   
 [威胁模型分析的示例方案](../core/sample-scenarios-for-threat-model-analysis.md)