---
title: 生效日期属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42373f55391f8bf3401d18e0a964005def222a8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389103"
---
# <a name="effective-date-properties"></a>生效日期属性
PeopleSoft Enterprise 提供的功能来计划和跟踪使用一个名为生效日期 (缩写 EFFDT) 的特殊属性的已计划的项目。 此类项实施中要么只被计划，具体取决于其日期是之前或之后在 PeopleSoft 当前日期。  
  
 如果组件接口的属性包含此类有效日期项 （即，一个名为 EFFDT 的字段），该适配器，可以让调用方不检索值或仅使用这些值的完整集合尚未生效，那些仍可进行更改.  
  
## <a name="gethistoryitems-parameter"></a>getHistoryItems 参数  
 对于包含有效日期的属性的组件接口，适配器提供了一个附加参数，调用`getHistoryItems`，为 Get 操作。 此参数是布尔型，如果设置为 True，则返回所有有效日期项。 其中包括所有过去、 当前和将来的有效日期项。  
  
 如果`getHistoryItems`参数设置为 False，返回仅当前和将来的有效日期项。 如果想要添加或更改这些项 （因为过去的项目不能更改），请选择 False。  
  
 还有可能有多个有效日期项具有相同有效日期。 在这种情况下，还必须提供附加属性，有效序列 (EFFSEQ)。 EFFSEQ 的值必须唯一，以便区分具有相同有效日期项。 请参阅 PeopleSoft 文档了解详细信息。  
  
## <a name="modifying-past-effective-dated-items"></a>修改过去的有效日期项  
 `correctionMode`参数在这种[UpdateEx](../core/updateex-method.md)并[DeleteOnly](../core/deleteonly-method.md)方法控制是否可以修改过去的有效日期的项。 如果设置为 true，所有可以修改项。 否则，修改的过去的有效日期的项将引发异常。  
  
 当调用不推荐使用`Update`具有有效日期项的组件接口的方法，您必须采取措施无法包含值的任何有效日期早于 PeopleSoft 当前有效日期或调用失败，出现异常。 但是，当前有效日期项可以包含如绕过设置属性时。 如果存在有效的序列，然后设置属性时具有的所有当前有效日期项匹配的服务器中的有效序列都将跳过。  
  
## <a name="see-also"></a>请参阅  
 [附录 a:组件接口方法](../core/appendix-a-component-interface-methods.md)