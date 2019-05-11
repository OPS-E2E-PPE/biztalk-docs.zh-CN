---
title: 第 1 步：安装基础平台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- platforms
- installing, base platform
- base platform
ms.assetid: 27da386f-90c7-414f-a4e3-e909f0c18371
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd3f901e31f0def313f3f8cf5cb3a9b8ea0dd16c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529967"
---
# <a name="step-1-installing-the-base-platform"></a><span data-ttu-id="fdf41-102">第 1 步：安装基础平台</span><span class="sxs-lookup"><span data-stu-id="fdf41-102">Step 1: Installing the Base Platform</span></span>
<span data-ttu-id="fdf41-103">基础平台，用于安装 Microsoft[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]和[!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)]使用默认安装选项的每个服务器上的 Service Pack 2。</span><span class="sxs-lookup"><span data-stu-id="fdf41-103">For the base platform, install Microsoft [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k3](../../includes/btswinsvr2k3-md.md)] Service Pack 2 on each server using the default installation options.</span></span> <span data-ttu-id="fdf41-104">请遵循以下建议：</span><span class="sxs-lookup"><span data-stu-id="fdf41-104">Follow these recommendations:</span></span>  
  
## <a name="pre-installation"></a><span data-ttu-id="fdf41-105">预安装</span><span class="sxs-lookup"><span data-stu-id="fdf41-105">Pre-Installation</span></span>  
  
- <span data-ttu-id="fdf41-106">在软件安装过程中禁用所有防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="fdf41-106">Disable all antivirus software during software installation.</span></span> <span data-ttu-id="fdf41-107">某些防病毒软件程序可能会阻止所需的软件组件正确安装。</span><span class="sxs-lookup"><span data-stu-id="fdf41-107">Some antivirus software programs might prevent required software components from installing properly.</span></span>  
  
- <span data-ttu-id="fdf41-108">请确保输入适当的授权信息 （最大已购买每个服务器的连接数）。</span><span class="sxs-lookup"><span data-stu-id="fdf41-108">Make sure that you enter the appropriate licensing information (maximum number of connections you have purchased per server).</span></span> <span data-ttu-id="fdf41-109">系统性能可能受到可用连接数。</span><span class="sxs-lookup"><span data-stu-id="fdf41-109">System performance can be affected by the number of available connections.</span></span>  
  
