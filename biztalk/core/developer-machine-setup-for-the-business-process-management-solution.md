---
title: "业务流程管理解决方案的开发人员计算机设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developer servers
- process management solution tutorial, developer servers
- process management solution tutorial, deploying
ms.assetid: cf975323-53ec-45a8-9f68-80ad423f298b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e2491d755062828a3204d895fa7be7552ef06d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="developer-machine-setup-for-the-business-process-management-solution"></a><span data-ttu-id="915a8-102">业务流程管理解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="915a8-102">Developer Machine Setup for the Business Process Management Solution</span></span>
<span data-ttu-id="915a8-103">业务流程管理 (BPM) 解决方案为您展示了一种在 BizTalk 应用程序中构造流程管理器的方法。</span><span class="sxs-lookup"><span data-stu-id="915a8-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="915a8-104">该解决方案使用组件来选择和控制订单处理中的阶段序列。</span><span class="sxs-lookup"><span data-stu-id="915a8-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="915a8-105">该解决方案首先获取订单（该订单可能是申请新的服务、申请升级或申请终止服务），然后记录该订单，并在传递订单以进行处理之前对该订单进行确认。</span><span class="sxs-lookup"><span data-stu-id="915a8-105">The solution takes an order—which may be for new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="915a8-106">处理过程由一个或多个订单处理阶段组成。</span><span class="sxs-lookup"><span data-stu-id="915a8-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="915a8-107">最后，该解决方案向原始订单请求返回响应。</span><span class="sxs-lookup"><span data-stu-id="915a8-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="915a8-108">作为开发人员，您首先要制订在单台计算机上运行的方案。</span><span class="sxs-lookup"><span data-stu-id="915a8-108">As a developer, you first get the scenario running on a single computer.</span></span> <span data-ttu-id="915a8-109">在单台计算机上测试功能之后，将与 IT 专业人员讨论如何在生产服务器上部署该解决方案。</span><span class="sxs-lookup"><span data-stu-id="915a8-109">After testing functionalities on the single computer, you will discuss how to deploy the solution on production servers with IT professionals.</span></span> <span data-ttu-id="915a8-110">您需要帮助他们设计系统结构以满足诸如高可用性、更佳的性能和更便于维护等方面的服务需求。</span><span class="sxs-lookup"><span data-stu-id="915a8-110">You need to help them to design the system architecture to satisfy service requirements such as high availability, better performance, and easier maintenance.</span></span> <span data-ttu-id="915a8-111">然后，将根据设计为进行生产部署准备资源。</span><span class="sxs-lookup"><span data-stu-id="915a8-111">You will then prepare resources for production deployment based on the design.</span></span>  
  
 <span data-ttu-id="915a8-112">本部署指南介绍了如何在单台计算机上安装和测试业务流程管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="915a8-112">This deployment guide describes how to install and test the business process management solution on a single computer.</span></span>  
  
 <span data-ttu-id="915a8-113">有关业务流程管理解决方案的详细信息，请参阅[了解业务流程管理解决方案](../core/understanding-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="915a8-113">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="915a8-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="915a8-114">In This Section</span></span>  
  
-   [<span data-ttu-id="915a8-115">在安装业务流程管理解决方案之前</span><span class="sxs-lookup"><span data-stu-id="915a8-115">Before Installing the Business Process Management Solution</span></span>](../core/before-installing-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="915a8-116">如何安装业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="915a8-116">How to Install the Business Process Management Solution</span></span>](../core/how-to-install-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="915a8-117">如何运行业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="915a8-117">How to Run the Business Process Management Solution</span></span>](../core/how-to-run-the-business-process-management-solution.md)