---
title: 面向服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solutions
- tutorials, legacy applications
- business solutions, back-end systems
- service solution tutorial
- tutorials, services
- Web services, tutorials
- Web services, business solutions
- tutorials, applications
- applications, tutorials
- applications, services
- legacy applications, tutorials
- service solutions, business solutions
- tutorials, Web services
- tutorials, service solutions
- business solutions, totorials
- business solutions, legacy applications
- back-end systems
- tutorials, business solutions
- legacy applications, business solutions
- business solutions, Web services
- business solutions, service solutions
ms.assetid: ce7cdf8d-ecaf-4a6a-9536-a9cf5d7f874f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53712039f5aa64f85fddd1d18af121abb3bb2dbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393282"
---
# <a name="service-oriented-solution"></a><span data-ttu-id="a6800-102">面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="a6800-102">Service Oriented Solution</span></span>
<span data-ttu-id="a6800-103">面向服务的解决方案演示如何提供一种服务，可为 Web 服务和可访问的旧版应用程序表单将 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6800-103">The service oriented solution shows how to present a BizTalk application as a service that is available as a Web service and in forms accessible to legacy applications.</span></span> <span data-ttu-id="a6800-104">该解决方案还显示如何与 Web 服务作为后端进程进行通信，以及如何聚合来自多个后端系统的响应。</span><span class="sxs-lookup"><span data-stu-id="a6800-104">The solution also shows how to communicate with back-end processes as Web services, as well as how to aggregate responses from multiple back-end systems.</span></span>  
  
 <span data-ttu-id="a6800-105">各节概述了解决方案的模式和设计选项和有关生成和运行解决方案的信息的详细说明。</span><span class="sxs-lookup"><span data-stu-id="a6800-105">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a6800-106">模式和这些部分中介绍的指南旨在阐释一种特定类型的业务解决方案的方法。</span><span class="sxs-lookup"><span data-stu-id="a6800-106">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="a6800-107">模式是简单的机制，旨在应用于特定的问题，通常与其他模式相结合。</span><span class="sxs-lookup"><span data-stu-id="a6800-107">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="a6800-108">它们不应插入到应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6800-108">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="a6800-109">"按原样"提供的示例代码，不适合生产环境中使用。</span><span class="sxs-lookup"><span data-stu-id="a6800-109">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="a6800-110">它仅用于阐释模式，并因此不包含额外的代码，如异常处理、 日志记录、 安全性和验证。</span><span class="sxs-lookup"><span data-stu-id="a6800-110">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="a6800-111">Microsoft 不支持"按原样"的示例代码部署到生产环境。</span><span class="sxs-lookup"><span data-stu-id="a6800-111">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6800-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="a6800-112">In This Section</span></span>  
  
-   [<span data-ttu-id="a6800-113">了解面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="a6800-113">Understanding the Service Oriented Solution</span></span>](../core/understanding-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="a6800-114">开发面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="a6800-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)  
  
-   [<span data-ttu-id="a6800-115">部署服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="a6800-115">Deploying the Service Oriented Solution</span></span>](../core/deploying-the-service-oriented-solution.md)