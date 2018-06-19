---
title: 断言 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e91dac06-f909-4fb2-8c87-828a3dfe2c27
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03237c27e0e35642be197b549c8b0102d9350702
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230309"
---
# <a name="assert-functoid"></a>“添加”Functoid

## <a name="overview"></a>概述
**断言**functoid 输出一个字符串值或引发异常基于布尔值。 如果使用一个或多个组合此 functoid**逻辑**functoid，你可以有效地测试你的代码图中的假设条件。 例如，如果你有需要采购订单金额，决不要超过特定阈值的映射，你可以测试采购订单值使用**大于**functoid，然后连接到**断言**functoid。 如果逻辑 functoid 返回**True**、**断言**functoid 将引发异常使用您提供的字符串。  
  
 ![断言 Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")  
  
## <a name="see-also"></a>另请参阅  
 **断言 Functoid 引用**和**逻辑 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]