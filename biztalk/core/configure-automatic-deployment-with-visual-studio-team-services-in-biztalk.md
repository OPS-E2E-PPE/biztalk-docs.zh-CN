---
title: 使用 Visual Studio Team Services 中配置自动部署 |Microsoft Docs
description: 安装 BizTalk 功能包，可使用应用程序生命周期管理与 VSTS 结合使用来部署应用程序到不同的 BizTalk 环境
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
ms.openlocfilehash: 99d321e4f5987fe642b8a2dd4babc2c67093aad9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356446"
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="35cf9-103">使用 BizTalk Server 中的 Visual Studio Team Services 中配置自动部署</span><span class="sxs-lookup"><span data-stu-id="35cf9-103">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="35cf9-104">概述</span><span class="sxs-lookup"><span data-stu-id="35cf9-104">Overview</span></span>

<span data-ttu-id="35cf9-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]提供改进的自动部署和应用程序生命周期管理 (ALM) 体验。</span><span class="sxs-lookup"><span data-stu-id="35cf9-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="35cf9-106">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，我们改进了此功能：</span><span class="sxs-lookup"><span data-stu-id="35cf9-106">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, we've improved this feature:</span></span>

* <span data-ttu-id="35cf9-107">Visual Studio 中，设置**应用程序名称**的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="35cf9-107">Within Visual Studio, set the **Application Name** of your BizTalk application</span></span>
* <span data-ttu-id="35cf9-108">除了使用的是基于代理的部署，还可以使用[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)部署 BizTalk 应用程序向多个服务器</span><span class="sxs-lookup"><span data-stu-id="35cf9-108">In addition to using an agent-based deployment, you can also use [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) to deploy your BizTalk applications to multiple servers</span></span>
* <span data-ttu-id="35cf9-109">在发布任务中，可以安装 BizTalk 应用程序，并输入到部署包的 BizTalk 管理计算机和路径</span><span class="sxs-lookup"><span data-stu-id="35cf9-109">In the release task, you can install the BizTalk application, and enter the BizTalk management computer, and the path to the deployment package</span></span>

<span data-ttu-id="35cf9-110">使用 Visual Studio Team Services，您可以自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到不同的 BizTalk 环境的应用程序。</span><span class="sxs-lookup"><span data-stu-id="35cf9-110">Using Visual Studio Team Services, you can automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications to different BizTalk environments.</span></span> 

<span data-ttu-id="35cf9-111">通常情况下，有所涉及的两个角色：</span><span class="sxs-lookup"><span data-stu-id="35cf9-111">Typically, there are two roles involved:</span></span>

- <span data-ttu-id="35cf9-112">BizTalk 开发人员创建应用程序，并生成它本地。</span><span class="sxs-lookup"><span data-stu-id="35cf9-112">BizTalk developer creates the application, and builds it locally.</span></span> <span data-ttu-id="35cf9-113">然后，检查到 Git 或 Team Foundation 版本控制的应用程序。</span><span class="sxs-lookup"><span data-stu-id="35cf9-113">Then, checks the application into Git or Team Foundation Version Control.</span></span>
- <span data-ttu-id="35cf9-114">VSTS 管理员创建的生成和发布定义，并将部署到 BizTalk 应用程序到不同的环境 （开发人员、 用户验收测试、 生产）。</span><span class="sxs-lookup"><span data-stu-id="35cf9-114">VSTS admin creates the build and release definitions, and deploys to the BizTalk application to different environments (Dev, UAT, Production).</span></span>

<span data-ttu-id="35cf9-115">如果你从未使用过 VSTS，本演练中可能具有挑战性。</span><span class="sxs-lookup"><span data-stu-id="35cf9-115">If you’ve never used VSTS, this walkthrough may be challenging.</span></span> <span data-ttu-id="35cf9-116">它需要一些了解 git，包括克隆，和推送更改。</span><span class="sxs-lookup"><span data-stu-id="35cf9-116">It does require some understanding of git, including cloning, and pushing changes.</span></span> 