- <span data-ttu-id="fdf41-110">请确保已安装 BizTalk Server 安装所需的所有软件必备项。</span><span class="sxs-lookup"><span data-stu-id="fdf41-110">Make sure that you have installed all the software prerequisites required for a BizTalk Server installation.</span></span> <span data-ttu-id="fdf41-111">有关详细信息，请参阅 BizTalk Server 安装说明[ http://go.microsoft.com/fwlink/?LinkId=81041 ](http://go.microsoft.com/fwlink/?LinkId=81041)。</span><span class="sxs-lookup"><span data-stu-id="fdf41-111">For more information, see the BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span> <span data-ttu-id="fdf41-112">[BizTalk 2013 R2 accelerator for SWIFT 安装指南](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1)。</span><span class="sxs-lookup"><span data-stu-id="fdf41-112">[Installation Guide for BizTalk 2013 R2 Accelerator for SWIFT](http://msdn.microsoft.com/library/d2b4a9f3-baeb-4fbc-9fda-5e4178832cd1).</span></span>  
  
- <span data-ttu-id="fdf41-113">在脱机环境中测试所有关键更新，然后再在生产服务器上安装它们。</span><span class="sxs-lookup"><span data-stu-id="fdf41-113">Test all critical updates in an offline environment before installing them on your production servers.</span></span>  
  
- <span data-ttu-id="fdf41-114">请确保安装所有适用的修补程序作为你的部署的一部分安装的所有产品。</span><span class="sxs-lookup"><span data-stu-id="fdf41-114">Make sure that you install all the applicable hotfixes for all the products that you install as part of your deployment.</span></span> <span data-ttu-id="fdf41-115">有关详细信息，请参阅以下源：</span><span class="sxs-lookup"><span data-stu-id="fdf41-115">For more information, see the following sources:</span></span>  
  
  - <span data-ttu-id="fdf41-116">Microsoft BizTalk Server 联机帮助</span><span class="sxs-lookup"><span data-stu-id="fdf41-116">Microsoft BizTalk Server Online Help</span></span>  
  
  - <span data-ttu-id="fdf41-117">在 BizTalk Server 安装说明[ http://go.microsoft.com/fwlink/?LinkId=81041 ](http://go.microsoft.com/fwlink/?LinkId=81041)。</span><span class="sxs-lookup"><span data-stu-id="fdf41-117">BizTalk Server Installation Instructions at [http://go.microsoft.com/fwlink/?LinkId=81041](http://go.microsoft.com/fwlink/?LinkId=81041).</span></span>  
  
  - <span data-ttu-id="fdf41-118">Microsoft[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]网站，网址[ http://go.microsoft.com/fwlink/?linkid=48685 ](http://go.microsoft.com/fwlink/?linkid=48685)。</span><span class="sxs-lookup"><span data-stu-id="fdf41-118">Microsoft [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Web site at [http://go.microsoft.com/fwlink/?linkid=48685](http://go.microsoft.com/fwlink/?linkid=48685).</span></span>  
  
  - <span data-ttu-id="fdf41-119">Microsoft 下载网站，网址[ http://go.microsoft.com/fwlink/?linkid=48686 ](http://go.microsoft.com/fwlink/?linkid=48686)。</span><span class="sxs-lookup"><span data-stu-id="fdf41-119">Microsoft Download Center Web site at [http://go.microsoft.com/fwlink/?linkid=48686](http://go.microsoft.com/fwlink/?linkid=48686).</span></span>  
  
  - [!INCLUDE[btsWinUpdate](../../includes/btswinupdate-md.md)] <span data-ttu-id="fdf41-120">网站，网址[ http://go.microsoft.com/fwlink/?linkid=48687 ](http://go.microsoft.com/fwlink/?linkid=48687)。</span><span class="sxs-lookup"><span data-stu-id="fdf41-120">Web site at [http://go.microsoft.com/fwlink/?linkid=48687](http://go.microsoft.com/fwlink/?linkid=48687).</span></span>  
  
- <span data-ttu-id="fdf41-121">若要避免病毒攻击，从 CD 安装平台和每个服务器断开与 Internet 的连接电缆拔出和禁用任何网络适配器。</span><span class="sxs-lookup"><span data-stu-id="fdf41-121">To avoid virus attacks, install the platform from a CD and disconnect each server from the Internet by unplugging any cables and disabling any network adapters.</span></span>  
  
- <span data-ttu-id="fdf41-122">空白分区使用格式[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]NTFS 文件系统。</span><span class="sxs-lookup"><span data-stu-id="fdf41-122">Format a clean partition using the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] NTFS file system.</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="fdf41-123">Active Directory</span><span class="sxs-lookup"><span data-stu-id="fdf41-123">Active Directory</span></span>  
  
-   <span data-ttu-id="fdf41-124">创建名为域用户**管理员**并将其添加到本地**管理员**组在部署中每台计算机上。</span><span class="sxs-lookup"><span data-stu-id="fdf41-124">Create a domain user called **Admin** and add it to the local **Administrators** group on every computer in your deployment.</span></span> <span data-ttu-id="fdf41-125">在安装时，登录到部署服务器使用此域帐户。</span><span class="sxs-lookup"><span data-stu-id="fdf41-125">At installation time, log on to the deployment servers using this domain account.</span></span>  
  
-   <span data-ttu-id="fdf41-126">没有配置任何网络适配器或在此时加入任何域。</span><span class="sxs-lookup"><span data-stu-id="fdf41-126">Do not configure any network adapters or join any domains at this time.</span></span> <span data-ttu-id="fdf41-127">本指南介绍如何配置这些设置更高版本时开始部署过程。</span><span class="sxs-lookup"><span data-stu-id="fdf41-127">This guide describes how to configure these settings later when you begin the deployment process.</span></span>  
  
## <a name="internal-web-servers-mrsr-site"></a><span data-ttu-id="fdf41-128">内部 Web 服务器 （MRSR 站点）</span><span class="sxs-lookup"><span data-stu-id="fdf41-128">Internal Web Servers (MRSR site)</span></span>  
  
-   <span data-ttu-id="fdf41-129">请确保仅在 MRSR 站点服务器上安装 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="fdf41-129">Make sure that Internet Information Services (IIS) is installed only on the MRSR site Servers.</span></span>  
  
-   <span data-ttu-id="fdf41-130">请确保 Internet 信息服务 (IIS) 未安装 Internet Security and Acceleration (ISA) 服务器上。</span><span class="sxs-lookup"><span data-stu-id="fdf41-130">Make sure that Internet Information Services (IIS) is not installed on the Internet Security and Acceleration (ISA) Server.</span></span>  
  
-   <span data-ttu-id="fdf41-131">请确保仅在 MRSR 站点服务器上安装了消息队列 (MSMQ) 服务。</span><span class="sxs-lookup"><span data-stu-id="fdf41-131">Make sure that the Message Queuing (MSMQ) service is installed only on the MRSR site Servers.</span></span> <span data-ttu-id="fdf41-132">如果 BizTalk 消息传送服务器也将用作 MRSR 站点服务器，并在这些服务器上安装 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="fdf41-132">If the BizTalk Messaging servers will also be used as the MRSR site Servers, do not install MSMQ on those servers.</span></span>