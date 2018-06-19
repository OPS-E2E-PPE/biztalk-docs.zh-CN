---
title: 版本控制服务面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- versioning, service solutions
- service solution tutorial, versioning
ms.assetid: 0e09720f-53f2-4b38-aae3-a79ddfd35be5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1c5d1475fc37322be9a8483963bbfd1432fbb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287637"
---
# <a name="versioning-the-service-oriented-solution"></a><span data-ttu-id="60893-102">版本控制服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="60893-102">Versioning the Service Oriented Solution</span></span>
<span data-ttu-id="60893-103">充当前端到解决方案中，两个业务流程**CustomerServiceReceiveSend**和**CustomerServiceNativeRequestResponse**，调用中部、 工作业务流程的**CustomerService**。</span><span class="sxs-lookup"><span data-stu-id="60893-103">The two orchestrations that act as front ends to the solution, **CustomerServiceReceiveSend** and **CustomerServiceNativeRequestResponse**, call the central, working orchestration, **CustomerService**.</span></span> <span data-ttu-id="60893-104">业务流程调用取决于包含该业务流程的程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="60893-104">Orchestration calls depend on the version number of the assembly containing the orchestration.</span></span> <span data-ttu-id="60893-105">由于所有三个业务流程都位于同一个程序集中，因此不存在版本控制问题。</span><span class="sxs-lookup"><span data-stu-id="60893-105">Because all three orchestrations are in the same assembly, there are no versioning issues.</span></span>  
  
 <span data-ttu-id="60893-106">此外，业务流程所实现的业务程序是寿命非常短的请求-响应过程，该过程会很快完成。</span><span class="sxs-lookup"><span data-stu-id="60893-106">In addition, the business process implemented by the orchestrations is a very short-lived request-response process that completes quickly.</span></span> <span data-ttu-id="60893-107">因此，在此解决方案中不会出现业务程序的版本控制问题，这是因为在不同版本的不同程序集中不存在不同的业务流程。</span><span class="sxs-lookup"><span data-stu-id="60893-107">Thus, the question of versioning the business process does not arise in this solution—there are no different orchestrations in different assemblies with different versions.</span></span>  
  
 <span data-ttu-id="60893-108">但是，业务流程要使用架构程序集中的架构。</span><span class="sxs-lookup"><span data-stu-id="60893-108">However, the orchestrations do use the schemas in the schema assembly.</span></span> <span data-ttu-id="60893-109">如果对架构进行了修订并将其编译为不同的版本，则必须使用更新版本的架构程序集重新编译业务流程。</span><span class="sxs-lookup"><span data-stu-id="60893-109">If the schemas are revised and compiled into a different version, you must recompile the orchestrations with the newer version of the schema assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60893-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60893-110">See Also</span></span>  
 [<span data-ttu-id="60893-111">面向开发的服务解决方案</span><span class="sxs-lookup"><span data-stu-id="60893-111">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)