---
title: "使用事实数据资源管理器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Facts Explorer
- business rules, vocabularies
- business rules, schemas
- business rules, databases
- business rules, .NET classes
- Facts Explorer [Business Rule Composer]
ms.assetid: ee125eb1-d5b9-4121-8a25-fcb7a640570e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4c84b01625bb1566d02c1679bfadd0100b7b406
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-facts-explorer"></a>使用事实数据资源管理器
事实数据资源管理器包含四个选项卡：**词汇**， **XML 架构**，**数据库**，和**.NET 类**。  
  
## <a name="vocabularies-tab"></a>“词汇”选项卡  
 使用**词汇**事实数据资源管理器来管理词汇版本和定义中的选项卡。  
  
 使用快捷菜单可访问以下选项：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**添加新的词汇**|创建新的词汇。|  
|**添加新的版本**|新建所选词汇的空版本。 可以从其他版本复制定义并将它们粘贴到新版本中。|  
|**粘贴词汇版本**|将以前复制的词汇版本的内容作为所选词汇的新版本粘贴。|  
|**删除**|删除所选词汇及其所有版本。|  
|**添加新的定义**|启动词汇定义向导，在所选词汇版本中创建新定义。|  
|**保存**|保存对所选版本及其定义所做的更改。|  
|**发布**|发布所选词汇版本。 请注意，不能直接修改已发布的版本。 可以将其复制并粘贴到新的词汇版本中。|  
|**重新加载**|重新加载所选词汇版本及其定义，可以选择放弃当前对该版本所做的全部更改和从规则存储恢复内容。|  
|**修改**|启动词汇定义向导以更改所选定义。 请注意，不能修改已发布词汇版本的定义。|  
|**转至源事实**|对于所选定义，转至 .NET 程序集、XML 架构或数据库表中的对应源事实。|  
  
## <a name="xml-schemas-tab"></a>“XML 架构”选项卡  
 浏览 XSD 架构以查找 XML 元素和属性的定义。 你可以将拖动将项放在未发布的词汇版本**词汇**选项卡上，创建定义，或者可以将项拖动到要定义谓词、 操作和自变量的条件编辑器或操作编辑器。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**选择根节点**|从包含多个根节点的 XML 架构中选择要加载的根节点。|  
  
## <a name="databases-tab"></a>“数据库”选项卡  
 浏览数据库和表定义的数据库服务器。 你可以将拖动将项放在未发布的词汇版本**词汇**选项卡上，创建定义，或者可以将项拖动到要定义谓词、 操作和自变量的条件编辑器或操作编辑器。  
  
## <a name="net-classes-tab"></a>“.NET 类”选项卡  
 浏览 .NET 程序集以查找公共 .NET 类定义。 你可以将拖动将项放在未发布的词汇版本**词汇**选项卡上，创建定义，或者可以将项拖动到要定义谓词、 操作和自变量的条件编辑器或操作编辑器。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**浏览**|从全局程序集缓存中加载 .NET 程序集|  
|**删除**|删除 .NET 程序集|