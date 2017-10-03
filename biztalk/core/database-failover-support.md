---
title: "数据库故障转移支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09347fdd-2929-4ed9-b0d8-698508663ecd
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bbc795191eb2c13ca35d55846719cebc20d61a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="database-failover-support"></a>数据库故障转移支持
你可以将传递的实例**PolicyFetchErrorHandler**作为重载构造函数的参数的委托**策略**类。 当从数据库提取策略的详细信息时出错时，将调用委托实例。 你还可以使用 try catch 块捕获**RuleStoreConnectionException**和**RuleStoreCompatibilityException**规则引擎无法连接到规则引擎时引发的异常数据库。  
  
 如果不传递的实例**PolicyFetchErrorHandler**作为参数传递给委托**策略**构造函数，或如果你使用**规则**中调整业务流程，然后如果检测到错误发生时从数据库中，提取策略的详细信息会发生下列情况：  
  
1.  规则引擎使用的值**PolicyFetchErrorHandlerAssembly**和**PolicyFetchErrorHandlerClass**下的注册表条目**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**。 默认值**PolicyFetchErrorHandlerAssembly**和**PolicyFetchErrorHandlerClass**注册表条目是**Microsoft.BizTalk.RuleEngineExtensions**和**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**分别。  
  
2.  **ExceptionHelper**类实现**IPolicyFetchErrorMaker**接口。  
  
3.  规则引擎时，将调用**get_ErrorHandler**方法**IPolicyFetchErrorMaker**接口来获取对错误处理方法的指针，并对其进行调用。  
  
4.  默认错误处理方法调用**SetDBFailure** BTSDBAccessor.dll 中定义的方法。  
  
5.  **SetDBFailure**方法则会导致 BizTalk 服务关闭。 BizTalk 服务在一分钟内重新启动和关闭，如果数据库是仍不可用。 此周期重复，直到这些数据库。