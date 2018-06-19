---
title: 规划你的解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Greenfield project
- security, BTAHL7
- BTAHL7, security
- installing, planning
- installing, installation types
- HL7, security
- security, HL7
- Embedded installation
- Migration project
- Coexistence installation
ms.assetid: a108c6d0-dd51-4bf9-85a0-103f60fae971
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e9a38517d7d548d458fa51fe87de5b9bf4faa5e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005742"
---
# <a name="planning-for-your-solution"></a>规划你的解决方案
本部分提供有关规划时应考虑的内容的信息你[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]解决方案。  
  
 你可以通过以下方式实现 BTAHL7:  
  
-   **未项目**。 这种情况下是 BTAHL7 的全新安装。  
  
-   **迁移项目**。 卫生保健组织逐步现有的集成 broker 时发生这种情况。 组织将迁移到 BTAHL7。  
  
-   **共存**。 此方案涉及使用另一个集成引擎的 BTAHL7 并行安装。  
  
-   **嵌入**。 此方案涉及到将 BTAHL7 集成业务线应用程序中。 你使用 BTAHL7 将 HL7 消息传送功能添加到该应用程序。  
  
 人们往往会低估的随时间相比所需首先创建它们的工作管理应用程序所需的工作量。 查看需要执行的复杂数组的数据处理和管理任务的在大型分布式的机构时，也是如此。 医院或集成的运行状况的供应商是此类机构的极好示例。 此类机构面临着需要提供软件，以支持大量的函数，以便可以将信息传递到应用程序以避免对重复和故障数据输入，若要为用户和维护人员提供培训需求的应用程序从软件，并提供以替换已过时或过时的应用程序通过改进的。 此替换过程具有其自己的要求为测试和教育机构。  
  
 将不可能 （成本过高） 为此类机构来管理所有其功能与单个集成应用程序。 首先，这些机构不会想要将其财富于单一供应商，并不会查找他们需要通过单一供应商的所有函数。 第二个就地制度处理简单操作需求导致的机构为满意单个集成的应用程序。 因此，机构将支持多个应用程序使用其需求。 为了使这些应用程序进行互操作，该应用程序需要交换信息的接口。 应用程序和涉及的接口的数量通常是很大的。 给定此分布式应用程序体系结构，接口引擎是用于随着时间的推移管理机构数据处理密钥检测。 关键问题是迁移、 映射和教育版。 BTAHL7 作业是使寻址容易也很有效尽可能作为这些问题：  
  
-   **映射**。 接口的实现中的最大作业创建应用程序/数据库结构和在界面中使用的数据结构之间的映射。 若要简化此简单而自然该工具将执行的任何内容是好的。 此外，由于映射文档将成为由接口和应用程序开发人员使用的规范，很重要，若要能够轻松地生成它的文档。 使用 BTAHL7 配置的资源管理器， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和 BizTalk Server 工具设计和实施这些映射。  
  
-   **迁移**。 随着应用程序的变化，你必须随着时间的推移维护应用程序互操作性。 如果你考虑与替换单个应用程序相关的问题，需要是更新数据源映射到适用的接口。 使用接口引擎应有其中一种。 你应考虑其中已安装接口，如果接口标准随时间而变化。 你会发现随着时间的推移接口标准只有更改，并且需要迁移到最流行的标准。 建议，你的迁移计划考虑将来的接口的任何更改。 你需要将标准，之间和标准的不同版本之间映射。 此外，范围内的单个标准-尤其是灵活一个如 HL7 V2 — 你必须处理的 （在许多应用程序） 的同一个标准的多个实现。 接口引擎应该处理这种复杂性的方式很容易管理。  
  
     密钥的迁移任务是从一个标准的接口的正文迁移到另一个。 此处的任务是迁移使用旧到新版本的所有映射 — 拍摄中帐户接口特定本地化和扩展，它可以是一个复杂的过程。 该工具应提供这种迁移的帮助。  
  
     使用 BTAHL7 配置资源管理器验证选项卡来指定的任何其他消息类型的架构命名空间。  
  
-   **教育**。 与管理和支持应用程序所涉及的人员将随时间变化。 此外，由于接口是中心的互操作性功能的应用程序的集合，其文档将会出现密钥管理在整个企业中的工具。 出于这两个这些原因，很有价值提供易于使用，并且易于维护文档） 的接口规范、 b） 的应用程序和 introversion 映射，，和自定义和本地化活动 c） 的基本原理。  
  
## <a name="see-also"></a>另请参阅  
[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)