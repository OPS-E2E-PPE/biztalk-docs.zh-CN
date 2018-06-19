---
title: 面向服务的解决方案 |Microsoft 文档
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
ms.openlocfilehash: 5a1c69d537469cc1c2a4d9d93cde37014b31daa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271365"
---
# <a name="service-oriented-solution"></a><span data-ttu-id="c8fc7-102">面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="c8fc7-102">Service Oriented Solution</span></span>
<span data-ttu-id="c8fc7-103">面向服务的解决方案显示如何将 BizTalk 应用程序展示为用作 Web Services 的服务、以及旧版应用程序可访问的表单。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-103">The service oriented solution shows how to present a BizTalk application as a service that is available as a Web service and in forms accessible to legacy applications.</span></span> <span data-ttu-id="c8fc7-104">该解决方案还显示如何与作为 Web Services 的后端进程进行通信，以及如何从多个后端系统聚合响应。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-104">The solution also shows how to communicate with back-end processes as Web services, as well as how to aggregate responses from multiple back-end systems.</span></span>  
  
 <span data-ttu-id="c8fc7-105">本部分对该解决方案进行了概括介绍，对模式和设计选项进行了详细说明，并提供了有关构建和运行该解决方案的信息。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-105">The sections provide an overview of the solution, detailed explanations of the patterns and design choices, and information about building and running the solution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8fc7-106">这些部分中介绍的模式和指南旨在阐释一种针对特殊类型业务解决方案的方法。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-106">The patterns and guidance documented in these sections are intended to illustrate an approach to a particular kind of business solution.</span></span> <span data-ttu-id="c8fc7-107">模式是一些可应用于特定问题的简单机制并且通常结合了其他模式。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-107">Patterns are simple mechanisms that are meant to be applied to a specific problem and are usually combined with other patterns.</span></span> <span data-ttu-id="c8fc7-108">它们并非是要插入到某个应用程序之中。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-108">They are not meant to be plugged into an application.</span></span> <span data-ttu-id="c8fc7-109">示例代码按“原样”提供并且不应将其用于生产目的。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-109">Example code is provided "as is" and is not intended for production use.</span></span> <span data-ttu-id="c8fc7-110">提供示例代码的目的仅在于描述模式，因此并未包含诸如异常处理、日志记录、安全性和有效性验证之类的额外代码。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-110">It is only intended to illustrate the pattern and therefore does not include extra code, such as exception handling, logging, security, and validation.</span></span> <span data-ttu-id="c8fc7-111">Microsoft 不支持将按“原样”提供的示例代码部署到生产环境中。</span><span class="sxs-lookup"><span data-stu-id="c8fc7-111">Microsoft does not support deploying the example code "as is" to production.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8fc7-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="c8fc7-112">In This Section</span></span>  
  
-   [<span data-ttu-id="c8fc7-113">了解服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="c8fc7-113">Understanding the Service Oriented Solution</span></span>](../core/understanding-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="c8fc7-114">面向开发的服务解决方案</span><span class="sxs-lookup"><span data-stu-id="c8fc7-114">Developing a Service Oriented Solution</span></span>](../core/developing-a-service-oriented-solution.md)  
  
-   [<span data-ttu-id="c8fc7-115">部署服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="c8fc7-115">Deploying the Service Oriented Solution</span></span>](../core/deploying-the-service-oriented-solution.md)