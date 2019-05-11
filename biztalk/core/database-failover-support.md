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
# <a name="database-failover-support"></a><span data-ttu-id="dfb6a-102">数据库故障转移支持</span><span class="sxs-lookup"><span data-stu-id="dfb6a-102">Database Failover Support</span></span>
<span data-ttu-id="dfb6a-103">可以将传递的实例**PolicyFetchErrorHandler**作为重载构造函数的参数的委托**策略**类。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-103">You can pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to overloaded constructors of the **Policy** class.</span></span> <span data-ttu-id="dfb6a-104">如果从数据库提取策略详细信息时发生错误，将调用委托实例。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-104">When an error occurs while fetching the policy details from the database, the delegate instance is invoked.</span></span> <span data-ttu-id="dfb6a-105">此外可以使用 try catch 块捕获**RuleStoreConnectionException**并**RuleStoreCompatibilityException**规则引擎无法连接到规则引擎时引发的异常数据库。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-105">You can also use a try-catch block to trap **RuleStoreConnectionException** and **RuleStoreCompatibilityException** exceptions that are raised when the rule engine fails to connect to the Rule Engine database.</span></span>  
  
 <span data-ttu-id="dfb6a-106">如果未通过的实例**PolicyFetchErrorHandler**委托的参数作为**策略**构造函数，或者如果您使用**CallRules**形状中业务流程，然后如果错误出现，则从数据库提取策略详细信息时则发生以下事件：</span><span class="sxs-lookup"><span data-stu-id="dfb6a-106">If you do not pass an instance of the **PolicyFetchErrorHandler** delegate as a parameter to the **Policy** constructor, or if you use the **CallRules** shape in an orchestration, then if an error occurs while fetching the policy details from the database, the following events happen:</span></span>  
  
1.  <span data-ttu-id="dfb6a-107">规则引擎使用的值**PolicyFetchErrorHandlerAssembly**并**PolicyFetchErrorHandlerClass**注册表项下的**HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-107">The rule engine uses the values of the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries under **HKEY_LOCAL_MACHINE\Software\Microsoft\BusinessRules\3.0**.</span></span> <span data-ttu-id="dfb6a-108">默认值为**PolicyFetchErrorHandlerAssembly**并**PolicyFetchErrorHandlerClass**注册表条目是**Microsoft.BizTalk.RuleEngineExtensions**并**Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper**分别。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-108">The default values for the **PolicyFetchErrorHandlerAssembly** and **PolicyFetchErrorHandlerClass** registry entries are **Microsoft.BizTalk.RuleEngineExtensions** and **Microsoft.BizTalk.RuleEngineExtension.ExceptionHelper** respectively.</span></span>  
  
2.  <span data-ttu-id="dfb6a-109">**ExceptionHelper**类实现**IPolicyFetchErrorMaker**接口。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-109">The **ExceptionHelper** class implements the **IPolicyFetchErrorMaker** interface.</span></span>  
  
3.  <span data-ttu-id="dfb6a-110">规则引擎将调用**get_ErrorHandler**方法**IPolicyFetchErrorMaker**用于获得到的错误处理方法的指针的接口和对其进行调用。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-110">The rule engine invokes the **get_ErrorHandler** method on the **IPolicyFetchErrorMaker** interface to get a pointer to the error-handling method and invokes it.</span></span>  
  
4.  <span data-ttu-id="dfb6a-111">默认的错误处理方法调用**SetDBFailure** BTSDBAccessor.dll 中定义的方法。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-111">The default error-handling method invokes the **SetDBFailure** method, which is defined in BTSDBAccessor.dll.</span></span>  
  
5.  <span data-ttu-id="dfb6a-112">**SetDBFailure**方法则会导致关闭的情况下 BizTalk 服务。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-112">The **SetDBFailure** method causes the BizTalk service to shut down.</span></span> <span data-ttu-id="dfb6a-113">BizTalk 服务在一分钟内重新启动和关闭，如果数据库仍不可用。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-113">The BizTalk service restarts in one minute and shuts down if the databases are still not available.</span></span> <span data-ttu-id="dfb6a-114">这个循环不断重复，直到数据库是可用的。</span><span class="sxs-lookup"><span data-stu-id="dfb6a-114">This cycle repeats until the databases are available.</span></span>