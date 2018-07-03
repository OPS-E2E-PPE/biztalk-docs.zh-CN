---
title: Namespace 管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4638c47c-3cdd-43af-aa00-da98e7293503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa476034a578be24bf388c87f38f910565cd2548
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022467"
---
# <a name="namespace-management"></a>命名空间管理
BizTalk 编辑器支持命名空间。 XML 命名空间是可以在 XML 消息中用作元素或属性名称的名称集合。 命名空间对元素和属性名称进行限定，以避免可能在相同架构中其他位置定义的相同元素和属性名称之间存在冲突。  
  
 命名空间由统一资源定位符 (URI) 标识为统一资源定位符 (URL) 或统一资源名称 (URN)。 还为它们提供了较短的前缀别名，该别名预置了分隔冒号 (:)，以分隔元素或属性名称本身。 例如，它是经常可以看到以下命名空间声明内的**架构**架构的 XSD 表示形式中的元素。  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 前缀为 xs，您看到在整个 XSD 表示形式符合条件的此类元素作为**元素**元素 (xs: element) 和**属性**元素 (xs:attribute)。  
  
 当首次创建新的架构，而不考虑它是消息架构还是属性架构，务必要设置**目标 Namespace**的属性**架构**节点正确。 在其他架构使用导入/包括/重新定义机制使用该架构之前以及定义任何属性升级之前，您需要建立目标命名空间。  
  
> [!WARNING]
>  如果要使用仅大小写的两个命名空间，BizTalk 数据库必须安装使用区分大小写的排序规则。 例如，区分大小写的排序规则包括启用了区分大小写功能的二进制和非二进制排序规则。 如果不这样，则架构解析将由于 XML 区分大小写而失败。  
  
 以下两个命名空间作为命名空间声明自动添加到架构的 XML 架构定义 (XSD) 语言表示形式中的 schema 元素：  
  
- xmlns:b ="<http://schemas.microsoft.com/BizTalk/2003>"  
  
- xmlns:xs ="<http://www.w3.org/2001/XMLSchema>"  
  
  在正创建的架构中使用其他架构的过程中，将会声明其他命名空间。 您可以检查这些命名空间，以及自动包括的命名空间中**导入**对话框，可以使用访问**导入**属性**架构**节点。 要创建使用其他架构中的其他架构中声明的数据类型有关的详细信息，请参阅[，使用其他架构](../core/schemas-that-use-other-schemas.md)并[创建使用其他架构的](../core/how-to-create-schemas-that-use-other-schemas.md)。  
  
  在中，可以检查与属性架构相关联的命名空间**升级属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [创建架构时的注意事项](../core/considerations-when-creating-schemas.md)