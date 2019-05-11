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
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>使用 BizTalk Server 中的 Visual Studio Team Services 中配置自动部署

## <a name="overview"></a>概述

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]提供改进的自动部署和应用程序生命周期管理 (ALM) 体验。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 2**，我们改进了此功能：

* Visual Studio 中，设置**应用程序名称**的 BizTalk 应用程序
* 除了使用的是基于代理的部署，还可以使用[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)部署 BizTalk 应用程序向多个服务器
* 在发布任务中，可以安装 BizTalk 应用程序，并输入到部署包的 BizTalk 管理计算机和路径

使用 Visual Studio Team Services，您可以自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到不同的 BizTalk 环境的应用程序。 

通常情况下，有所涉及的两个角色：

- BizTalk 开发人员创建应用程序，并生成它本地。 然后，检查到 Git 或 Team Foundation 版本控制的应用程序。
- VSTS 管理员创建的生成和发布定义，并将部署到 BizTalk 应用程序到不同的环境 （开发人员、 用户验收测试、 生产）。

如果你从未使用过 VSTS，本演练中可能具有挑战性。 它需要一些了解 git，包括克隆，和推送更改。 

我们介绍如何设置包含的 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并添加你要部署的第一个应用程序。 我们建议您参考[VSTS 指南](https://docs.microsoft.com/vsts/user-guide/)，如 VSTS UI 更改。 

## <a name="before-you-begin"></a>开始之前

* 具有 Visual Studio Team Services (VSTS) 帐户准备就绪。 还没有吗？ [注册 Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)。
* 如果已在 BizTalk 计算机上安装了 VSTS 代理，则使用最新的 VSTS 代理覆盖现有的代理。 您可能必须更新您[VSTS 服务以便与新代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)。
* Feature Pack 1，与使用 VSTS 自动部署在上一个完成[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。 确保计算机具有 Visual Studio 和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]开发人员工具和 SDK 安装。 请参阅[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)][硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。
* 功能包 2，使用 VSTS 自动部署后可以使用[部署组](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups)。 使用部署组，可以部署到部署组内的多个 BizTalk 服务器应用程序。

## <a name="prerequisites"></a>先决条件

* 安装[功能包 2](https://aka.ms/bts2016fp2)上你 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 一些经验和知识并通过创建和使用 VSTS 中的定义。 如果你是新手 VSTS，这些可能是有用的资源： 

  [Visual Studio Team Services 概述](https://www.visualstudio.com/docs/overview)  
  [适用于新手的 CI/CD](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a>入门
[步骤 1：添加应用程序项目和更新.json 模板](feature-pack-add-application-project.md)  

[步骤 2：创建 VSTS 令牌和安装生成代理](feature-pack-create-vsts-token.md)

[步骤 3：创建生成和发布定义](feature-pack-add-build-release-definitions.md)

[配置环境令牌和变量](configure-environmental-tokens-and-variables-for-automatic-deployment.md)