---
title: 部署业务流程管理解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, process management solution tutorial
- process management solution tutorial, deploying
ms.assetid: e033e0cd-0333-4f16-a4a0-eaae9ce98fcc
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a61048ecb90876b251657f00361c35587a7ec1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239437"
---
# <a name="deploying-the-business-process-management-solution"></a><span data-ttu-id="b0d6a-102">部署业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="b0d6a-102">Deploying the Business Process Management Solution</span></span>
<span data-ttu-id="b0d6a-103">业务流程管理 (BPM) 解决方案为您展示了一种在 BizTalk 应用程序中构造流程管理器的方法。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-103">The Business Process Management (BPM) solution shows one way to construct a process manager in a BizTalk application.</span></span> <span data-ttu-id="b0d6a-104">该解决方案使用组件来选择和控制订单处理中的阶段序列。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-104">The solution uses a component to select and control the sequence of stages in order processing.</span></span> <span data-ttu-id="b0d6a-105">解决方案采用订单-这可能会为新的服务、 升级时或服务终止-记录它，并将其上传递以进行处理之前确认顺序。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-105">The solution takes an order—which may be for a new service, an upgrade, or termination of service—logs it, and acknowledges the order before passing it on for processing.</span></span> <span data-ttu-id="b0d6a-106">处理过程由一个或多个订单处理阶段组成。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-106">The processing consists of one or more stages that handle the order.</span></span> <span data-ttu-id="b0d6a-107">最后，该解决方案向原始订单请求返回响应。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-107">Finally, the solution returns a response to the original order request.</span></span>  
  
 <span data-ttu-id="b0d6a-108">本部署指南介绍如何安装和运行在开发计算机和多个生产服务器上的业务流程管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-108">This deployment guide describes how to install and run the business process management solution on a development computer and multiple production servers.</span></span>  
  
 <span data-ttu-id="b0d6a-109">有关业务流程管理解决方案的详细信息，请参阅[了解业务流程管理解决方案](../core/understanding-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-109">For more information about the business process management solution, see [Understanding the Business Process Management Solution](../core/understanding-the-business-process-management-solution.md).</span></span>  
  
 <span data-ttu-id="b0d6a-110">**读取器指南**</span><span class="sxs-lookup"><span data-stu-id="b0d6a-110">**Reader Guidance**</span></span>  
  
 <span data-ttu-id="b0d6a-111">本文档假定您熟悉 BizTalk Server、Windows Server 和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-111">This document assumes that you are familiar with BizTalk Server, Windows Server, and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="b0d6a-112">它还假定你已了解有关企业应用程序集成和 Web 服务的基本概念。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-112">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span> <span data-ttu-id="b0d6a-113">此外，我们建议你熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和你熟悉创建项目、 设置引用，以及使用调试模式下调试和测试你的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-113">Additionally, we recommend that you are familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and that you are familiar with creating projects, setting references, and using the debug mode to debug and test your solution.</span></span> <span data-ttu-id="b0d6a-114">有关先决条件的技能和知识 IT 专业人员和开发人员的详细信息，请参阅[先决条件技能和知识](../core/prerequisite-skills-and-knowledge5.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d6a-114">For more information about the prerequisite skills and knowledge for IT professionals and developers, see [Prerequisite Skills and Knowledge](../core/prerequisite-skills-and-knowledge5.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0d6a-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="b0d6a-115">In This Section</span></span>  
  
-   [<span data-ttu-id="b0d6a-116">业务流程管理解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="b0d6a-116">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)