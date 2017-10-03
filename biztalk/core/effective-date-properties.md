---
title: "生效日期属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- effective-dated items
- getHistoryItems parameter
- Effective Date
- EFFDT
- planned items, scheduling and tracking
ms.assetid: 0d9a153c-7ea5-41cf-9e4e-055e1c18f64b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34f1c4cf3579a3381c846ddbb9896b2e5be26f6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="effective-date-properties"></a>生效日期属性
PeopleSoft Enterprise 通过使用名为“有效日期”（简写为 EFFDT）的特殊属性，提供了为项目制定计划和跟踪已计划项目的功能。 此类项目要么正在实施中要么只是已制定了计划，具体取决于其日期是在 PeopleSoft 当前日期之前还是之后。  
  
 如果组件接口的属性包含此类有效日期项（即，名为 EFFDT 的字段），则呼叫方可以使用适配器来检索完整的值组，或只检索尚未生效的值（仍可更改的值）。  
  
## <a name="gethistoryitems-parameter"></a>getHistoryItems 参数  
 对于其属性包含有效日期的组件接口，适配器会为 Get 操作提供一个名为 `getHistoryItems` 的附加参数。 此参数为布尔型，如果将其设置为 True，则会返回所有有效日期项。 其中包括所有过去、当前和将来的有效日期项。  
  
 如果将 `getHistoryItems` 参数设置为 False，则只会返回当前和将来的有效日期项。 如果您需要添加或更改这些项目，请选择 False（因为过去的项目无法更改）。  
  
 也可以出现多个有效日期项具有相同有效日期的情况。 在这种情况下，还必须提供一个附加属性：“有效序列”(EFFSEQ)。 EFFSEQ 的值必须唯一，以便区分具有相同有效日期的项目。 请参阅 PeopleSoft 文档以了解更多信息。  
  
## <a name="modifying-past-effective-dated-items"></a>修改过生效日期的项  
 `correctionMode`中同时参数[UpdateEx](../core/updateex-method.md)和[DeleteOnly](../core/deleteonly-method.md)方法控制是否可以修改过去有效的发布日期为项。 如果将其设置为 True，则可以修改所有项目。 否则，修改过去的有效日期项会生成异常。  
  
 对具有有效日期项的组件接口调用已弃用的 `Update` 方法时，您务必要小心不要包含任何早于 PeopleSoft 当前有效日期的有效日期值，否则，调用会失败并生成异常。 但是，可以包含当前的有效日期项，因为在设置属性时会绕过该项目。 如果存在“有效序列”，则在设置属性时会跳过服务器中带有匹配的“有效序列”的所有当前有效日期项。  
  
## <a name="see-also"></a>另请参阅  
 [附录 a： 组件接口方法](../core/appendix-a-component-interface-methods.md)