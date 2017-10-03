---
title: "策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Engine, policies
- policies, about policies
- policies, deploying
- policies, Business Rules Engine
- policies
- business rules, policies
- policies, versioning
- policies, testing
- policies, creating
- policies, updating
ms.assetid: 2e0ae081-938d-4e2a-947e-1c0ecfebb4b8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd05d6cf67d89ee811cac45ac3950697db74f59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="policies"></a>策略
策略是一组逻辑规则。 您可以撰写一个策略版本，保存该策略版本，通过将该策略版本应用于事实来对其进行测试，并在得到满意结果后，发布该策略版本并将其部署到产品环境中。  
  
## <a name="policy-composition"></a>撰写策略  
 可以在业务规则编辑器中通过根据事实和定义构造规则来撰写策略。 策略可以包含一个任意大小的规则集，但通常是根据与使用该策略的应用程序上下文中的特定业务域相关的规则来撰写策略。  
  
## <a name="policy-testing"></a>策略测试  
 在将策略发布和部署到产品环境中之前，可以有效地执行该策略的运行测试。 使用业务规则编辑器，您可以为策略提供事实实例，运行该策略并查看该策略的输出。 输出包括事实活动、规则执行、条件评估和议程更新。  
  
## <a name="policy-versions"></a>策略版本  
 在策略中定义所有规则之后，可以发布策略版本。 通过此方式可以锁定策略，并且策略行为将被固定下来。  
  
 给定的策略版本可以在业务环境中的一组给定条件下使用，并在这些条件发生变化时由另一版本替代。 并且，新版本和旧版本可同时由不同的应用程序使用。  
  
## <a name="policy-deployment"></a>策略部署  
 当策略准备就绪，可在产品环境中运行时，可以部署该策略以使该策略可用于主机应用程序。  
  
## <a name="dynamic-policy-updates"></a>动态策略更新  
 使用动态策略更新，您可以修改策略而不会影响业务流程的运行。 您可以创建和部署策略的更新版本，主机应用程序可以近乎实时地合并更新。 此更新不需要更改任何代码，因此，可以避免重新开发和重新部署应用程序所带来的开销。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则引擎](../core/business-rules-engine.md)