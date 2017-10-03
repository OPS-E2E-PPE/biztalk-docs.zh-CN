---
title: "附录 a： 组件接口方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cb5b87cb063f22c889291b8eff3b2be50d64a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-a-component-interface-methods"></a>附录 a： 组件接口方法
用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器提供了组件接口的标准方法。  
  
> [!NOTE]
>  各种方法的 Ex 版本中的 `interactiveMode` 参数有助于调试对后端（`Create/CreateEx`、`Update/UpdateEx` 和 `DeleteOnly`）的调用。 对后端的 *Ex 调用中的每个项都是单独调用的，因此您完全知道哪个项失败。 当你使用存在将导致性能降低\*Ex 方法因为每个属性项收到一个单独的调用。 你可以开发\*Ex 方法，然后切换到 main 方法 (例如， `Create`) 用于生产。 你还可以使用在用于生产调试交换机切换使用方法和\*Ex 方法。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [CreateEx 方法](../core/createex-method.md)  
  
-   [DeleteOnly 方法](../core/deleteonly-method.md)  
  
-   [Find 方法](../core/find-method.md)  
  
-   [Get 方法](../core/get-method.md)  
  
-   [UpdateEx 方法](../core/updateex-method.md)  
  
-   [组件接口用户定义的方法](../core/component-interface-user-defined-methods.md)  
  
-   [生效日期属性](../core/effective-date-properties.md)