---
title: 数据库故障转移支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09347fdd-2929-4ed9-b0d8-698508663ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774976e245d8b7ae72d8b10807a4166aa36e3d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352621"
---
# <a name="database-failover-support"></a>数据库故障转移支持
可以将传递的实例**PolicyFetchErrorHandler**作为重载构造函数的参数的委托**策略**类。 如果从数据库提取策略详细信息时发生错误，将调用委托实例。 此外可以使用 try catch 块捕获**RuleStoreConnectionException**并**RuleStoreCompatibilityException**规则引擎无法连接到规则引擎时引发的异常数据库。  
  
 如果未通过的实例**PolicyFetchErrorHandler**委托的参数作为**策略**构造函数，或者如果您使用**CallRules**形状中业务流程，然后如果错误出现，则从数据库提取策略详细信息时则发生以下事件：  
  
1.  规则引擎使用的值**PolicyFetchErrorHandlerAssembly**并**PolicyFetchErrorHandlerClass**注册表项下的**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**。 默认值为**PolicyFetchErrorHandlerAssembly**并**PolicyFetchErrorHandlerClass**注册表条目是**Microsoft.BizTalk.RuleEngineExtensions**并**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**分别。  
  
2.  **ExceptionHelper**类实现**IPolicyFetchErrorMaker**接口。  
  
3.  规则引擎将调用**get_ErrorHandler**方法**IPolicyFetchErrorMaker**用于获得到的错误处理方法的指针的接口和对其进行调用。  
  
4.  默认的错误处理方法调用**SetDBFailure** BTSDBAccessor.dll 中定义的方法。  
  
5.  **SetDBFailure**方法则会导致关闭的情况下 BizTalk 服务。 BizTalk 服务在一分钟内重新启动和关闭，如果数据库仍不可用。 这个循环不断重复，直到数据库是可用的。