---
title: BizTalk Server 2016:最新内容、 和安装 |Microsoft Docs
description: 什么是新，以及如何安装和升级到 BizTalk Server 2016 简介
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
ms.openlocfilehash: 4d877ba2b81a536e8c1818c243cf0eb82e5f2c8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266497"
---
# <a name="biztalk-server-2016-whats-new-and-installation"></a><span data-ttu-id="198d0-103">BizTalk Server 2016:最新内容、 和安装</span><span class="sxs-lookup"><span data-stu-id="198d0-103">BizTalk Server 2016: What's New, and Installation</span></span>

## <a name="get-started-with-biztalk-server-2016"></a><span data-ttu-id="198d0-104">开始使用 BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="198d0-104">Get started with BizTalk Server 2016</span></span>

[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] <span data-ttu-id="198d0-105">是最新的本地版本。</span><span class="sxs-lookup"><span data-stu-id="198d0-105">is the latest on-premises release.</span></span> <span data-ttu-id="198d0-106">使用此新版本，可以与 Azure 中使用新的逻辑应用适配器期望更紧密集成，并连接到 Azure 资源使用的文件和 WCF SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="198d0-106">With this new version, you can expect closer integration with Azure using the new Logic Apps adapter, and connect to Azure resources using the File and WCF-SQL adapters.</span></span> 

<span data-ttu-id="198d0-107">最大的变化之一是支持的 SQL Server 2016 AlwaysOn 可用性组 (AG)。</span><span class="sxs-lookup"><span data-stu-id="198d0-107">One of the biggest changes is support for SQL Server 2016 AlwaysOn Availability Groups (AG).</span></span> <span data-ttu-id="198d0-108">此支持包括使用 BizTalk Server 的本地，并使用 BizTalk Server Azure 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="198d0-108">This support covers using BizTalk Server on-premises, and using BizTalk Server Azure virtual machines.</span></span> <span data-ttu-id="198d0-109">使用 AlwaysOn，您现在可以使用 Azure 虚拟机高度可用的解决方案。</span><span class="sxs-lookup"><span data-stu-id="198d0-109">With AlwaysOn, you can now have a highly-available solution using Azure virtual machines.</span></span>

<span data-ttu-id="198d0-110">此外需要进行更新的 sha-2 支持、 导入和导出的绑定选项参与方，改进了管理控制台，和很多得多。</span><span class="sxs-lookup"><span data-stu-id="198d0-110">There have also been updates to SHA-2 support, import and export binding options for parties, Administration console improvements, and much much more.</span></span> 

<span data-ttu-id="198d0-111">在此[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]组的主题，我们关注的特定文档[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，包括更改的内容和安装。</span><span class="sxs-lookup"><span data-stu-id="198d0-111">In this [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] set of topics, we focus on the specific documentation for [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], including what's changed, and the installation.</span></span> <span data-ttu-id="198d0-112">因此，如果你想要深入了解高可用性，监视 BIzTalk 环境和的详细信息，然后转到[BizTalk Server 核心文档](../core/biztalk-server-core-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="198d0-112">So, if you want to read about high availability, monitoring your BIzTalk environment, and more, then go to the [BizTalk Server core documentation](../core/biztalk-server-core-documentation.md).</span></span> <span data-ttu-id="198d0-113">如果你想要配置 BizTalk Server，然后转[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="198d0-113">If you want to configure BizTalk Server, then go [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span> <span data-ttu-id="198d0-114">如果想要阅读有关哪些新增功能，并且安装[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，然后开始使用以下链接：</span><span class="sxs-lookup"><span data-stu-id="198d0-114">If you want to read about what's new, and install [!INCLUDE[bts2016_md](../includes/bts2016-md.md)], then get started with the following links:</span></span>  

* [<span data-ttu-id="198d0-115">新增功能</span><span class="sxs-lookup"><span data-stu-id="198d0-115">What's New</span></span>](../install-and-config-guides/what-s-new-in-biztalk-server-2016.md)  
* [<span data-ttu-id="198d0-116">硬件和软件要求</span><span class="sxs-lookup"><span data-stu-id="198d0-116">Hardware and Software Requirements</span></span>](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)  
* [<span data-ttu-id="198d0-117">设置和安装必备组件</span><span class="sxs-lookup"><span data-stu-id="198d0-117">Set up and install prerequisites</span></span>](../install-and-config-guides/set-up-and-install-prerequisites-for-biztalk-server-2016.md)  
* [<span data-ttu-id="198d0-118">安装 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="198d0-118">Install BizTalk Server</span></span>](../install-and-config-guides/install-biztalk-server-2016.md)
* [<span data-ttu-id="198d0-119">升级 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="198d0-119">Upgrade BizTalk Server</span></span>](../install-and-config-guides/upgrade-to-biztalk-server-2016.md)
  
## <a name="more-good-stuff"></a><span data-ttu-id="198d0-120">更多有用资料</span><span class="sxs-lookup"><span data-stu-id="198d0-120">More good stuff</span></span>
[<span data-ttu-id="198d0-121">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="198d0-121">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)

[<span data-ttu-id="198d0-122">在群集中配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="198d0-122">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[<span data-ttu-id="198d0-123">用于优化环境的配置后步骤</span><span class="sxs-lookup"><span data-stu-id="198d0-123">Post-configuration steps to optimize your environment</span></span>](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

[<span data-ttu-id="198d0-124">导入和导出 BizTalk Server 配置</span><span class="sxs-lookup"><span data-stu-id="198d0-124">Import and Export BizTalk Server Configuration</span></span>](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)

[<span data-ttu-id="198d0-125">合并 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="198d0-125">Consolidate the BizTalk Server Databases</span></span>](../install-and-config-guides/consolidate-the-biztalk-server-databases2.md)

[<span data-ttu-id="198d0-126">使用配置框架</span><span class="sxs-lookup"><span data-stu-id="198d0-126">Working with the Configuration Framework</span></span>](../install-and-config-guides/working-with-the-configuration-framework.md)

[<span data-ttu-id="198d0-127">保护 BizTalk Server 部署</span><span class="sxs-lookup"><span data-stu-id="198d0-127">Securing Your BizTalk Server Deployment</span></span>](../install-and-config-guides/securing-your-biztalk-server-deployment.md)

[<span data-ttu-id="198d0-128">卸载并取消配置 BizTalk Server 将其删除</span><span class="sxs-lookup"><span data-stu-id="198d0-128">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)