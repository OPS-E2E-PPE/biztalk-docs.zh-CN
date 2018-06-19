---
title: 数据库故障转移支持 |Microsoft 文档
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
ms.openlocfilehash: 3bbc795191eb2c13ca35d55846719cebc20d61a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238629"
---
# <a name="database-failover-support"></a><span data-ttu-id="de440-102">数据库故障转移支持</span><span class="sxs-lookup"><span data-stu-id="de440-102">Database Failover Support</span></span>
<span data-ttu-id="de440-103">你可以将传递的实例**PolicyFetchErrorHandler**作为重载构造函数的参数的委托**策略**类。</span><span class="sxs-lookup"><span data-stu-id="de440-103">You can pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to overloaded constructors of the **Policy** class.</span></span> <span data-ttu-id="de440-104">当从数据库提取策略的详细信息时出错时，将调用委托实例。</span><span class="sxs-lookup"><span data-stu-id="de440-104">When an error occurs while fetching the policy details from the database, the delegate instance is invoked.</span></span> <span data-ttu-id="de440-105">你还可以使用 try catch 块捕获**RuleStoreConnectionException**和**RuleStoreCompatibilityException**规则引擎无法连接到规则引擎时引发的异常数据库。</span><span class="sxs-lookup"><span data-stu-id="de440-105">You can also use a try-catch block to trap **RuleStoreConnectionException** and **RuleStoreCompatibilityException** exceptions that are raised when the rule engine fails to connect to the Rule Engine database.</span></span>  
  
 <span data-ttu-id="de440-106">如果不传递的实例**PolicyFetchErrorHandler**作为参数传递给委托**策略**构造函数，或如果你使用**规则**中调整业务流程，然后如果检测到错误发生时从数据库中，提取策略的详细信息会发生下列情况：</span><span class="sxs-lookup"><span data-stu-id="de440-106">If you do not pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to the **Policy** constructor, or if you use the **CallRules** shape in an orchestration, then if an error occurs while fetching the policy details from the database, the following events happen:</span></span>  
  
1.  <span data-ttu-id="de440-107">规则引擎使用的值**PolicyFetchErrorHandlerAssembly**和**PolicyFetchErrorHandlerClass**下的注册表条目**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**。</span><span class="sxs-lookup"><span data-stu-id="de440-107">The rule engine uses the values of the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**.</span></span> <span data-ttu-id="de440-108">默认值**PolicyFetchErrorHandlerAssembly**和**PolicyFetchErrorHandlerClass**注册表条目是**Microsoft.BizTalk.RuleEngineExtensions**和**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**分别。</span><span class="sxs-lookup"><span data-stu-id="de440-108">The default values for the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries are **Microsoft.BizTalk.RuleEngineExtensions** and **Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper** respectively.</span></span>  
  
2.  <span data-ttu-id="de440-109">**ExceptionHelper**类实现**IPolicyFetchErrorMaker**接口。</span><span class="sxs-lookup"><span data-stu-id="de440-109">The **ExceptionHelper** class implements the **IPolicyFetchErrorMaker** interface.</span></span>  
  
3.  <span data-ttu-id="de440-110">规则引擎时，将调用**get_ErrorHandler**方法**IPolicyFetchErrorMaker**接口来获取对错误处理方法的指针，并对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="de440-110">The rule engine invokes the **get_ErrorHandler** method on the **IPolicyFetchErrorMaker** interface to get a pointer to the error-handling method and invokes it.</span></span>  
  
4.  <span data-ttu-id="de440-111">默认错误处理方法调用**SetDBFailure** BTSDBAccessor.dll 中定义的方法。</span><span class="sxs-lookup"><span data-stu-id="de440-111">The default error-handling method invokes the **SetDBFailure** method, which is defined in BTSDBAccessor.dll.</span></span>  
  
5.  <span data-ttu-id="de440-112">**SetDBFailure**方法则会导致 BizTalk 服务关闭。</span><span class="sxs-lookup"><span data-stu-id="de440-112">The **SetDBFailure** method causes the BizTalk service to shut down.</span></span> <span data-ttu-id="de440-113">BizTalk 服务在一分钟内重新启动和关闭，如果数据库是仍不可用。</span><span class="sxs-lookup"><span data-stu-id="de440-113">The BizTalk service restarts in one minute and shuts down if the databases are still not available.</span></span> <span data-ttu-id="de440-114">此周期重复，直到这些数据库。</span><span class="sxs-lookup"><span data-stu-id="de440-114">This cycle repeats until the databases are available.</span></span>