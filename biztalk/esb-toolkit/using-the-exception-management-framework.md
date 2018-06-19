---
title: 使用异常管理框架 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b69c9c01-e7e4-4788-8fe2-43d32075155d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47442604831a3a11bb9d00b65f9dc34961de2367
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295181"
---
# <a name="using-the-exception-management-framework"></a><span data-ttu-id="86755-102">使用异常管理框架</span><span class="sxs-lookup"><span data-stu-id="86755-102">Using the Exception Management Framework</span></span>
<span data-ttu-id="86755-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用异常的动态转换和路由进行通信失败 （例如，非部署映射或未返回映射名称的规则）。</span><span class="sxs-lookup"><span data-stu-id="86755-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses exceptions to communicate failures (for example, a non-deployed map or rules that do not return a map name) for dynamic transformations and routing.</span></span> <span data-ttu-id="86755-104">当转换或路由过程失败时，ESB 创建一条异常消息，并将其提交通过直接绑定到消息框数据库端口。</span><span class="sxs-lookup"><span data-stu-id="86755-104">When a transformation or routing process fails, the ESB creates an exception message and submits it through a direct-bound port to the Message Box database.</span></span> <span data-ttu-id="86755-105">ESB 还实现名为所有发送端口。订阅和检索异常消息，并将其发布到 ESB 管理门户的异常。</span><span class="sxs-lookup"><span data-stu-id="86755-105">The ESB also implements a send port named ALL.Exceptions that subscribes to and retrieves exception messages and publishes them to the ESB Management Portal.</span></span>  
  
 <span data-ttu-id="86755-106">此外，所有的业务流程示例使用 ESB 失败业务流程异常路由 API 来处理异常。</span><span class="sxs-lookup"><span data-stu-id="86755-106">In addition, all orchestration samples use the ESB Failed Orchestration Exception Routing API to handle exceptions.</span></span> <span data-ttu-id="86755-107">在部署任何业务流程项目中，可以使用此 API。</span><span class="sxs-lookup"><span data-stu-id="86755-107">You can use this API in any orchestration project you deploy.</span></span> <span data-ttu-id="86755-108">ESB 失败业务流程异常路由功能可提供一种标准的方式，以捕获并报告在 BizTalk Server 环境中的所有异常。</span><span class="sxs-lookup"><span data-stu-id="86755-108">The ESB Failed Orchestration Exception Routing feature provides a standard way to trap and report all exceptions in a BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="86755-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含演示如何使用 ESB 异常管理框架的几个示例项目。</span><span class="sxs-lookup"><span data-stu-id="86755-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains several sample projects that demonstrate how to use the ESB Exception Management Framework.</span></span> <span data-ttu-id="86755-110">以下两个项目封装 ESB 失败业务流程异常路由 API:</span><span class="sxs-lookup"><span data-stu-id="86755-110">The following two projects encapsulate the ESB Failed Orchestration Exception Routing API:</span></span>  
  
-   <span data-ttu-id="86755-111">**ESB。ExceptionHandling**。</span><span class="sxs-lookup"><span data-stu-id="86755-111">**ESB.ExceptionHandling**.</span></span> <span data-ttu-id="86755-112">此项目包含用于处理在业务流程中的错误消息处理的所有公共方法。</span><span class="sxs-lookup"><span data-stu-id="86755-112">This project contains all the public methods for handling fault message processing in orchestrations.</span></span> <span data-ttu-id="86755-113">你必须在本地服务器上的全局程序集缓存中的此项目中注册程序集。</span><span class="sxs-lookup"><span data-stu-id="86755-113">You must register the assembly in this project in the global assembly cache on the local server.</span></span>  
  
-   <span data-ttu-id="86755-114">**ESB。ExceptionHandling.Schemas.Faults**。</span><span class="sxs-lookup"><span data-stu-id="86755-114">**ESB.ExceptionHandling.Schemas.Faults**.</span></span> <span data-ttu-id="86755-115">此项目包含命名空间定义的错误消息架构**http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling**和系统属性架构。</span><span class="sxs-lookup"><span data-stu-id="86755-115">This project contains the fault message schema defined by the namespace **http://schemas.microsoft.biztalk.practices.esb.com/exceptionhandling** and the system property schema.</span></span> <span data-ttu-id="86755-116">必须将此项目部署到 Microsoft.Practices.ESB 应用程序容器。</span><span class="sxs-lookup"><span data-stu-id="86755-116">You must deploy this project to the Microsoft.Practices.ESB application container.</span></span>  
  
 <span data-ttu-id="86755-117">使用 ESB 失败业务流程异常路由 API 的所有项目必须都引用核心程序集：</span><span class="sxs-lookup"><span data-stu-id="86755-117">All projects that use the ESB Failed Orchestration Exception Routing API must reference the core assemblies:</span></span>  
  
-   <span data-ttu-id="86755-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span><span class="sxs-lookup"><span data-stu-id="86755-118">**Microsoft.Practices.ESB.ExceptionHandling.dll**</span></span>  
  
-   <span data-ttu-id="86755-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span><span class="sxs-lookup"><span data-stu-id="86755-119">**Microsoft.Practices.ESB.ExceptionHandling.Schemas.Faults.dll**</span></span>  
  
 <span data-ttu-id="86755-120">下列各节提供有关使用 ESB 异常管理框架的详细信息：</span><span class="sxs-lookup"><span data-stu-id="86755-120">The following sections provide more information about using the ESB Exception Management Framework:</span></span>  
  
-   [<span data-ttu-id="86755-121">ESB 异常 API 成员</span><span class="sxs-lookup"><span data-stu-id="86755-121">The ESB Exception API Members</span></span>](../esb-toolkit/the-esb-exception-api-members.md)  
  
-   [<span data-ttu-id="86755-122">创建并发布错误消息</span><span class="sxs-lookup"><span data-stu-id="86755-122">Creating and Publishing Fault Messages</span></span>](../esb-toolkit/creating-and-publishing-fault-messages.md)  
  
-   [<span data-ttu-id="86755-123">订阅以及提取消息</span><span class="sxs-lookup"><span data-stu-id="86755-123">Subscribing to and Extracting Messages</span></span>](../esb-toolkit/subscribing-to-and-extracting-messages.md)  
  
-   [<span data-ttu-id="86755-124">方案解决方案步骤</span><span class="sxs-lookup"><span data-stu-id="86755-124">Scenario Solution Steps</span></span>](../esb-toolkit/scenario-solution-steps.md)