<span data-ttu-id="35cf9-117">我们介绍如何设置包含的 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并添加你要部署的第一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="35cf9-117">We show you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span> <span data-ttu-id="35cf9-118">我们建议您参考[VSTS 指南](https://docs.microsoft.com/vsts/user-guide/)，如 VSTS UI 更改。</span><span class="sxs-lookup"><span data-stu-id="35cf9-118">We recommend you refer to the [VSTS guidance](https://docs.microsoft.com/vsts/user-guide/), as the VSTS UI changes.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="35cf9-119">开始之前</span><span class="sxs-lookup"><span data-stu-id="35cf9-119">Before you begin</span></span>

* <span data-ttu-id="35cf9-120">具有 Visual Studio Team Services (VSTS) 帐户准备就绪。</span><span class="sxs-lookup"><span data-stu-id="35cf9-120">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="35cf9-121">还没有吗？</span><span class="sxs-lookup"><span data-stu-id="35cf9-121">Don't have one?</span></span> <span data-ttu-id="35cf9-122">[注册 Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)。</span><span class="sxs-lookup"><span data-stu-id="35cf9-122">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="35cf9-123">如果已在 BizTalk 计算机上安装了 VSTS 代理，则使用最新的 VSTS 代理覆盖现有的代理。</span><span class="sxs-lookup"><span data-stu-id="35cf9-123">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="35cf9-124">您可能必须更新您[VSTS 服务以便与新代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="35cf9-124">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="35cf9-125">Feature Pack 1，与使用 VSTS 自动部署在上一个完成[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。</span><span class="sxs-lookup"><span data-stu-id="35cf9-125">With Feature Pack 1, automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="35cf9-126">确保计算机具有 Visual Studio 和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]开发人员工具和 SDK 安装。</span><span class="sxs-lookup"><span data-stu-id="35cf9-126">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="35cf9-127">请参阅[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)][硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="35cf9-127">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>
* <span data-ttu-id="35cf9-128">功能包 2，使用 VSTS 自动部署后可以使用[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups)。</span><span class="sxs-lookup"><span data-stu-id="35cf9-128">With Feature Pack 2, automatic deployment with VSTS can be done using [deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups).</span></span> <span data-ttu-id="35cf9-129">使用部署组，可以部署到部署组内的多个 BizTalk 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="35cf9-129">Using deployment groups, you can deploy your applications to multiple BizTalk Servers within the deployment group.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35cf9-130">先决条件</span><span class="sxs-lookup"><span data-stu-id="35cf9-130">Prerequisites</span></span>

* <span data-ttu-id="35cf9-131">安装[功能包 2](https://aka.ms/bts2016fp2)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35cf9-131">Install [Feature Pack 2](https://aka.ms/bts2016fp2) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="35cf9-132">一些经验和知识并通过创建和使用 VSTS 中的定义。</span><span class="sxs-lookup"><span data-stu-id="35cf9-132">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="35cf9-133">如果你是新手 VSTS，这些可能是有用的资源：</span><span class="sxs-lookup"><span data-stu-id="35cf9-133">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="35cf9-134">Visual Studio Team Services 概述</span><span class="sxs-lookup"><span data-stu-id="35cf9-134">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="35cf9-135">适用于新手的 CI/CD</span><span class="sxs-lookup"><span data-stu-id="35cf9-135">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a><span data-ttu-id="35cf9-136">入门</span><span class="sxs-lookup"><span data-stu-id="35cf9-136">Get started</span></span>
[<span data-ttu-id="35cf9-137">步骤 1：添加应用程序项目和更新.json 模板</span><span class="sxs-lookup"><span data-stu-id="35cf9-137">Step 1: Add Application project & update .json template</span></span>](feature-pack-add-application-project.md)  

[<span data-ttu-id="35cf9-138">步骤 2：创建 VSTS 令牌和安装生成代理</span><span class="sxs-lookup"><span data-stu-id="35cf9-138">Step 2: Create the VSTS token & install the build agent</span></span>](feature-pack-create-vsts-token.md)

[<span data-ttu-id="35cf9-139">步骤 3：创建生成和发布定义</span><span class="sxs-lookup"><span data-stu-id="35cf9-139">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)

[<span data-ttu-id="35cf9-140">配置环境令牌和变量</span><span class="sxs-lookup"><span data-stu-id="35cf9-140">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)