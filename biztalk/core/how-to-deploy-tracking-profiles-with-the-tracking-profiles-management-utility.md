---
title: 如何部署跟踪配置文件使用跟踪配置文件管理实用程序 |Microsoft 文档
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
ms.openlocfilehash: 2dde3f351c583be9037127c060d02c98d12b2fcb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970115"
---
# <a name="how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility"></a><span data-ttu-id="d5371-102">如何使用跟踪配置文件管理实用程序部署跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="d5371-102">How to Deploy Tracking Profiles with the Tracking Profiles Management Utility</span></span>
<span data-ttu-id="d5371-103">业务经理要求解决方案开发人员创建一个新的跟踪配置文件或修改现有跟踪配置文件以便更好地管理和监视组织的特定业务流程。</span><span class="sxs-lookup"><span data-stu-id="d5371-103">A business manager asks a solutions developer to create a new tracking profile or modify an existing one to better manage and monitor a specific business process for your organization.</span></span>  
  
 <span data-ttu-id="d5371-104">解决方案开发人员使用跟踪配置文件编辑器 (TPE) 定义业务分析员需要的数据。</span><span class="sxs-lookup"><span data-stu-id="d5371-104">The solutions developer uses the Tracking Profile Editor (TPE) to define the data that the business analyst requires.</span></span>  
  
 <span data-ttu-id="d5371-105">在解决方案开发人员创建或修改跟踪配置文件后，管理员使用 bttdeploy.exe 命令行实用程序对其进行部署，以便所做的更改能够生效并收集数据。</span><span class="sxs-lookup"><span data-stu-id="d5371-105">After a solutions developer creates or modifies the tracking profile, an administrator uses the bttdeploy.exe command line utility to deploy it so that the changes take affect and the data is collected.</span></span> <span data-ttu-id="d5371-106">解决方案开发人员可以使用 TPE 部署跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="d5371-106">The solutions developer can deploy tracking profiles with the TPE.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5371-107">在部署跟踪配置文件前，必须部署与跟踪配置文件相关联的程序集。</span><span class="sxs-lookup"><span data-stu-id="d5371-107">You must deploy the assemblies associated with the tracking profile before you deploy the tracking profile.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d5371-108">你必须拥有 BizTalk® 管理员特权才能使用此工具。</span><span class="sxs-lookup"><span data-stu-id="d5371-108">You must have BizTalk® Administrator privileges to use this tool.</span></span>  
  
### <a name="to-deploy-the-tracking-profile-from-the-command-line-utility"></a><span data-ttu-id="d5371-109">通过命令行实用工具部署跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="d5371-109">To deploy the tracking profile from the command-line utility</span></span>  
  
1.  <span data-ttu-id="d5371-110">从命令提示符处，将移动到目录\<安装路径\>files\microsoft BizTalk Server\<版本\>\Tracking\\。</span><span class="sxs-lookup"><span data-stu-id="d5371-110">From a command prompt, move to the directory \<installation path\>\Program Files\Microsoft BizTalk Server \<version\>\Tracking\\.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5371-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d5371-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
2.  <span data-ttu-id="d5371-112">类型**bttdeploy.exe\<配置文件名称\>.btt**。</span><span class="sxs-lookup"><span data-stu-id="d5371-112">Type **bttdeploy.exe \<profile name\>.btt**.</span></span>  
  
3.  <span data-ttu-id="d5371-113">按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d5371-113">Press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5371-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5371-114">See Also</span></span>  
 <span data-ttu-id="d5371-115">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="d5371-115">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="d5371-116">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="d5371-116">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="d5371-117">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="d5371-117">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)