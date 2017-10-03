---
title: "使用 BizTalk Server 中的 Visual Studio Team Services 中配置自动部署 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 23d79eae3bd89a572a919cfeff800178f9163796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>使用 BizTalk Server 中的 Visual Studio Team Services 中配置自动部署
自动部署[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]使用 Visual Studio Team Services 应用程序。 

**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** ，[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]提供改进的自动部署和应用程序生命周期管理 (ALM) 体验。 

本部分说明如何设置与 VSTS [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，并添加你要部署的第一个应用程序。

## <a name="before-you-begin"></a>开始之前

* 已准备好你的 Visual Studio Team Services (VSTS) 帐户。 还没有？ [注册 Visual Studio Team Services](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)。
* 如果你没有 BizTalk 计算机上安装了 VSTS 代理，然后使用最新的 VSTS 代理覆盖现有的代理。 你可能需要更新你[VSTS 服务，以符合新代理](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)。
* 自动部署 VSTS 完成其中一个上[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]组中。 请确保计算机具有 Visual Studio 和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]开发人员工具和安装 SDK。 请参阅[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)][硬件和软件要求](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)。

## <a name="next-steps"></a>后续步骤
[为自动部署配置 VSTS](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)

[配置的 JSON 模板](../core/configure-the-json-template-for-automatic-deployment.md)

[配置环境的令牌和变量](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)

[添加到 VSTS BizTalk 应用程序](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)