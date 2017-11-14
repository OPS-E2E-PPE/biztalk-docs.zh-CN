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
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>使用 BizTalk Server 中的 Visual Studio Team Services 中配置自动部署

## <a name="overview"></a>概述

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]提供改进的自动部署和应用程序生命周期管理 (ALM) 体验。 

使用 Visual Studio Team Services，你可以自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到不同的 BizTalk 环境的应用程序。 

通常情况下，有所涉及的两个角色：

- BizTalk 开发人员创建应用程序，并本地生成。 然后，检查应用程序置于 Git 或 Team Foundation 版本控制。
- VSTS 管理员创建的生成和发布的定义，并将部署到不同的环境 （开发人员、 UAT、 生产） 到 BizTalk 应用程序。

如果你从未使用过 VSTS，本演练中可能具有挑战性。 它需要一些 git，包括克隆，和将更改推送的知识。 

我们向您展示如何设置与 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并添加你要部署的第一个应用程序。 我们建议你为参阅[VSTS 指南](https://docs.microsoft.com/vsts/user-guide/)，如 VSTS UI 更改。 

## <a name="before-you-begin"></a>开始之前

* 已准备好你的 Visual Studio Team Services (VSTS) 帐户。 还没有？ [注册 Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)。
* 如果你没有 BizTalk 计算机上安装了 VSTS 代理，然后使用最新的 VSTS 代理覆盖现有的代理。 你可能需要更新你[VSTS 服务，以符合新代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)。
* 自动部署 VSTS 完成其中一个上[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。 请确保计算机具有 Visual Studio 和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]开发人员工具和安装 SDK。 请参阅[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)][硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。

## <a name="prerequisites"></a>先决条件

* 安装[功能包 1](https://www.microsoft.com/download/details.aspx?id=55100)上你[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 某些体验和创建和使用 VSTS 中定义的知识。 如果你是新手 VSTS，这些可能是很好的资源： 

  [Visual Studio Team Services 概述](https://www.visualstudio.com/docs/overview)  
  [CI/CD 的新手](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a>要开始
[第 1 步： 添加应用程序项目与更新.json 模板](feature-pack-add-application-project.md)  

[第 2 步： 创建 VSTS 令牌与安装的生成代理](feature-pack-create-vsts-token.md)

[步骤 3： 创建构建并发布定义](feature-pack-add-build-release-definitions.md)

[配置环境的令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)