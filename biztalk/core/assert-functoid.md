---
title: 添加 Functoid |Microsoft Docs
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
ms.openlocfilehash: 1e3f14c05d1d4fd6538c126659c27cdb8b25fe08
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530618"
---
# <a name="assert-functoid"></a>添加 Functoid

## <a name="overview"></a>概述
**Assert** functoid 输出一个字符串值或引发异常，基于一个布尔值。 如果将此 functoid 与一个或多个结合**逻辑**functoid，您可以有效地测试映射中的假设条件。 例如，如果有需要采购订单量从不超过某一阈值的映射，您可以测试采购订单值通过**Greater Than** functoid，然后连接到**Assert**functoid。 如果判断 functoid 返回 **，则返回 True**，则**Assert** functoid 将引发异常使用您提供的字符串。  
  
 ![添加 Functoid](../core/media/assertfunctoid.gif "AssertFunctoid")  
  
## <a name="see-also"></a>请参阅  
 **声明 Functoid 参考**和**判断 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]