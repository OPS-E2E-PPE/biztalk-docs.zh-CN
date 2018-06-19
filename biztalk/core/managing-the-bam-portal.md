---
title: 管理 BizTalk Server 中的 BAM 门户 |Microsoft 文档
Description: 安装和配置 BizTalk Server 中的 BAM 门户概述
ms.custom: ''
ms.date: 08/15/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a08aa85-3a45-4a8c-bdb5-5615ca097ce1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7908c9c7ce8e4b731e0b88569e3dc3fb228a1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262565"
---
# <a name="manage-the-bam-portal"></a><span data-ttu-id="634b1-103">管理 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="634b1-103">Manage the BAM portal</span></span>

## <a name="set-up-bam-portal"></a><span data-ttu-id="634b1-104">设置 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="634b1-104">Set up BAM portal</span></span>
<span data-ttu-id="634b1-105">管理员可以通过运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装过程来设置 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="634b1-105">Administrators set up the BAM portal by running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="634b1-106">使用 BizTalk Server 配置工具可以指定是否启用 BAM，还可以指定 Web Services 帐户、可查看门户的 Windows 组以及门户的宿主网站。</span><span class="sxs-lookup"><span data-stu-id="634b1-106">Use the BizTalk Server configuration tool to specify whether BAM is enabled, and to specify the Web service accounts, the Windows groups that can view portal, and the Web site that will host the portal.</span></span> <span data-ttu-id="634b1-107">如果设置 BAM 门户后有必要更新 BAM 门户配置，可以使用配置工具更新配置设置，例如，Portal Users 组、应用程序池帐户和管理 Web Services 用户。</span><span class="sxs-lookup"><span data-stu-id="634b1-107">If it becomes necessary to update the BAM portal configuration once you have set up the BAM portal, you use the configuration tool to update the configuration settings such as the portal users group, the Application Pool account, and the management Web services user.</span></span>  
  
 <span data-ttu-id="634b1-108">有关安装 BAM 门户的详细信息，请参阅[安装和配置多个计算机环境中的 BAM](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)。</span><span class="sxs-lookup"><span data-stu-id="634b1-108">For more information about installing the BAM portal, see [Install and Configure BAM in Multiple Computer Environments](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx).</span></span>  
  
 <span data-ttu-id="634b1-109">有关配置 BAM 门户的详细信息，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="634b1-109">For more information about configuring the BAM portal, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>
  
 <span data-ttu-id="634b1-110">BAM 门户有许多可自定义的设置，这些设置可通过修改 webconfig.xml 文件来访问。</span><span class="sxs-lookup"><span data-stu-id="634b1-110">The BAM portal has many customizable settings that are accessed by modifying the webconfig.xml file.</span></span> <span data-ttu-id="634b1-111">这些设置控制 BAM 门户的性能和操作。</span><span class="sxs-lookup"><span data-stu-id="634b1-111">These settings control the performance and operation of the BAM portal.</span></span> <span data-ttu-id="634b1-112">本部分中的剩余内容介绍如何自定义 BAM 门户配置。</span><span class="sxs-lookup"><span data-stu-id="634b1-112">This rest of this section describes how to customize your BAM portal configuration.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="634b1-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="634b1-113">Next steps</span></span> 
  
-   [<span data-ttu-id="634b1-114">自定义 BAM 门户配置</span><span class="sxs-lookup"><span data-stu-id="634b1-114">Customizing the BAM Portal Configuration</span></span>](../core/customizing-the-bam-portal-configuration.md)  
  
-   [<span data-ttu-id="634b1-115">如何在 NLB 群集上配置到工作 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="634b1-115">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a><span data-ttu-id="634b1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="634b1-116">See Also</span></span>  
 [<span data-ttu-id="634b1-117">管理 BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="634b1-117">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)