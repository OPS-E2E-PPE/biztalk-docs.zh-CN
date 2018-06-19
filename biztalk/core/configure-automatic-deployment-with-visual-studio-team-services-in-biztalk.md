---
title: 使用 Visual Studio Team Services 中配置自动部署 |Microsoft 文档
description: 安装 BizTalk 功能包，可使用 VSTS 应用程序生命周期管理部署到不同的 BizTalk 环境应用程序
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d135960143fed33d1ce4847c681f5b1134489b65
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25497878"
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="9a720-103">使用 BizTalk Server 中的 Visual Studio Team Services 中配置自动部署</span><span class="sxs-lookup"><span data-stu-id="9a720-103">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="9a720-104">概述</span><span class="sxs-lookup"><span data-stu-id="9a720-104">Overview</span></span>

<span data-ttu-id="9a720-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]提供改进的自动部署和应用程序生命周期管理 (ALM) 体验。</span><span class="sxs-lookup"><span data-stu-id="9a720-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="9a720-106">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，我们改进了此功能：</span><span class="sxs-lookup"><span data-stu-id="9a720-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, we've improved this feature:</span></span>

* <span data-ttu-id="9a720-107">Visual Studio 中，设置**应用程序名称**的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="9a720-107">Within Visual Studio, set the **Application Name** of your BizTalk application</span></span>
* <span data-ttu-id="9a720-108">除了使用基于代理的部署，你可以使用[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)部署 BizTalk 应用程序向多个服务器</span><span class="sxs-lookup"><span data-stu-id="9a720-108">In addition to using an agent-based deployment, you can also use [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) to deploy your BizTalk applications to multiple servers</span></span>
* <span data-ttu-id="9a720-109">在发布任务中，可以安装 BizTalk 应用程序，并输入到部署包的 BizTalk 管理计算机和路径</span><span class="sxs-lookup"><span data-stu-id="9a720-109">In the release task, you can install the BizTalk application, and enter the BizTalk management computer, and the path to the deployment package</span></span>

<span data-ttu-id="9a720-110">使用 Visual Studio Team Services，你可以自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到不同的 BizTalk 环境的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a720-110">Using Visual Studio Team Services, you can automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications to different BizTalk environments.</span></span> 

<span data-ttu-id="9a720-111">通常情况下，有所涉及的两个角色：</span><span class="sxs-lookup"><span data-stu-id="9a720-111">Typically, there are two roles involved:</span></span>

- <span data-ttu-id="9a720-112">BizTalk 开发人员创建应用程序，并本地生成。</span><span class="sxs-lookup"><span data-stu-id="9a720-112">BizTalk developer creates the application, and builds it locally.</span></span> <span data-ttu-id="9a720-113">然后，检查应用程序置于 Git 或 Team Foundation 版本控制。</span><span class="sxs-lookup"><span data-stu-id="9a720-113">Then, checks the application into Git or Team Foundation Version Control.</span></span>
- <span data-ttu-id="9a720-114">VSTS 管理员创建的生成和发布的定义，并将部署到不同的环境 （开发人员、 UAT、 生产） 到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a720-114">VSTS admin creates the build and release definitions, and deploys to the BizTalk application to different environments (Dev, UAT, Production).</span></span>

<span data-ttu-id="9a720-115">如果你从未使用过 VSTS，本演练中可能具有挑战性。</span><span class="sxs-lookup"><span data-stu-id="9a720-115">If you’ve never used VSTS, this walkthrough may be challenging.</span></span> <span data-ttu-id="9a720-116">它需要一些 git，包括克隆，和将更改推送的知识。</span><span class="sxs-lookup"><span data-stu-id="9a720-116">It does require some understanding of git, including cloning, and pushing changes.</span></span> 

