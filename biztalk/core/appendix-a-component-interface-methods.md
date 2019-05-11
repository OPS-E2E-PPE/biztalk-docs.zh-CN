---
title: 附录 A：组件接口方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- component interfaces, methods
- methods, component interfaces
- component interface methods
ms.assetid: c8377589-fbdf-4287-b822-53263a00381d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48487071e0c4099158a10b0a7cfb922ad8d75717
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359611"
---
# <a name="appendix-a-component-interface-methods"></a>附录 A：组件接口方法
用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器提供了组件接口的标准方法。  
  
> [!NOTE]
>  `interactiveMode`参数的方法的 Ex 版本中有助于调试对后端的调用 (`Create/CreateEx`， `Update/UpdateEx`，和`DeleteOnly`)。 中的每项 * Ex 调用到后端分别调用，以便您知道哪一项完全失败。 存在使用时是性能降低\*Ex 方法因为每个属性的项都会接收单独调用。 可以使用开发\*Ex 方法，然后切换到 main 方法 (例如， `Create`) 用于生产。 您还可以使用在用于生产调试开关使用的方法之间进行切换和\*Ex 方法。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [CreateEx 方法](../core/createex-method.md)  
  
-   [DeleteOnly 方法](../core/deleteonly-method.md)  
  
-   [Find 方法](../core/find-method.md)  
  
-   [Get 方法](../core/get-method.md)  
  
-   [UpdateEx 方法](../core/updateex-method.md)  
  
-   [组件接口用户定义的方法](../core/component-interface-user-defined-methods.md)  
  
-   [“有效日期”属性](../core/effective-date-properties.md)