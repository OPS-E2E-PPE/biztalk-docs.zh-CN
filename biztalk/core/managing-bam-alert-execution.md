---
title: 管理 BAM 警报执行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], executing alerts
- Notification Services, configuration files
- BAM Management utility
- alerts, executing
ms.assetid: 44bb738e-fa2c-4b32-9e8d-e756d6c3778e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d8dca3f99480b6875253eb6aca102977935160b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021979"
---
# <a name="managing-bam-alert-execution"></a><span data-ttu-id="c1826-102">管理 BAM 警报执行</span><span class="sxs-lookup"><span data-stu-id="c1826-102">Managing BAM Alert Execution</span></span>
<span data-ttu-id="c1826-103">可以通过以下三种渠道修改 BAM 警报执行，即 BAM 门户、BAM 管理实用程序和 ProcessBamNSFiles.vbs 脚本。</span><span class="sxs-lookup"><span data-stu-id="c1826-103">BAM Alert execution can be modified through three avenues, The BAM Portal, the BAM management utility, and the ProcessBamNSFiles.vbs script.</span></span>  
  
## <a name="bam-portal"></a><span data-ttu-id="c1826-104">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="c1826-104">BAM Portal</span></span>  
 <span data-ttu-id="c1826-105">知识工作者和管理员可以使用 BAM 门户的警报管理器来修改传送警报的方式。</span><span class="sxs-lookup"><span data-stu-id="c1826-105">Knowledge workers and administrators can modify the manner in which alerts are delivered by using the Alert Manager in the BAM portal.</span></span> <span data-ttu-id="c1826-106">在 BAM 门户中，可以启用或禁用警报，还可以修改阈值级别、传送位置以及影响警报执行的其他参数。</span><span class="sxs-lookup"><span data-stu-id="c1826-106">From the BAM portal, the Alert can be enabled or disabled, threshold levels can be modified, delivery locations can be modified, as well as other parameters the affect the execution of the alert.</span></span>  
  
 <span data-ttu-id="c1826-107">有关修改警报的详细信息，请参阅[BAM 门户页上的警报管理器](../core/alert-manager-on-the-bam-portal-page.md)并[BAM 门户中的警报](../core/alerts-in-the-bam-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="c1826-107">For more information on modifying alerts, see [Alert Manager on the BAM Portal Page](../core/alert-manager-on-the-bam-portal-page.md) and [Alerts in the BAM Portal](../core/alerts-in-the-bam-portal.md).</span></span>  
  
### <a name="bam-management-utility"></a><span data-ttu-id="c1826-108">BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="c1826-108">BAM Management Utility</span></span>  
 <span data-ttu-id="c1826-109">管理员可以使用 BAM 管理实用程序来启用、禁用和删除警报。</span><span class="sxs-lookup"><span data-stu-id="c1826-109">Administrators can use the BAM Management utility to enable, disable, and remove alerts.</span></span>  
  
 <span data-ttu-id="c1826-110">有关使用 BAM 管理实用程序管理警报的信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="c1826-110">For information on using the BAM Management Utility to mange alerts, the following topics:</span></span>  
  
-   [<span data-ttu-id="c1826-111">如何启用警报</span><span class="sxs-lookup"><span data-stu-id="c1826-111">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md) 
  
-   [<span data-ttu-id="c1826-112">如何禁用警报</span><span class="sxs-lookup"><span data-stu-id="c1826-112">How to Disable Alerts</span></span>](../core/how-to-disable-alerts.md)  
  
-   [<span data-ttu-id="c1826-113">如何删除 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="c1826-113">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a><span data-ttu-id="c1826-114">修改 Notification Services 配置文件</span><span class="sxs-lookup"><span data-stu-id="c1826-114">Modifying Notification Services Configuration Files</span></span>  
 <span data-ttu-id="c1826-115">管理员可使用 ProcessBamNSFiles.vbs 脚本更改 Notification Services 传送警报的方式。</span><span class="sxs-lookup"><span data-stu-id="c1826-115">Administrators can use the ProcessBamNSFiles.vbs script to change the manner in which the Notification Services delivers alerts.</span></span> <span data-ttu-id="c1826-116">Notification Services 的详细信息应用程序定义文件 (ADF)，请参阅[ http://go.microsoft.com/fwlink/?LinkId=127016 ](http://go.microsoft.com/fwlink/?LinkId=127016)。</span><span class="sxs-lookup"><span data-stu-id="c1826-116">For more information the Application Definition File (ADF) for Notification Services, see [http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016).</span></span>  
  
 <span data-ttu-id="c1826-117">若要修改与 BAM 相关的 ADF，可以按照以下常规步骤执行操作：</span><span class="sxs-lookup"><span data-stu-id="c1826-117">To modify the ADF associated with BAM you can follow these general steps:</span></span>  
  
1. <span data-ttu-id="c1826-118">运行脚本，以获得当前的配置文件和 ADF 文件。</span><span class="sxs-lookup"><span data-stu-id="c1826-118">Run the script to obtain the current configuration and ADF files.</span></span>  
  
2. <span data-ttu-id="c1826-119">修改这些文件。</span><span class="sxs-lookup"><span data-stu-id="c1826-119">Modify the files.</span></span>  
  
3. <span data-ttu-id="c1826-120">运行脚本以应用更改。</span><span class="sxs-lookup"><span data-stu-id="c1826-120">Run the script to apply the changes.</span></span>  
  
   <span data-ttu-id="c1826-121">有关 ProcessBamNSFiles.vbs 脚本的详细信息，请参阅[BAM 通知服务配置文件的命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="c1826-121">For more information on the ProcessBamNSFiles.vbs script, see [BAM Command-Line Script for Notification Services Configuration Files](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1826-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1826-122">See Also</span></span>  
 <span data-ttu-id="c1826-123">[管理 BAM 门户](../core/managing-the-bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="c1826-123">[Managing the BAM Portal](../core/managing-the-bam-portal.md) </span></span>  
 <span data-ttu-id="c1826-124">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="c1826-124">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="c1826-125">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="c1826-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)