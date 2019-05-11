---
title: 规划你的解决方案 |Microsoft Docs
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
ms.openlocfilehash: b560623a2a34d4c65511077c7434dd9aebfe1cce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290018"
---
# <a name="planning-for-your-solution"></a>规划你的解决方案
本部分提供有关您的 Microsoft 在规划时应考虑的信息[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]解决方案。  
  
 可以按以下方式实现 BTAHL7:  
  
- **初始项目**。 这种情况下是 BTAHL7 的全新安装。  
  
- **迁移项目**。 医疗保健组织逐步淘汰现有集成代理时发生这种情况。 组织将迁移到 BTAHL7。  
  
- **共存**。 此方案涉及使用另一个集成引擎的 BTAHL7 并行安装。  
  
- **嵌入**。 此方案涉及到将 BTAHL7 集成业务线应用程序中。 BTAHL7 用于 HL7 消息传送功能添加到该应用程序。  
  
  人们往往会低估的时间比第一个位置中创建它们所需的工作，管理应用程序所需的工作量。 查看需要执行的复杂数组的数据处理和管理任务的大型分布式的机构时，也是如此。 医院或集成了运行状况的供应商是此类机构的极好示例。 此类机构面临着需要提供支持大量的函数，使信息传递到应用程序以避免重复和故障数据输入，若要为用户和维护的人员提供培训的应用程序中的软件软件，并提供替换为已过时或已过时的应用程序通过提升的。 此替换过程具有其自己测试和教育版的要求。  
  
  它就不可能 （成本过高） 来管理所有其功能与单个此类机构集成应用程序。 首先，机构不会想要将绑定到一家供应商，他们都和将找不到一家供应商通过所需的所有函数。 在第二个位置，简单的操作需求的系统化处理还使机构能够满足单个集成的应用程序使用不可能。 因此，机构将支持用户使用多个应用程序的需要。 为了使这些应用程序进行互操作，应用程序需要交换信息的接口。 应用程序和所涉及的接口的数量通常是很大。 给定此分布式应用程序体系结构，此接口引擎是随着时间的推移管理机构数据处理密钥检测。 关键问题是迁移、 映射和教育版。 BTAHL7 的任务是使解决这些问题最简单且尽可能高效：  
  
- **映射**。 接口实现中的最大作业创建应用程序/数据库结构和在界面中使用的数据结构之间的映射。 该工具执行的操作以将此项简单而自然的任何内容是很好。 此外，因为映射文档将成为界面和应用程序开发人员使用的规范，务必要能够轻松地生成它的文档。 使用 BTAHL7 配置资源管理器，Microsoft[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和 BizTalk Server 工具来设计和实施这些映射。  
  
- **迁移**。 在应用程序更改，必须随着时间的推移维护应用程序的互操作性。 如果您考虑与替换为单个应用程序相关的问题，需要是更新数据源映射到适用的接口。 与接口引擎应该有其中一种。 应考虑其中已安装接口和接口标准如果随时间而变化。 您会发现，随着时间的推移接口标准更改，需要迁移到流行的标准。 建议，迁移计划考虑将来的接口的任何更改。 需要映射之间的标准，以及标准的不同版本之间。 此外，单个标准范围内，尤其是灵活一个如 HL7 V2 — 您必须处理 （跨许多应用程序） 的同一个标准的多个实现。 接口引擎应处理的这种复杂性的方式很容易管理。  
  
   密钥的迁移任务是从一个标准的接口的正文迁移到另一个。 此处的任务是迁移使用旧到新版本的所有映射 — 拍摄帐户接口特定的本地化和扩展中，可以是一个复杂的过程。 该工具应提供此迁移的帮助。  
  
   使用 BTAHL7 配置资源管理器验证选项卡来指定所有其他消息类型的架构的命名空间。  
  
- **教育**。 与管理和支持应用程序所涉及的人员会随时间变化。 此外，由于接口是应用程序的集合的互操作性功能的核心，其文档将会提供密钥管理在整个企业中的工具。 对于这两个以上原因，很有价值，以提供易于使用，且易于维护文档） 的接口规范、 b） 的应用程序和 introversion 映射和自定义和本地化活动 c） 的基本原理。  
  
## <a name="see-also"></a>请参阅  
[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)