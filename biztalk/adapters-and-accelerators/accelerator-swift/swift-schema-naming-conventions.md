---
title: SWIFT 架构命名约定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dabd9796497bdd5b81d34f71c01124f26de203d9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987422"
---
# <a name="swift-schema-naming-conventions"></a>SWIFT 架构命名约定
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括架构用于社会用于全球 Interbank 金融电信 (SWIFT) FIN 消息使用 BizTalk 编辑器创建的。 这两个架构符合在整个的以下约定：  
  
> [!NOTE]
>  所有架构都的版本控制。 若要查看版本，请打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后右键单击解决方案资源管理器中的架构。 与\<架构\>BizTalk 编辑器中，选择在属性窗格中向下滚动到标准版本属性中的节点。  
  
- 每个交换架构文件的名称是**MT*xxx*.xsd**，其中*xxx*是 FIN 消息类型。  
  
- 为每个消息关联的主策略文件的名称是**MT*xxx*_Master_Policy.xml**，以及相应的名称在业务规则引擎 (BRE) 是**MT*xxx*_Master_Policy**，使用的列表名称**MT*xxx*_PolicyList**。  
  
- 为每个消息关联的验证策略文件的名称是**MT*xxx*_Validation_Policy.xml**，以及 BRE 中的相应名称是**MT*xxx*_Validation_Policy**。  
  
- 每个消息架构中的根名称是**SWIFT_CATEGORY*z*_MT*zxx*_Interchange**，其中*z*是消息类别 （消息类型的第一个数字） 和*zxx*是消息类型。  
  
- 每个消息架构的目标命名空间**<http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx>** <em>，其中 * z</em>是消息类别 （消息类型的第一个数字） 和*zxx*是消息类型。  
  
- 文档类型是**MT * zxx**<em>，其中 * zxx</em>是消息类型。  
  
- 不带编号的字段和子字段的名称包含描述性业务名称。 每个单词的第一个字母大写，并且名称不包括插入空格或单词间的标点符号 (例如，名称会**ServiceIdentifier**，而非**服务标识符**).  
  
- 在消息中序列的标签遵守*SWIFT 参考指南*(例如， **SequenceA**)。  
  
- 标签的字段编号 SWIFT 包括 （如果存在） 的序列后, 跟一个描述性标题后面加上数字代码和可选的字母格式 (例如， **Reference_A_20C**)。  
  
- 选择的多个字段的格式时，节点的标签是 **\<*选*\>**，，然后每个选项是带编号的字段 (例如，**日期_A_98A**并**DateTime_A_98C**)。  
  
- 最低级别的元素定义的子字段的名称包含后跟的子字段的名称**类型**(例如， **accountType**帐户)。  
  
  消息架构中的其他命名空间包括：  
  
- xmlns:xs="<http://www.w3.org/2001/XMLSchema>". 这是默认 W3C XML 架构命名空间。  
  
- xmlns:b ="<http://schemas.microsoft.com/BizTalk/2003>"。 这是默认的 BizTalk 命名空间。  
  
  每个消息架构直接引用的基类型和通用数据类型架构。  
  
## <a name="see-also"></a>请参阅  
 [处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)