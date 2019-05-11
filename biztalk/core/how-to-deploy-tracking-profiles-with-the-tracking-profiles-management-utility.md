---
title: 如何部署跟踪配置文件与跟踪配置文件管理实用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking profiles, deploying
- deploying, tracking profiles
- bttdeploy.exe [BAM]
- managing [BAM], deploying tracking profiles
ms.assetid: b3023379-cae1-45fc-a773-2660d3e4abf1
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c4402c8e2951e069c908e431fac203c582c80be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385269"
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a><span data-ttu-id="e100b-102">如何部署跟踪配置文件与跟踪配置文件管理实用程序</span><span class="sxs-lookup"><span data-stu-id="e100b-102">How to Deploy Tracking Profiles with the Tracking Profiles Management Utility</span></span>
<span data-ttu-id="e100b-103">业务经理要求解决方案开发人员若要创建新的跟踪配置文件或修改现有更好地管理和监视你的组织的特定业务流程。</span><span class="sxs-lookup"><span data-stu-id="e100b-103">A business manager asks a solutions developer to create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span>  
  
 <span data-ttu-id="e100b-104">解决方案开发人员使用跟踪配置文件编辑器 (TPE) 来定义业务分析员所需的数据。</span><span class="sxs-lookup"><span data-stu-id="e100b-104">The solutions developer uses the Tracking Profile Editor (TPE) to define the data that the business analyst requires.</span></span>  
  
 <span data-ttu-id="e100b-105">解决方案开发人员创建或修改跟踪配置文件后，管理员使用 bttdeploy.exe 命令行实用程序来部署，以便所做的更改生效并收集的数据。</span><span class="sxs-lookup"><span data-stu-id="e100b-105">After a solutions developer creates or modifies the tracking profile, an administrator uses the bttdeploy.exe command line utility to deploy it so that the changes take affect and the data is collected.</span></span> <span data-ttu-id="e100b-106">解决方案开发人员可以将部署跟踪配置文件使用 TPE。</span><span class="sxs-lookup"><span data-stu-id="e100b-106">The solutions developer can deploy tracking profiles with the TPE.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e100b-107">您必须部署在部署跟踪配置文件之前，与跟踪配置文件相关联的程序集。</span><span class="sxs-lookup"><span data-stu-id="e100b-107">You must deploy the assemblies associated with the tracking profile before you deploy the tracking profile.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e100b-108">必须具有 BizTalk® 管理员权限才能使用此工具。</span><span class="sxs-lookup"><span data-stu-id="e100b-108">You must have BizTalk® Administrator privileges to use this tool.</span></span>  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a><span data-ttu-id="e100b-109">若要部署跟踪配置文件从命令行实用程序</span><span class="sxs-lookup"><span data-stu-id="e100b-109">To deploy the tracking profile from the command-line utility</span></span>  
  
1.  <span data-ttu-id="e100b-110">从命令提示符下，移动到的目录\<安装路径\>\Program Files\Microsoft BizTalk Server\<版本\>\Tracking\\。</span><span class="sxs-lookup"><span data-stu-id="e100b-110">From a command prompt, move to the directory \<installation path\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e100b-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="e100b-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="e100b-112">类型**bttdeploy.exe\<配置文件名称\>.btt**。</span><span class="sxs-lookup"><span data-stu-id="e100b-112">Type **bttdeploy.exe \<profile name\>.btt**.</span></span>  
  
3.  <span data-ttu-id="e100b-113">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="e100b-113">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e100b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="e100b-114">See Also</span></span>  
 <span data-ttu-id="e100b-115">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="e100b-115">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="e100b-116">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="e100b-116">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="e100b-117">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="e100b-117">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)