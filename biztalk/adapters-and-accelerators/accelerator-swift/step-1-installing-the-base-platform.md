---
title: "步骤 1： 安装基础平台 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b7551972c14de0bcbd36532d76e3706a762cf48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-installing-the-base-platform"></a><span data-ttu-id="7b587-102">步骤 1： 安装基础平台</span><span class="sxs-lookup"><span data-stu-id="7b587-102">Step 1: Installing the Base Platform</span></span>
<span data-ttu-id="7b587-103">对于基础平台，安装[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]和[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]使用默认安装选项的每个服务器上的 Service Pack 2。</span><span class="sxs-lookup"><span data-stu-id="7b587-103">For the base platform, install [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] Service Pack 2 on each server using the default installation options.</span></span> <span data-ttu-id="7b587-104">请遵循这些建议：</span><span class="sxs-lookup"><span data-stu-id="7b587-104">Follow these recommendations:</span></span>  
  
## <a name="pre-installation"></a><span data-ttu-id="7b587-105">预安装</span><span class="sxs-lookup"><span data-stu-id="7b587-105">Pre-Installation</span></span>  
  
-   <span data-ttu-id="7b587-106">在软件安装过程中禁用所有防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="7b587-106">Disable all antivirus software during software installation.</span></span> <span data-ttu-id="7b587-107">某些防病毒软件程序可能会阻止所需的软件组件正确安装。</span><span class="sxs-lookup"><span data-stu-id="7b587-107">Some antivirus software programs might prevent required software components from installing properly.</span></span>  
  
-   <span data-ttu-id="7b587-108">请确保你输入合适的许可信息 （最大你购买的每个服务器的连接数）。</span><span class="sxs-lookup"><span data-stu-id="7b587-108">Make sure that you enter the appropriate licensing information (maximum number of connections you have purchased per server).</span></span> <span data-ttu-id="7b587-109">可以通过的可用连接数影响系统性能。</span><span class="sxs-lookup"><span data-stu-id="7b587-109">System performance can be affected by the number of available connections.</span></span>  
  
-   <span data-ttu-id="7b587-110">请确保你已安装所需的所有软件必备项[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="7b587-110">Make sure that you have installed all the software prerequisites required for a [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] installation.</span></span> <span data-ttu-id="7b587-111">有关详细信息，请参阅在 BizTalk Server 安装说明[http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)。</span><span class="sxs-lookup"><span data-stu-id="7b587-111">For more information, see the BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span> <span data-ttu-id="7b587-112">[安装指南 》 BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)。</span><span class="sxs-lookup"><span data-stu-id="7b587-112">[Installation Guide for BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1).</span></span>  
  
-   <span data-ttu-id="7b587-113">在生产服务器上安装它们之前，请在脱机环境中测试所有重要更新。</span><span class="sxs-lookup"><span data-stu-id="7b587-113">Test all critical updates in an offline environment before installing them on your production servers.</span></span>  
  
-   <span data-ttu-id="7b587-114">请确保你安装适用的作为你部署的一部分安装的所有产品的所有修补程序。</span><span class="sxs-lookup"><span data-stu-id="7b587-114">Make sure that you install all the applicable hotfixes for all the products that you install as part of your deployment.</span></span> <span data-ttu-id="7b587-115">有关详细信息，请参阅以下源：</span><span class="sxs-lookup"><span data-stu-id="7b587-115">For more information, see the following sources:</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="7b587-116">[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]联机帮助</span><span class="sxs-lookup"><span data-stu-id="7b587-116"> [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Online Help</span></span>  
  
    -   <span data-ttu-id="7b587-117">在 BizTalk Server 安装说明[http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041)。</span><span class="sxs-lookup"><span data-stu-id="7b587-117">BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="7b587-118">[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]网站，网址[http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685)。</span><span class="sxs-lookup"><span data-stu-id="7b587-118"> [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web site at [http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685).</span></span>  
  
    -   [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="7b587-119">下载中心网站，网址[http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686)。</span><span class="sxs-lookup"><span data-stu-id="7b587-119"> Download Center Web site at [http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686).</span></span>  
  
    -   [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)]<span data-ttu-id="7b587-120">网站，网址[http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687)。</span><span class="sxs-lookup"><span data-stu-id="7b587-120"> Web site at [http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687).</span></span>  
  
-   <span data-ttu-id="7b587-121">若要避免病毒攻击，从 CD 安装平台，并通过一个电缆拔出并禁用任何网络适配器将每个服务器断开 Internet。</span><span class="sxs-lookup"><span data-stu-id="7b587-121">To avoid virus attacks, install the platform from a CD and disconnect each server from the Internet by unplugging any cables and disabling any network adapters.</span></span>  
  
-   <span data-ttu-id="7b587-122">干净分区使用格式的[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]NTFS 文件系统。</span><span class="sxs-lookup"><span data-stu-id="7b587-122">Format a clean partition using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS file system.</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="7b587-123">Active Directory</span><span class="sxs-lookup"><span data-stu-id="7b587-123">Active Directory</span></span>  
  
-   <span data-ttu-id="7b587-124">创建一个名为的域用户**管理员**并将其添加到本地**管理员**组部署中的每台计算机上。</span><span class="sxs-lookup"><span data-stu-id="7b587-124">Create a domain user called **Admin** and add it to the local **Administrators** group on every computer in your deployment.</span></span> <span data-ttu-id="7b587-125">在安装时，登录到使用此域帐户的部署服务器。</span><span class="sxs-lookup"><span data-stu-id="7b587-125">At installation time, log on to the deployment servers using this domain account.</span></span>  
  
-   <span data-ttu-id="7b587-126">请不要配置任何网络适配器，或者在此时加入任何域。</span><span class="sxs-lookup"><span data-stu-id="7b587-126">Do not configure any network adapters or join any domains at this time.</span></span> <span data-ttu-id="7b587-127">本指南介绍如何更高版本配置这些设置，当你开始部署过程。</span><span class="sxs-lookup"><span data-stu-id="7b587-127">This guide describes how to configure these settings later when you begin the deployment process.</span></span>  
  
## <a name="internal-web-servers-mrsr-site"></a><span data-ttu-id="7b587-128">内部 Web 服务器 （MRSR 站点）</span><span class="sxs-lookup"><span data-stu-id="7b587-128">Internal Web Servers (MRSR site)</span></span>  
  
-   <span data-ttu-id="7b587-129">请确保仅在 MRSR 站点服务器上安装 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="7b587-129">Make sure that Internet Information Services (IIS) is installed only on the MRSR site Servers.</span></span>  
  
-   <span data-ttu-id="7b587-130">请确保 Internet 信息服务 (IIS) 未安装在 Internet Security and Acceleration (ISA) Server。</span><span class="sxs-lookup"><span data-stu-id="7b587-130">Make sure that Internet Information Services (IIS) is not installed on the Internet Security and Acceleration (ISA) Server.</span></span>  
  
-   <span data-ttu-id="7b587-131">请确保仅在 MRSR 站点服务器上安装了消息队列 (MSMQ) 服务。</span><span class="sxs-lookup"><span data-stu-id="7b587-131">Make sure that the Message Queuing (MSMQ) service is installed only on the MRSR site Servers.</span></span> <span data-ttu-id="7b587-132">如果 BizTalk 消息传送服务器也将用作 MRSR 站点服务器，并在这些服务器上安装 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="7b587-132">If the BizTalk Messaging servers will also be used as the MRSR site Servers, do not install MSMQ on those servers.</span></span>