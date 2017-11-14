---
title: "使用 Visual Studio Team Services 中配置自动部署 |Microsoft 文档"
description: "安装 BizTalk 功能包，可使用 VSTS 应用程序生命周期管理部署到不同的 BizTalk 环境应用程序"
ms.custom: 
ms.date: 11/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04a7d2b2430a5dc57403fc179fa1c1859d3a82b3
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a><span data-ttu-id="565cb-103">使用 BizTalk Server 中的 Visual Studio Team Services 中配置自动部署</span><span class="sxs-lookup"><span data-stu-id="565cb-103">Configure automatic deployment with Visual Studio Team Services in BizTalk Server</span></span>

## <a name="overview"></a><span data-ttu-id="565cb-104">概述</span><span class="sxs-lookup"><span data-stu-id="565cb-104">Overview</span></span>

<span data-ttu-id="565cb-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]提供改进的自动部署和应用程序生命周期管理 (ALM) 体验。</span><span class="sxs-lookup"><span data-stu-id="565cb-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]**, [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] provides an improved automatic deployment and application lifecycle management (ALM) experience.</span></span> 

<span data-ttu-id="565cb-106">使用 Visual Studio Team Services，你可以自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到不同的 BizTalk 环境的应用程序。</span><span class="sxs-lookup"><span data-stu-id="565cb-106">Using Visual Studio Team Services, you can automatically deploy [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] applications to different BizTalk environments.</span></span> 

<span data-ttu-id="565cb-107">通常情况下，有所涉及的两个角色：</span><span class="sxs-lookup"><span data-stu-id="565cb-107">Typically, there are two roles involved:</span></span>

- <span data-ttu-id="565cb-108">BizTalk 开发人员创建应用程序，并本地生成。</span><span class="sxs-lookup"><span data-stu-id="565cb-108">BizTalk developer creates the application, and builds it locally.</span></span> <span data-ttu-id="565cb-109">然后，检查应用程序置于 Git 或 Team Foundation 版本控制。</span><span class="sxs-lookup"><span data-stu-id="565cb-109">Then, checks the application into Git or Team Foundation Version Control.</span></span>
- <span data-ttu-id="565cb-110">VSTS 管理员创建的生成和发布的定义，并将部署到不同的环境 （开发人员、 UAT、 生产） 到 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="565cb-110">VSTS admin creates the build and release definitions, and deploys to the BizTalk application to different environments (Dev, UAT, Production).</span></span>

<span data-ttu-id="565cb-111">如果你从未使用过 VSTS，本演练中可能具有挑战性。</span><span class="sxs-lookup"><span data-stu-id="565cb-111">If you’ve never used VSTS, this walkthrough may be challenging.</span></span> <span data-ttu-id="565cb-112">它需要一些 git，包括克隆，和将更改推送的知识。</span><span class="sxs-lookup"><span data-stu-id="565cb-112">It does require some understanding of git, including cloning, and pushing changes.</span></span> 

