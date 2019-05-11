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
ms.openlocfilehash: 485842a1cb2bfe315c6b8570409eb9beeb9dac41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65327473"
---
# <a name="managing-bam-alert-execution"></a><span data-ttu-id="94b69-102">管理 BAM 警报执行</span><span class="sxs-lookup"><span data-stu-id="94b69-102">Managing BAM Alert Execution</span></span>
<span data-ttu-id="94b69-103">可以通过以下三种渠道，即 BAM 门户、 BAM 管理实用程序和 ProcessBamNSFiles.vbs 脚本修改 BAM 警报执行。</span><span class="sxs-lookup"><span data-stu-id="94b69-103">BAM Alert execution can be modified through three avenues, The BAM Portal, the BAM management utility, and the ProcessBamNSFiles.vbs script.</span></span>  
  
## <a name="bam-portal"></a><span data-ttu-id="94b69-104">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="94b69-104">BAM Portal</span></span>  
 <span data-ttu-id="94b69-105">知识工作者和管理员可以修改 BAM 门户中使用警报管理器传送警报的方式。</span><span class="sxs-lookup"><span data-stu-id="94b69-105">Knowledge workers and administrators can modify the manner in which alerts are delivered by using the Alert Manager in the BAM portal.</span></span> <span data-ttu-id="94b69-106">在 BAM 门户中，可以启用或禁用警报，可以修改阈值级别、 传送位置可以修改，以及其他参数会影响警报执行。</span><span class="sxs-lookup"><span data-stu-id="94b69-106">From the BAM portal, the Alert can be enabled or disabled, threshold levels can be modified, delivery locations can be modified, as well as other parameters the affect the execution of the alert.</span></span>  
  
 <span data-ttu-id="94b69-107">有关修改警报的详细信息，请参阅[BAM 门户页上的警报管理器](../core/alert-manager-on-the-bam-portal-page.md)并[BAM 门户中的警报](../core/alerts-in-the-bam-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="94b69-107">For more information on modifying alerts, see [Alert Manager on the BAM Portal Page](../core/alert-manager-on-the-bam-portal-page.md) and [Alerts in the BAM Portal](../core/alerts-in-the-bam-portal.md).</span></span>  
  
### <a name="bam-management-utility"></a><span data-ttu-id="94b69-108">BAM 管理实用程序</span><span class="sxs-lookup"><span data-stu-id="94b69-108">BAM Management Utility</span></span>  
 <span data-ttu-id="94b69-109">管理员可以使用 BAM 管理实用程序来启用、 禁用和删除警报。</span><span class="sxs-lookup"><span data-stu-id="94b69-109">Administrators can use the BAM Management utility to enable, disable, and remove alerts.</span></span>  
  
 <span data-ttu-id="94b69-110">有关使用 BAM 管理实用程序管理警报，以下主题的信息：</span><span class="sxs-lookup"><span data-stu-id="94b69-110">For information on using the BAM Management Utility to mange alerts, the following topics:</span></span>  
  
-   [<span data-ttu-id="94b69-111">如何启用警报</span><span class="sxs-lookup"><span data-stu-id="94b69-111">How to Enable Alerts</span></span>](../core/how-to-enable-alerts.md) 
  
-   [<span data-ttu-id="94b69-112">如何禁用警报</span><span class="sxs-lookup"><span data-stu-id="94b69-112">How to Disable Alerts</span></span>](../core/how-to-disable-alerts.md)  
  
-   [<span data-ttu-id="94b69-113">如何删除 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="94b69-113">How to Remove BAM Alerts</span></span>](../core/how-to-remove-bam-alerts.md)  
  
### <a name="modifying-notification-services-configuration-files"></a><span data-ttu-id="94b69-114">修改 Notification Services 配置文件</span><span class="sxs-lookup"><span data-stu-id="94b69-114">Modifying Notification Services Configuration Files</span></span>  
 <span data-ttu-id="94b69-115">管理员可以使用 ProcessBamNSFiles.vbs 脚本更改在其中 Notification Services 传送警报的方式。</span><span class="sxs-lookup"><span data-stu-id="94b69-115">Administrators can use the ProcessBamNSFiles.vbs script to change the manner in which the Notification Services delivers alerts.</span></span> <span data-ttu-id="94b69-116">Notification Services 的详细信息应用程序定义文件 (ADF)，请参阅[ http://go.microsoft.com/fwlink/?LinkId=127016 ](http://go.microsoft.com/fwlink/?LinkId=127016)。</span><span class="sxs-lookup"><span data-stu-id="94b69-116">For more information the Application Definition File (ADF) for Notification Services, see [http://go.microsoft.com/fwlink/?LinkId=127016](http://go.microsoft.com/fwlink/?LinkId=127016).</span></span>  
  
 <span data-ttu-id="94b69-117">要修改与 BAM 相关的 ADF 可以遵循以下常规步骤：</span><span class="sxs-lookup"><span data-stu-id="94b69-117">To modify the ADF associated with BAM you can follow these general steps:</span></span>  
  
1. <span data-ttu-id="94b69-118">运行脚本，以获得当前配置文件和 ADF 文件。</span><span class="sxs-lookup"><span data-stu-id="94b69-118">Run the script to obtain the current configuration and ADF files.</span></span>  
  
2. <span data-ttu-id="94b69-119">修改的文件。</span><span class="sxs-lookup"><span data-stu-id="94b69-119">Modify the files.</span></span>  
  
3. <span data-ttu-id="94b69-120">运行脚本以应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="94b69-120">Run the script to apply the changes.</span></span>  
  
   <span data-ttu-id="94b69-121">有关 ProcessBamNSFiles.vbs 脚本的详细信息，请参阅[BAM 通知服务配置文件的命令行脚本](../core/bam-command-line-script-for-notification-services-configuration-files.md)。</span><span class="sxs-lookup"><span data-stu-id="94b69-121">For more information on the ProcessBamNSFiles.vbs script, see [BAM Command-Line Script for Notification Services Configuration Files](../core/bam-command-line-script-for-notification-services-configuration-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b69-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="94b69-122">See Also</span></span>  
 <span data-ttu-id="94b69-123">[管理 BAM 门户](../core/managing-the-bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="94b69-123">[Managing the BAM Portal](../core/managing-the-bam-portal.md) </span></span>  
 <span data-ttu-id="94b69-124">[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="94b69-124">[Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md) </span></span>  
 [<span data-ttu-id="94b69-125">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="94b69-125">BAM Management Utility</span></span>](../core/bam-management-utility.md)