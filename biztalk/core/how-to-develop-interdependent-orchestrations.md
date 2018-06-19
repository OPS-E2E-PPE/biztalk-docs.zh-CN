---
title: 如何开发相互依赖的业务流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5464096e-66d8-48de-bc02-c754c5cfbada
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93f8d086a60487e144b02c01a393eb6f10a63b40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249477"
---
# <a name="how-to-develop-interdependent-orchestrations"></a><span data-ttu-id="a149c-102">如何开发相互依赖的业务流程</span><span class="sxs-lookup"><span data-stu-id="a149c-102">How to Develop Interdependent Orchestrations</span></span>
<span data-ttu-id="a149c-103">你可以使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]开发一套提供相互依赖 Web 服务的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a149c-103">You can use [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to develop a set of orchestrations that have interdependent Web services.</span></span> <span data-ttu-id="a149c-104">当必须引用数据类型和/或业务流程从中调用它们中的端口的业务流程时，会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="a149c-104">This scenario arises when you have orchestrations that reference data types and/or ports in the orchestration from which they were called.</span></span> <span data-ttu-id="a149c-105">这种方案的示例的特征如下：</span><span class="sxs-lookup"><span data-stu-id="a149c-105">An example of this type of scenario is characterized by the following:</span></span>  
  
-   <span data-ttu-id="a149c-106">具有两个或多个业务流程。</span><span class="sxs-lookup"><span data-stu-id="a149c-106">You have two or more orchestrations.</span></span>  
  
-   <span data-ttu-id="a149c-107">第一个业务流程 (Orch1) 使用单向 Web 服务调用调用第二个业务流程 (Orch2)。</span><span class="sxs-lookup"><span data-stu-id="a149c-107">The first orchestration (Orch1) calls the second orchestration (Orch2) with a one-way Web service call.</span></span>  
  
-   <span data-ttu-id="a149c-108">Orch2 响应回 Orch1 与 Web 服务调用。</span><span class="sxs-lookup"><span data-stu-id="a149c-108">Orch2 responds back to Orch1 with a Web service call.</span></span>  
  
 <span data-ttu-id="a149c-109">有关此类型的项目的一个示例，请参阅[教程 2： 采购订单过程](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467)。</span><span class="sxs-lookup"><span data-stu-id="a149c-109">For one example of this type of project, see [Tutorial 2: Purchase Order Process](http://msdn.microsoft.com/library/a324ef1b-39b3-49ab-9719-a13f526cb467).</span></span>  
  
### <a name="to-develop-two-interdependent-orchestrations-orch1-and-orch2"></a><span data-ttu-id="a149c-110">若要开发 Orch1 和 Orch2 的两个相互依赖业务流程</span><span class="sxs-lookup"><span data-stu-id="a149c-110">To develop two interdependent orchestrations Orch1 and Orch2</span></span>  
  
1.  <span data-ttu-id="a149c-111">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建具有接收端口将作为 Web 服务公开 Orch1 的部分版本。</span><span class="sxs-lookup"><span data-stu-id="a149c-111">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a partial version of the Orch1 that has a receive port which will be exposed as a Web service.</span></span>  
  
2.  <span data-ttu-id="a149c-112">编译 Orch1。</span><span class="sxs-lookup"><span data-stu-id="a149c-112">Compile Orch1.</span></span>  
  
3.  <span data-ttu-id="a149c-113">运行 Web 服务发布向导并发布该端口。</span><span class="sxs-lookup"><span data-stu-id="a149c-113">Run the Web Services Publishing Wizard and publish the port.</span></span>  
  
4.  <span data-ttu-id="a149c-114">使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、 创建和完成所有 Orch2，使用 Orch1 的 web 服务。</span><span class="sxs-lookup"><span data-stu-id="a149c-114">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create and complete all of Orch2, consuming Orch1's web service.</span></span>  
  
5.  <span data-ttu-id="a149c-115">编译 Orch2。</span><span class="sxs-lookup"><span data-stu-id="a149c-115">Compile Orch2.</span></span>  
  
6.  <span data-ttu-id="a149c-116">运行 Web 服务发布向导并发布端口。</span><span class="sxs-lookup"><span data-stu-id="a149c-116">Run the Web Services Publishing Wizard and publish the port(s).</span></span>  
  
7.  <span data-ttu-id="a149c-117">完成 Orch1，使用 Orch2 的 web 服务根据需要。</span><span class="sxs-lookup"><span data-stu-id="a149c-117">Complete Orch1, consuming Orch2's web service(s) as needed.</span></span>  
  
8.  <span data-ttu-id="a149c-118">重新编译 Orch1。</span><span class="sxs-lookup"><span data-stu-id="a149c-118">Recompile Orch1.</span></span>  
  
9. <span data-ttu-id="a149c-119">部署 Orch1 和 Orch2。</span><span class="sxs-lookup"><span data-stu-id="a149c-119">Deploy Orch1 and Orch2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a149c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a149c-120">See Also</span></span>  
 [<span data-ttu-id="a149c-121">如何使用发布向导的 BizTalk Web 服务发布作为 Web 服务业务流程</span><span class="sxs-lookup"><span data-stu-id="a149c-121">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)