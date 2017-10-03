---
title: "命名约定的 SWIFT 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- naming conventions [schemas]
- schemas, naming conventions
ms.assetid: 3c1f2519-2575-4178-89c1-e97333c1e6bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb792fe66e5806a186b0ffb946aa99f86a6a10c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-schema-naming-conventions"></a>SWIFT 架构的命名约定
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]包括用于互联网协会用于使用 BizTalk 编辑器创建的全球 Interbank 财务电信 (SWIFT) FIN 消息的架构。 这些架构符合在整个以下约定：  
  
> [!NOTE]
>  所有架构都是版本控制的。 若要查看版本，请打开[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后右键单击解决方案资源管理器中的架构。 与\<架构 > BizTalk 编辑器中，选定属性窗格中向下滚动到标准版本属性中的节点。  
  
-   每个交换架构文件的名称是 **MT*xxx*.xsd * *，其中*xxx*是 FIN 消息类型。  
  
-   为每个消息关联的主策略文件的名称是 **MT*xxx*_Master_Policy.xml**，并且相应的名称在业务规则引擎 (BRE) 为 **MT*xxx*_Master_Policy**，列表名称为 **MT*xxx*_PolicyList * *。  
  
-   为每个消息关联的验证策略文件的名称是 **MT*xxx*_Validation_Policy.xml**，BRE 中的相应名称和 **MT*xxx*_Validation_Policy**。  
  
-   在每个消息架构，根的名称是 **SWIFT_CATEGORY*z*_MT*zxx*_Interchange * *，其中*z*消息类别（消息类型的第一个数字） 和*zxx*是消息类型。  
  
-   每个消息架构的目标命名空间是 **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category*z*/MT*zxx** *，其中*z*消息类别 （第一个数字的消息类型） 和*zxx*是消息类型。  
  
-   文档类型是 **MT*zxx** *，其中*zxx*是消息类型。  
  
-   不带编号的字段和子字段的名称包含描述性业务名称。 每个单词的第一个字母大写，并且名称不包括干预空格或单词之间的标点符号 (例如，则名称将为**ServiceIdentifier**，而不**服务标识符**).  
  
-   在消息的序列的标签符合*SWIFT 参考指南*(例如， **SequenceA**)。  
  
-   标签编号 SWIFT 字段包括序列中 （如果存在） 后, 跟一个描述性标题跟的数字代码和可选字母格式 (例如， **Reference_A_20C**)。  
  
-   选择的多个字段的格式，节点的标签是  **\<*选择*> * *，，然后每个选项的已编号的字段 (例如， **Date_A_98A**和**DateTime_A_98C**)。  
  
-   最低级别的元素定义的子字段的名称包含跟子字段的名称**类型**(例如， **accountType**帐户)。  
  
 其他命名空间中的消息架构如下所示：  
  
-   xmlns:xs ="http://www.w3.org/2001/XMLSchema"。 这是默认 W3C XML 架构命名空间。  
  
-   xmlns:b ="http://schemas.microsoft.com/BizTalk/2003"。 这是默认 BizTalk 命名空间。  
  
 每个消息架构直接引用的基类型和通用数据类型的架构。  
  
## <a name="see-also"></a>另请参阅  
 [使用架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)