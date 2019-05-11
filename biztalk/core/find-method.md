---
title: Find 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Find method
ms.assetid: 676827a6-82af-4922-bf9e-aca5bd23624b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81599a87a88aaa383616653435119ec95d6ff430
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345387"
---
# <a name="find-method"></a>Find 方法
用于返回的满足提供部分搜索项的键列表。 请注意，只有一个实例组件接口，即，没有任何键`Find()`不生成函数。 另请参阅[Get 方法](../core/get-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
Find (partialKey, keyList)  
```  
  
## <a name="parameters"></a>Parameters  
  
|参数|Description|  
|---------------|-----------------|  
|`partialKey`|其中的各个键是可选的结构。|  
|`keyList`|匹配的键列表`partialKey`。 它是一个输出参数。<br /><br /> 为特定组件接口定义，这些项对应于查找键的集合。|  
  
## <a name="remarks"></a>备注  
 当指定部分项时，就可以使用从 PeopleSoft 内部可用的相同通配符搜索`Find()`函数。 例如，"11"的部分 ACCOUNT 项返回以"11"开头的所有 ACCOUNT 项，而"%40"将都返回包含"40"项中的任意位置的所有 ACCOUNT 项。 部分项"_4_4"返回的第二个和第四个位置中的字符"4"的所有 ACCOUNT 项。  
  
 注意：使用 PeopleSoft 服务器的当前实现，如果项多于 300 个匹配搜索条件，则调用失败。 这是 PeopleSoft 服务器的限制。 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器`Find()`方法提供如果 PeopleSoft`Find`启用组件接口中的函数并且 Get 项可用。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)