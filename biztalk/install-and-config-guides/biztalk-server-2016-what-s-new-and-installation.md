---
title: BizTalk Server 2016： 最新内容、 和安装 |Microsoft 文档
description: 什么是新，以及安装和升级到 BizTalk Server 2016 的简介
ms.custom: ''
ms.prod: biztalk-server
ms.date: 08/10/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 229043b3-b1a4-47e9-9c0e-1fba5ec5b417
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 212eee411c78bacd3d46ca66762fc8fc0f25fa05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300101"
---
# <a name="biztalk-server-2016-whats-new-and-installation"></a><span data-ttu-id="a00fa-103">BizTalk Server 2016：新增功能和安装</span><span class="sxs-lookup"><span data-stu-id="a00fa-103">BizTalk Server 2016: What's New, and Installation</span></span>

## <a name="get-started-with-biztalk-server-2016"></a><span data-ttu-id="a00fa-104">BizTalk Server 2016 入门</span><span class="sxs-lookup"><span data-stu-id="a00fa-104">Get started with BizTalk Server 2016</span></span>

[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]<span data-ttu-id="a00fa-105"> 是最新本地版本。</span><span class="sxs-lookup"><span data-stu-id="a00fa-105"> is the latest on-premises release.</span></span> <span data-ttu-id="a00fa-106">通过此新版本，可使用新的逻辑应用适配器实现与 Azure 的更紧密集成，还可使用文件适配器和 WCF-SQL 适配器连接到 Azure 资源。</span><span class="sxs-lookup"><span data-stu-id="a00fa-106">With this new version, you can expect closer integration with Azure using the new Logic Apps adapter, and connect to Azure resources using the File and WCF-SQL adapters.</span></span> 

<span data-ttu-id="a00fa-107">最大的变化之一是，支持 SQL Server 2016 AlwaysOn 可用性组 (AG)。</span><span class="sxs-lookup"><span data-stu-id="a00fa-107">One of the biggest changes is support for SQL Server 2016 AlwaysOn Availability Groups (AG).</span></span> <span data-ttu-id="a00fa-108">此支持包括在本地使用 BizTalk Server，以及使用 BizTalk Server Azure 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="a00fa-108">This support covers using BizTalk Server on-premises, and using BizTalk Server Azure virtual machines.</span></span> <span data-ttu-id="a00fa-109">使用 AlwaysOn，现在可通过使用 Azure 虚拟机获得高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="a00fa-109">With AlwaysOn, you can now have a highly-available solution using Azure virtual machines.</span></span>

<span data-ttu-id="a00fa-110">还更新了 SHA-2 支持、用于参与方的导入和导出绑定选项，改进了管理控制台等。</span><span class="sxs-lookup"><span data-stu-id="a00fa-110">There have also been updates to SHA-2 support, import and export binding options for parties, Administration console improvements, and much much more.</span></span> 

<span data-ttu-id="a00fa-111">在此 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 系列主题中，重点介绍 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] 的特定文档，包括更改的内容和安装。</span><span class="sxs-lookup"><span data-stu-id="a00fa-111">In this [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] set of topics, we focus on the specific documentation for [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], including what's changed, and the installation.</span></span> <span data-ttu-id="a00fa-112">因此，若要了解有关高可用性、监视 BIzTalk 环境等方面的信息，请转到 [BizTalk Server 核心文档](../core/biztalk-server-core-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="a00fa-112">So, if you want to read about high availability, monitoring your BIzTalk environment, and more, then go to the [BizTalk Server core documentation](../core/biztalk-server-core-documentation.md).</span></span> <span data-ttu-id="a00fa-113">若要配置 BizTalk Server，请转到[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a00fa-113">If you want to configure BizTalk Server, then go [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span> <span data-ttu-id="a00fa-114">若要了解新增功能并安装 [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，可通过访问以下链接开始：</span><span class="sxs-lookup"><span data-stu-id="a00fa-114">If you want to read about what's new, and install [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], then get started with the following links:</span></span>  

* [<span data-ttu-id="a00fa-115">新增功能</span><span class="sxs-lookup"><span data-stu-id="a00fa-115">What's New</span></span>](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
* [<span data-ttu-id="a00fa-116">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="a00fa-116">Hardware and Software Requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
* [<span data-ttu-id="a00fa-117">设置和安装必备组件</span><span class="sxs-lookup"><span data-stu-id="a00fa-117">Set up and install prerequisites</span></span>](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
* [<span data-ttu-id="a00fa-118">安装 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a00fa-118">Install BizTalk Server</span></span>](../install-and-config-guides/install-biztalk-server-2016.md)
* [<span data-ttu-id="a00fa-119">升级 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a00fa-119">Upgrade BizTalk Server</span></span>](../install-and-config-guides/upgrade-to-biztalk-server-2016.md)
  
## <a name="more-good-stuff"></a><span data-ttu-id="a00fa-120">更多有用内容</span><span class="sxs-lookup"><span data-stu-id="a00fa-120">More good stuff</span></span>
[<span data-ttu-id="a00fa-121">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a00fa-121">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)

[<span data-ttu-id="a00fa-122">在群集中配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="a00fa-122">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[<span data-ttu-id="a00fa-123">用于优化环境的配置后步骤</span><span class="sxs-lookup"><span data-stu-id="a00fa-123">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

[<span data-ttu-id="a00fa-124">导入和导出 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="a00fa-124">Import and Export BizTalk Server Configuration</span></span>](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)

[<span data-ttu-id="a00fa-125">合并 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a00fa-125">Consolidate the BizTalk Server Databases</span></span>](../install-and-config-guides/consolidate-the-biztalk-server-databases2.md)

[<span data-ttu-id="a00fa-126">使用配置框架</span><span class="sxs-lookup"><span data-stu-id="a00fa-126">Working with the Configuration Framework</span></span>](../install-and-config-guides/working-with-the-configuration-framework.md)

[<span data-ttu-id="a00fa-127">确保 BizTalk Server 部署的安全</span><span class="sxs-lookup"><span data-stu-id="a00fa-127">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)

[<span data-ttu-id="a00fa-128">卸载 BizTalk Server 并取消配置以将其删除</span><span class="sxs-lookup"><span data-stu-id="a00fa-128">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)