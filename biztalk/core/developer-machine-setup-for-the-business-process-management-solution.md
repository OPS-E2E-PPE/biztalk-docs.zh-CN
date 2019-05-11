---
title: 业务流程管理解决方案的开发人员计算机设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developer servers
- process management solution tutorial, developer servers
- process management solution tutorial, deploying
ms.assetid: cf975323-53ec-45a8-9f68-80ad423f298b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35249beb37b648ee730532d27df50e7e50fa210d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351566"
---
# <a name="developer-machine-setup-for-the-business-process-management-solution"></a><span data-ttu-id="f1b89-102">业务流程管理解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="f1b89-102">Developer Machine Setup for the Business Process Management Solution</span></span>
<span data-ttu-id="f1b89-103">业务流程管理 (BPM) 解决方案显示了一种方法来构造流程管理器中的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f1b89-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="f1b89-104">该解决方案使用一个组件来选择和控制订单处理中的阶段序列。</span><span class="sxs-lookup"><span data-stu-id="f1b89-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="f1b89-105">该解决方案首先获取订单-这可能会为新的服务、 升级或服务终止，记录它，并处理在传递之前该订单进行确认。</span><span class="sxs-lookup"><span data-stu-id="f1b89-105">The solution takes an order—which may be for new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="f1b89-106">处理由处理订单的一个或多个阶段组成。</span><span class="sxs-lookup"><span data-stu-id="f1b89-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="f1b89-107">最后，该解决方案将返回对原始订单请求的响应。</span><span class="sxs-lookup"><span data-stu-id="f1b89-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="f1b89-108">作为开发人员，您首先获得一台计算机上运行的方案。</span><span class="sxs-lookup"><span data-stu-id="f1b89-108">As a developer, you first get the scenario running on a single computer.</span></span> <span data-ttu-id="f1b89-109">测试在单台计算机上的功能之后, 将讨论如何与 IT 专业人员的生产服务器上安装解决方案。</span><span class="sxs-lookup"><span data-stu-id="f1b89-109">After testing functionalities on the single computer, you will discuss how to deploy the solution on production servers with IT professionals.</span></span> <span data-ttu-id="f1b89-110">您需要帮助他们设计系统结构以满足服务要求，如高可用性、 更好的性能和更便于维护。</span><span class="sxs-lookup"><span data-stu-id="f1b89-110">You need to help them to design the system architecture to satisfy service requirements such as high availability, better performance, and easier maintenance.</span></span> <span data-ttu-id="f1b89-111">然后将基于设计的生产部署准备资源。</span><span class="sxs-lookup"><span data-stu-id="f1b89-111">You will then prepare resources for production deployment based on the design.</span></span>  
  
 <span data-ttu-id="f1b89-112">本部署指南介绍如何安装和测试业务流程管理解决方案在单台计算机上。</span><span class="sxs-lookup"><span data-stu-id="f1b89-112">This deployment guide describes how to install and test the business process management solution on a single computer.</span></span>  
  
 <span data-ttu-id="f1b89-113">有关业务流程管理解决方案的详细信息，请参阅[了解业务流程管理解决方案](../core/understanding-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="f1b89-113">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1b89-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="f1b89-114">In This Section</span></span>  
  
-   [<span data-ttu-id="f1b89-115">在安装业务流程管理解决方案之前</span><span class="sxs-lookup"><span data-stu-id="f1b89-115">Before Installing the Business Process Management Solution</span></span>](../core/before-installing-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="f1b89-116">如何安装业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="f1b89-116">How to Install the Business Process Management Solution</span></span>](../core/how-to-install-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="f1b89-117">如何运行业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="f1b89-117">How to Run the Business Process Management Solution</span></span>](../core/how-to-run-the-business-process-management-solution.md)