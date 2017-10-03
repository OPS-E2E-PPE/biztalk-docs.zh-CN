---
title: "Find 方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Find method
ms.assetid: 676827a6-82af-4922-bf9e-aca5bd23624b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5432c68c36dcf8e769351af6d57f3cd3ed712b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="find-method"></a>Find 方法
用于返回满足所提供部分搜索项的项列表。 请注意，对于只有一个实例组件接口（即无项），不会生成 `Find()` 函数。 另请参阅[Get 方法](../core/get-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`partialKey`|各个项可选的结构。|  
|`keyList`|与 `partialKey` 匹配的项列表。 它是一个输出参数。<br /><br /> 这些项对应于为特定组件接口定义的“查找”项集。|  
  
## <a name="remarks"></a>注释  
 指定部分项时，可以使用从 PeopleSoft 内部 `Find()` 函数中可用的相同通配符搜索。 例如，"11" 的部分 ACCOUNT 项将返回以 "11" 开始的所有 ACCOUNT 项，而 "%40" 将返回项中任何位置包含 "40" 的所有 ACCOUNT 项。 部分项 "_4_4" 将返回第 2 个和第 4 个位置为字符 4 的所有 ACCOUNT 项。  
  
 注意： 与 PeopleSoft 服务器的当前实现，如果大于 300 个项匹配搜索条件，则调用失败。 这是 PeopleSoft 服务器的限制。 如果组件接口中的 PeopleSoft `Find()` 函数已启用，并且 Get 项可用，则提供用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器 `Find` 方法。  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)