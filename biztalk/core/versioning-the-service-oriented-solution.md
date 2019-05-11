---
title: 版本控制服务面向解决方案 |Microsoft Docs
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
ms.openlocfilehash: 34896f02ac6335c8f5041ca959b25fe9ab2716c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393738"
---
# <a name="versioning-the-service-oriented-solution"></a><span data-ttu-id="6285f-102">版本控制服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="6285f-102">Versioning the Service Oriented Solution</span></span>
<span data-ttu-id="6285f-103">充当前端到解决方案中，两个业务流程**CustomerServiceReceiveSend**并**CustomerServiceNativeRequestResponse**，中间的工作业务流程调用**CustomerService**。</span><span class="sxs-lookup"><span data-stu-id="6285f-103">The two orchestrations that act as front ends to the solution, **CustomerServiceReceiveSend** and **CustomerServiceNativeRequestResponse**, call the central, working orchestration, **CustomerService**.</span></span> <span data-ttu-id="6285f-104">业务流程调用取决于包含该业务流程的程序集的版本号。</span><span class="sxs-lookup"><span data-stu-id="6285f-104">Orchestration calls depend on the version number of the assembly containing the orchestration.</span></span> <span data-ttu-id="6285f-105">由于所有三个业务流程是在同一程序集中，没有任何版本控制问题。</span><span class="sxs-lookup"><span data-stu-id="6285f-105">Because all three orchestrations are in the same assembly, there are no versioning issues.</span></span>  
  
 <span data-ttu-id="6285f-106">此外，实现的业务流程的业务流程是一个快速完成的生存期很短的请求-响应过程。</span><span class="sxs-lookup"><span data-stu-id="6285f-106">In addition, the business process implemented by the orchestrations is a very short-lived request-response process that completes quickly.</span></span> <span data-ttu-id="6285f-107">因此，版本控制的业务流程的问题不会出现在此解决方案中，有不同的业务流程中使用不同版本的不同程序集。</span><span class="sxs-lookup"><span data-stu-id="6285f-107">Thus, the question of versioning the business process does not arise in this solution—there are no different orchestrations in different assemblies with different versions.</span></span>  
  
 <span data-ttu-id="6285f-108">但是，业务流程执行操作中的架构程序集使用的架构。</span><span class="sxs-lookup"><span data-stu-id="6285f-108">However, the orchestrations do use the schemas in the schema assembly.</span></span> <span data-ttu-id="6285f-109">如果架构进行了修订，并且编译为不同的版本，则必须重新编译了架构程序集的较新版本的业务流程。</span><span class="sxs-lookup"><span data-stu-id="6285f-109">If the schemas are revised and compiled into a different version, you must recompile the orchestrations with the newer version of the schema assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6285f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="6285f-110">See Also</span></span>  
 [<span data-ttu-id="6285f-111">开发面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="6285f-111">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)