<span data-ttu-id="9a720-117">我们向您展示如何设置与 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并添加你要部署的第一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a720-117">We show you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span> <span data-ttu-id="9a720-118">我们建议你为参阅[VSTS 指南](https://docs.microsoft.com/vsts/user-guide/)，如 VSTS UI 更改。</span><span class="sxs-lookup"><span data-stu-id="9a720-118">We recommend you refer to the [VSTS guidance](https://docs.microsoft.com/vsts/user-guide/), as the VSTS UI changes.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="9a720-119">開始之前</span><span class="sxs-lookup"><span data-stu-id="9a720-119">Before you begin</span></span>

* <span data-ttu-id="9a720-120">已准备好你的 Visual Studio Team Services (VSTS) 帐户。</span><span class="sxs-lookup"><span data-stu-id="9a720-120">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="9a720-121">还没有？</span><span class="sxs-lookup"><span data-stu-id="9a720-121">Don't have one?</span></span> <span data-ttu-id="9a720-122">[注册 Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)。</span><span class="sxs-lookup"><span data-stu-id="9a720-122">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="9a720-123">如果你没有 BizTalk 计算机上安装了 VSTS 代理，然后使用最新的 VSTS 代理覆盖现有的代理。</span><span class="sxs-lookup"><span data-stu-id="9a720-123">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="9a720-124">你可能需要更新你[VSTS 服务，以符合新代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="9a720-124">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="9a720-125">功能包 1，自动部署 VSTS 完成其中一个上[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。</span><span class="sxs-lookup"><span data-stu-id="9a720-125">With Feature Pack 1, automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="9a720-126">请确保计算机具有 Visual Studio 和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]开发人员工具和安装 SDK。</span><span class="sxs-lookup"><span data-stu-id="9a720-126">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="9a720-127">请参阅[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)][硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="9a720-127">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>
* <span data-ttu-id="9a720-128">自动部署 VSTS 可以完成对功能包 2，使用[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups)。</span><span class="sxs-lookup"><span data-stu-id="9a720-128">With Feature Pack 2, automatic deployment with VSTS can be done using [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups).</span></span> <span data-ttu-id="9a720-129">使用部署组，可以部署到部署组中的多个 BizTalk 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="9a720-129">Using deployment groups, you can deploy your applications to multiple BizTalk Servers within the deployment group.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9a720-130">必要條件</span><span class="sxs-lookup"><span data-stu-id="9a720-130">Prerequisites</span></span>

* <span data-ttu-id="9a720-131">安装[功能包 2](https://aka.ms/bts2016fp2)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a720-131">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="9a720-132">某些体验和创建和使用 VSTS 中定义的知识。</span><span class="sxs-lookup"><span data-stu-id="9a720-132">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="9a720-133">如果你是新手 VSTS，这些可能是很好的资源︰</span><span class="sxs-lookup"><span data-stu-id="9a720-133">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="9a720-134">Visual Studio Team Services 概述</span><span class="sxs-lookup"><span data-stu-id="9a720-134">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="9a720-135">CI/CD 的新手</span><span class="sxs-lookup"><span data-stu-id="9a720-135">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a><span data-ttu-id="9a720-136">要开始</span><span class="sxs-lookup"><span data-stu-id="9a720-136">Get started</span></span>
[<span data-ttu-id="9a720-137">步骤1：添加应用程序项目和更新 .json 模板</span><span class="sxs-lookup"><span data-stu-id="9a720-137">Step 1: Add Application project & update .json template</span></span>](feature-pack-add-application-project.md)  

[<span data-ttu-id="9a720-138">步骤 2：创建 VSTS 令牌和安装生成代理 </span><span class="sxs-lookup"><span data-stu-id="9a720-138">Step 2: Create the VSTS token & install the build agent</span></span>](feature-pack-create-vsts-token.md)

[<span data-ttu-id="9a720-139">步骤 3： 创建构建并发布定义</span><span class="sxs-lookup"><span data-stu-id="9a720-139">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)

[<span data-ttu-id="9a720-140">配置环境的令牌和变量</span><span class="sxs-lookup"><span data-stu-id="9a720-140">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)