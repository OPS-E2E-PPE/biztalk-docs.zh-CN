---
title: 管理 BizTalk Server 中的 BAM 门户 |Microsoft Docs
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
ms.openlocfilehash: a0448e435e7adcc84d30f31ded54534c248e8e69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380158"
---
# <a name="manage-the-bam-portal"></a><span data-ttu-id="67cf5-103">管理 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="67cf5-103">Manage the BAM portal</span></span>

## <a name="set-up-bam-portal"></a><span data-ttu-id="67cf5-104">设置 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="67cf5-104">Set up BAM portal</span></span>
<span data-ttu-id="67cf5-105">管理员通过运行设置 BAM 门户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="67cf5-105">Administrators set up the BAM portal by running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="67cf5-106">若要指定是否启用了 BAM，并指定 Web 服务帐户，可以查看门户中，Windows 组和将承载在门户的网站，请使用 BizTalk Server 配置工具。</span><span class="sxs-lookup"><span data-stu-id="67cf5-106">Use the BizTalk Server configuration tool to specify whether BAM is enabled, and to specify the Web service accounts, the Windows groups that can view portal, and the Web site that will host the portal.</span></span> <span data-ttu-id="67cf5-107">如果有必要更新 BAM 门户配置设置 BAM 门户后，，使用配置工具来更新配置设置，例如，portal users 组、 应用程序池帐户和管理 Web services 用户。</span><span class="sxs-lookup"><span data-stu-id="67cf5-107">If it becomes necessary to update the BAM portal configuration once you have set up the BAM portal, you use the configuration tool to update the configuration settings such as the portal users group, the Application Pool account, and the management Web services user.</span></span>  
  
 <span data-ttu-id="67cf5-108">有关安装 BAM 门户的详细信息，请参阅[安装并在多计算机环境中配置 BAM](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx)。</span><span class="sxs-lookup"><span data-stu-id="67cf5-108">For more information about installing the BAM portal, see [Install and Configure BAM in Multiple Computer Environments](http://social.technet.microsoft.com/wiki/contents/articles/1888.install-and-configure-bam-business-activity-monitoring-in-a-multi-computer-environment.aspx).</span></span>  
  
 <span data-ttu-id="67cf5-109">有关配置 BAM 门户的详细信息，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="67cf5-109">For more information about configuring the BAM portal, see [Configure BizTalk Server](../install-and-config-guides/configure-biztalk-server.md).</span></span>
  
 <span data-ttu-id="67cf5-110">BAM 门户提供了通过修改 webconfig.xml 文件访问的许多可自定义设置。</span><span class="sxs-lookup"><span data-stu-id="67cf5-110">The BAM portal has many customizable settings that are accessed by modifying the webconfig.xml file.</span></span> <span data-ttu-id="67cf5-111">这些设置控制的性能和 BAM 门户的操作。</span><span class="sxs-lookup"><span data-stu-id="67cf5-111">These settings control the performance and operation of the BAM portal.</span></span> <span data-ttu-id="67cf5-112">本部分的余下部分介绍如何自定义 BAM 门户配置。</span><span class="sxs-lookup"><span data-stu-id="67cf5-112">This rest of this section describes how to customize your BAM portal configuration.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="67cf5-113">后续步骤</span><span class="sxs-lookup"><span data-stu-id="67cf5-113">Next steps</span></span> 
  
-   [<span data-ttu-id="67cf5-114">自定义 BAM 门户配置</span><span class="sxs-lookup"><span data-stu-id="67cf5-114">Customizing the BAM Portal Configuration</span></span>](../core/customizing-the-bam-portal-configuration.md)  
  
-   [<span data-ttu-id="67cf5-115">如何在 NLB 群集上配置 BAM 门户，转到工作</span><span class="sxs-lookup"><span data-stu-id="67cf5-115">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>](../core/how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster.md)  
  
## <a name="see-also"></a><span data-ttu-id="67cf5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="67cf5-116">See Also</span></span>  
 [<span data-ttu-id="67cf5-117">管理 BAM 动态基础结构</span><span class="sxs-lookup"><span data-stu-id="67cf5-117">Managing the BAM Dynamic Infrastructure</span></span>](../core/managing-the-bam-dynamic-infrastructure.md)