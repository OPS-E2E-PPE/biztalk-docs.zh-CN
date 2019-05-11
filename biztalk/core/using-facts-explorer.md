---
title: 使用事实浏览器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Facts Explorer
- business rules, vocabularies
- business rules, schemas
- business rules, databases
- business rules, .NET classes
- Facts Explorer [Business Rule Composer]
ms.assetid: ee125eb1-d5b9-4121-8a25-fcb7a640570e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79020dd4487d338e839a4a6d7bacc815f2b19bf9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247327"
---
# <a name="using-facts-explorer"></a>使用事实浏览器
事实浏览器包含四个选项卡：**词汇**， **XML 架构**，**数据库**，并且 **.NET 类**。  
  
## <a name="vocabularies-tab"></a>词汇选项卡  
 使用**词汇**在事实浏览器来管理词汇版本和定义的选项卡。  
  
 使用快捷菜单来访问以下选项。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**添加新词汇**|创建新的词汇。|  
|**添加新版本**|创建所选词汇的新的空版本。 可以从其他版本复制定义并将其粘贴到新版本。|  
|**粘贴词汇版本**|将以前复制的词汇版本的内容粘贴为所选词汇的新版本。|  
|**删除**|删除所选的词汇及其所有版本。|  
|**添加新定义**|启动词汇定义向导以在所选的词汇版本中创建新的定义。|  
|**保存**|保存对所选的版本及其定义所做的更改。|  
|**Publish**|发布所选的词汇版本。 请注意，不能直接修改已发布的版本。 可以复制并将其粘贴到新版本的词汇。|  
|**重新加载**|重新加载所选的词汇版本及其定义，可以选择放弃当前对该版本所做的全部更改和从规则存储恢复内容。|  
|**修改**|启动词汇定义向导以更改所选的定义。 请注意，不能修改已发布的词汇版本的定义。|  
|**转至源事实**|有关所选定义，请转至.NET 程序集、 XML 架构或数据库表中的对应源事实。|  
  
## <a name="xml-schemas-tab"></a>XML 架构选项卡  
 浏览 XSD 架构的 XML 元素和属性定义。 可以将拖到未发布的词汇版本上的项**词汇**选项卡上，以创建定义，或可以将项拖动到条件编辑器或操作编辑器中以定义谓词、 操作和参数。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**选择根节点**|选择要从包含多个根节点的 XML 架构加载的根节点。|  
  
## <a name="databases-tab"></a>数据库选项卡  
 浏览数据库和表定义的数据库服务器。 可以将拖到未发布的词汇版本上的项**词汇**选项卡上，以创建定义，或可以将项拖动到条件编辑器或操作编辑器中以定义谓词、 操作和参数。  
  
## <a name="net-classes-tab"></a>.NET 类选项卡  
 浏览查找公共.NET 类定义的.NET 程序集。 可以将拖到未发布的词汇版本上的项**词汇**选项卡上，以创建定义，或可以将项拖动到条件编辑器或操作编辑器中以定义谓词、 操作和参数。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**“浏览”**|从全局程序集缓存中加载.NET 程序集|  
|**删除**|删除.NET 程序集|