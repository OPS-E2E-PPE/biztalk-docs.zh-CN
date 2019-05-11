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
ms.openlocfilehash: f313ba2063e2184b4c0fe755c32bc0cbf07e0409
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323546"
---
# <a name="namespace-management"></a>Namespace 管理
BizTalk 编辑器为命名空间提供支持。 XML 命名空间是可以用作 XML 消息中的元素或属性名称的名称的集合。 命名空间限定元素和属性名，以避免同一元素和属性名称可能相同架构中其他位置定义之间的冲突。  
  
 命名空间进行标识的通用资源标识符 (URI)，作为统一资源定位器 (URL) 或统一资源名称 (URN)。 系统会提供较短的前缀别名，该别名预置了分隔冒号 （:） 中的元素或属性名称本身。 例如，它是经常可以看到以下命名空间声明内的**架构**架构的 XSD 表示形式中的元素。  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 前缀为 xs，您看到在整个 XSD 表示形式符合条件的此类元素作为**元素**元素 (xs: element) 和**属性**元素 (xs:attribute)。  
  
 当首次创建新的架构，而不考虑它是消息架构还是属性架构，务必要设置**目标 Namespace**的属性**架构**节点正确。 你需要之前导入/包括/重新定义机制，则由另一个架构使用的架构和任何属性升级定义建立目标命名空间。  
  
> [!WARNING]
>  如果要使用仅大小写的两个命名空间，BizTalk 数据库必须安装使用区分大小写的排序规则。 区分大小写的排序规则的示例包括与启用了区分大小写的二进制和非二进制排序规则。 如果不执行此操作，架构解析将失败，因为 XML 区分大小写。  
  
 以下两个命名空间将自动添加到架构的 XML 架构定义 (XSD) 语言表示形式中 schema 元素的命名空间声明为：  
  
- xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>"  
  
- xmlns:xs="<http://www.w3.org/2001/XMLSchema>"  
  
  在过程中使用其他架构中创建的架构，将声明其他命名空间。 您可以检查这些命名空间，以及自动包括的命名空间中**导入**对话框，可以使用访问**导入**属性**架构**节点。 要创建使用其他架构中的其他架构中声明的数据类型有关的详细信息，请参阅[，使用其他架构](../core/schemas-that-use-other-schemas.md)并[创建使用其他架构的](../core/how-to-create-schemas-that-use-other-schemas.md)。  
  
  在中，可以检查与属性架构相关联的命名空间**升级属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [创建架构时的注意事项](../core/considerations-when-creating-schemas.md)