<span data-ttu-id="565cb-113">我们向您展示如何设置与 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并添加你要部署的第一个应用程序。</span><span class="sxs-lookup"><span data-stu-id="565cb-113">We show you how to setup VSTS with [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], and add your first application to deploy.</span></span> <span data-ttu-id="565cb-114">我们建议你为参阅[VSTS 指南](https://docs.microsoft.com/vsts/user-guide/)，如 VSTS UI 更改。</span><span class="sxs-lookup"><span data-stu-id="565cb-114">We recommend you refer to the [VSTS guidance](https://docs.microsoft.com/vsts/user-guide/), as the VSTS UI changes.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="565cb-115">开始之前</span><span class="sxs-lookup"><span data-stu-id="565cb-115">Before you begin</span></span>

* <span data-ttu-id="565cb-116">已准备好你的 Visual Studio Team Services (VSTS) 帐户。</span><span class="sxs-lookup"><span data-stu-id="565cb-116">Have your Visual Studio Team Services (VSTS) account ready.</span></span> <span data-ttu-id="565cb-117">还没有？</span><span class="sxs-lookup"><span data-stu-id="565cb-117">Don't have one?</span></span> <span data-ttu-id="565cb-118">[注册 Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)。</span><span class="sxs-lookup"><span data-stu-id="565cb-118">[Sign up for Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services).</span></span>
* <span data-ttu-id="565cb-119">如果你没有 BizTalk 计算机上安装了 VSTS 代理，然后使用最新的 VSTS 代理覆盖现有的代理。</span><span class="sxs-lookup"><span data-stu-id="565cb-119">If you already have a VSTS Agent installed on your BizTalk computer, then the existing agent is overwritten with the latest VSTS Agent.</span></span> <span data-ttu-id="565cb-120">你可能需要更新你[VSTS 服务，以符合新代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)。</span><span class="sxs-lookup"><span data-stu-id="565cb-120">You may have to update your [VSTS service to align with the new agent](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent).</span></span>
* <span data-ttu-id="565cb-121">自动部署 VSTS 完成其中一个上[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。</span><span class="sxs-lookup"><span data-stu-id="565cb-121">Automatic deployment with VSTS is done on one [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in the group.</span></span> <span data-ttu-id="565cb-122">请确保计算机具有 Visual Studio 和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]开发人员工具和安装 SDK。</span><span class="sxs-lookup"><span data-stu-id="565cb-122">Be sure the computer has Visual Studio and the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] Developer Tools and SDK installed.</span></span> <span data-ttu-id="565cb-123">请参阅[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)][硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。</span><span class="sxs-lookup"><span data-stu-id="565cb-123">See the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [hardware and software requirements](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="565cb-124">先决条件</span><span class="sxs-lookup"><span data-stu-id="565cb-124">Prerequisites</span></span>

* <span data-ttu-id="565cb-125">安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="565cb-125">Install [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100) on your [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]</span></span>
* <span data-ttu-id="565cb-126">某些体验和创建和使用 VSTS 中定义的知识。</span><span class="sxs-lookup"><span data-stu-id="565cb-126">Some experience and knowledge with creating and working with definitions in VSTS.</span></span> <span data-ttu-id="565cb-127">如果你是新手 VSTS，这些可能是很好的资源：</span><span class="sxs-lookup"><span data-stu-id="565cb-127">If you're brand new to VSTS, these may be good resources:</span></span> 

  [<span data-ttu-id="565cb-128">Visual Studio Team Services 概述</span><span class="sxs-lookup"><span data-stu-id="565cb-128">Visual Studio Team Services overview</span></span>](https://www.visualstudio.com/docs/overview)  
  [<span data-ttu-id="565cb-129">CI/CD 的新手</span><span class="sxs-lookup"><span data-stu-id="565cb-129">CI/CD for newbies</span></span>](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a><span data-ttu-id="565cb-130">要开始</span><span class="sxs-lookup"><span data-stu-id="565cb-130">Get started</span></span>
[<span data-ttu-id="565cb-131">第 1 步： 添加应用程序项目与更新.json 模板</span><span class="sxs-lookup"><span data-stu-id="565cb-131">Step 1: Add Application project & update .json template</span></span>](feature-pack-add-application-project.md)  

[<span data-ttu-id="565cb-132">第 2 步： 创建 VSTS 令牌与安装的生成代理</span><span class="sxs-lookup"><span data-stu-id="565cb-132">Step 2: Create the VSTS token & install the build agent</span></span>](feature-pack-create-vsts-token.md)

[<span data-ttu-id="565cb-133">步骤 3： 创建构建并发布定义</span><span class="sxs-lookup"><span data-stu-id="565cb-133">Step 3: Create the build and release definitions</span></span>](feature-pack-add-build-release-definitions.md)

[<span data-ttu-id="565cb-134">配置环境的令牌和变量</span><span class="sxs-lookup"><span data-stu-id="565cb-134">Configure environmental tokens and variables</span></span>](configure-environmental-tokens-and-variables-for-automatic-deployment.md)