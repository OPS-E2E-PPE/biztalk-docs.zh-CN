---
title: 使用架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, schemas
- schemas, developing
ms.assetid: 123c4b43-34e4-41c7-980d-5d518b1479c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb6ac17cd0959d712da290b937a961d517f320e7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968358"
---
# <a name="working-with-schemas"></a>使用架构
在 Microsoft 提供的架构[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]是全球范围内 Interbank 金融电信 (SWIFT) FIN 消息协会的 Microsoft XSD 表示形式。 每个消息类型都有其自己的架构，包括 SWIFT 标头和 SWIFT 尾部 （交换格式）。 此架构就足以发送或接收 SWIFT 消息。 这些架构包括分隔和位置记录，提供详细的 XML 表示形式的平面文件 FIN 结构的唯一组合。  

 SWIFT 的大多数客户使用相对较小的 SWIFT FIN 消息子集。 若要为这些客户实现解决方案，可以创建 BizTalk 架构项目 (如中所示[模块 2： 添加新架构项目](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)A4SWIFT 教程的)。 添加相关的消息架构 (MT*xxx*.xsd) 从\\\ Program Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>MessagePack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category x\MT xyy 目录，其中 x 是 FIN 消息类型的第一个数字，xyy 是消息的三位消息类型。  

 可以将多个架构添加到同一个项目。 若要维护的可管理性，不应将添加每个项目超过 20 个消息架构。 此外需要向项目添加基类和常见架构。 如果你已部署的基类和常见的架构，您需要使其程序集的引用，而不是将其部署。 本部分介绍这些架构。 消息架构已准备好用，因为是到 SWIFT 网络发送的消息和从 SWIFT 接收的消息。  

 您可以检查在 Microsoft 中每个 SWIFT 架构的内容[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]使用架构编辑器。 所有消息交换架构具有以下常见的结构：  

- 标头  

- 消息正文  

- 尾部  

  本部分介绍的标头和尾部架构。 消息文本包含 FIN 消息的负载，并包含所有除包含发件人、 收件人和消息类型的字段的数据字段。 这三个字段都包含在标头部分。 有些消息还包含一个可选的用户标头，还可以提供处理信息。  

  每个 FIN 消息有效负载包含一系列定义序列中的字段。 这些字段符合以下规则：  

- 字段是必需或可选序列中。  

- 序列可能包含子序列，并在序列内重复子序列可能。  

- 可以使用几种消息类型中的字段。  

- 在字段中可能有元素或子字段。 元素或子字段可能是普遍适用于多个字段。  

- 组节点表示每个重复的序列。  

- 每个字段可能本身具有多个 nodal 级别，每个描述为一条记录。  

- 架构元素表示只能最低的级别子字段。  

- 常见和基本架构定义通用记录和元素。  

- 架构表示几种格式 （如参与方字段） 中的某些字段。 架构将定义此类字段作为所选的字段。  

- 某些字段具有有限的值集。 大多数情况下，该架构还列出了这些值。 架构定义还包括字符集验证。  

  本部分包含：  

- [基础架构和通用架构](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  

- [SWIFT 标头和尾部架构](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  

- [SWIFT 架构命名约定](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)
