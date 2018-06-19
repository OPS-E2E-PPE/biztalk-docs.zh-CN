---
title: 使用架构 |Microsoft 文档
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
ms.openlocfilehash: 404beaeb617f7a6c0c5e3fc4ddc40126e6b97990
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963091"
---
# <a name="working-with-schemas"></a>使用架构
中提供的架构[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]是[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]XSD 表示形式的全球 Interbank 财务电信 (SWIFT) FIN 消息互联网协会。 每个消息类型都有其自己的架构，包括 SWIFT 标头和 SWIFT 预告片 （交换格式）。 此架构并有效地发送或接收 SWIFT 消息。 这些架构是分隔和位置的记录，提供详细的 XML 表示形式的平面文件 FIN 结构的唯一组合。  
  
 大多数 SWIFT 客户使用 SWIFT FIN 消息的一个相对较小子集。 若要为这些客户实现解决方案，你可以创建 BizTalk 架构项目 (如所示[模块 2： 添加新的架构项目](../../adapters-and-accelerators/accelerator-swift/module-2-adding-a-new-schemas-project.md)的 A4SWIFT 教程)。 将相关消息架构添加 (MT*xxx*.xsd) 从\\\ 程序 Files\Microsoft BizTalk Accelerator for SWIFT\<版本\>MessagePack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category x\MT xyy 目录，其中 x 是 FIN 消息类型的第一个数字，xyy 是消息的三个数字消息类型。  
  
 你可以将多个架构添加到同一个项目。 若要维护可管理性，则不应添加 20 个以上的消息架构，每个项目。 你还需要将这些基类和常见架构添加到项目。 如果你已部署的基类和常用的架构，你需要使其程序集的引用，而不是将它们部署。 本部分介绍这些架构。 消息架构已准备好使用，因为是到 SWIFT 网络发送的消息和从 SWIFT 接收的消息。  
  
 你可以检查每个 SWIFT 架构中的内容[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]使用架构编辑器。 所有消息交换架构具有以下常见结构：  
  
-   标头  
  
-   消息正文  
  
-   拖车安排  
  
 本部分介绍的标头和尾的架构。 消息文本包括 FIN 消息中的负载和包含的所有数据字段包含消息类型，发送方和接收方，字段除外。 这三个字段都包含在标头部分。 有些消息还包含一个可选的用户标头，也可提供处理信息。  
  
 每个 FIN 消息负载包含的一系列定义的序列中的字段。 这些字段符合以下规则：  
  
-   字段可能必需或可选在序列中。  
  
-   序列可能包含子序列，并且子序列可以重复序列内。  
  
-   你可以使用几种消息类型中的字段。  
  
-   在字段中，可能有元素或子字段。 元素或子字段可能是普遍适用于多个字段。  
  
-   组节点表示每个重复的序列。  
  
-   每个字段可能本身具有多个 nodal 级别，每个作为记录所述。  
  
-   架构元素表示仅最低的级别个子字段。  
  
-   常见和基架构定义通用记录和元素。  
  
-   架构表示几种格式 （如方字段） 中的某些字段。 架构定义选择字段为此类字段。  
  
-   某些字段具有有限组值。 大多数情况下，架构列出了这些值。 架构定义还包括字符集验证。  
  
 本部分包含：  
  
-   [基础架构和通用架构](../../adapters-and-accelerators/accelerator-swift/base-and-common-schemas.md)  
  
-   [SWIFT 标头和尾部架构](../../adapters-and-accelerators/accelerator-swift/swift-header-and-trailer-schemas.md)  
  
-   [SWIFT 架构命名约定](../../adapters-and-accelerators/accelerator-swift/swift-schema-naming-conventions.md)