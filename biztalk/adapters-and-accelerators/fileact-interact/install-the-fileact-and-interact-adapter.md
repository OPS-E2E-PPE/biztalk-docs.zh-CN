---
title: "安装 FileAct 和交互适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf387d59-373b-4151-9dfd-30c511978862
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48a3beccd6179bcb4526ba41f4f41a7923f5f966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-fileact-and-interact-adapter"></a><span data-ttu-id="35d7e-102">安装 FileAct 和交互适配器</span><span class="sxs-lookup"><span data-stu-id="35d7e-102">Install the FileAct and InterAct Adapter</span></span>
<span data-ttu-id="35d7e-103">本部分介绍了如何安装[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]– for SWIFT。</span><span class="sxs-lookup"><span data-stu-id="35d7e-103">This section provides instructions to install [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] – for SWIFT.</span></span> <span data-ttu-id="35d7e-104">安装适配器之前，你必须安装必备软件。</span><span class="sxs-lookup"><span data-stu-id="35d7e-104">Before you install the adapters, you must install the prerequisite software.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="35d7e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="35d7e-105">Prerequisites</span></span>  

* <span data-ttu-id="35d7e-106">使用的是本地管理员组的成员和 BizTalk Server Administrators 组的成员的帐户登录</span><span class="sxs-lookup"><span data-stu-id="35d7e-106">Sign in with an account that is member of the local administrators group, and a member of the BizTalk Server Administrators group</span></span>
  
## <a name="step-1-install-biztalk-server-and-configure-bam"></a><span data-ttu-id="35d7e-107">步骤 1： 安装 BizTalk Server 和配置 BAM</span><span class="sxs-lookup"><span data-stu-id="35d7e-107">Step 1: Install BizTalk Server and configure BAM</span></span>

1. <span data-ttu-id="35d7e-108">安装[BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md)，或[BizTalk Server 2013 R2 / 2013年](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md)，并安装业务活动监视 (BAM)。</span><span class="sxs-lookup"><span data-stu-id="35d7e-108">Install [BizTalk Server 2016](../../install-and-config-guides/biztalk-server-2016-what-s-new-and-installation.md), or [BizTalk Server 2013 R2 / 2013](../../install-and-config-guides/biztalk-server-2013-and-2013-r2-what-s-new-install-and-upgrade.md), and install Business Activity Monitoring (BAM).</span></span>

2. <span data-ttu-id="35d7e-109">配置[BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md)，并配置业务活动监视 (BAM)。</span><span class="sxs-lookup"><span data-stu-id="35d7e-109">Configure [BizTalk Server](../../install-and-config-guides/configure-biztalk-server.md), and configure Business Activity Monitoring (BAM).</span></span>
  
3. <span data-ttu-id="35d7e-110">请确保有足够的安全特权来访问[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="35d7e-110">Make sure you have enough security privileges to access the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="35d7e-111">[BizTalk Server 的最低安全权限](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)是一个不错的资源。</span><span class="sxs-lookup"><span data-stu-id="35d7e-111">[Minimum Security Rights for BizTalk Server](http://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx) is a great resource.</span></span>
  
## <a name="step-2-install-biztalk-accelerator-for-swift-a4swift"></a><span data-ttu-id="35d7e-112">步骤 2： 安装 BizTalk Accelerator for SWIFT (A4SWIFT)</span><span class="sxs-lookup"><span data-stu-id="35d7e-112">Step 2: Install BizTalk Accelerator for SWIFT (A4SWIFT)</span></span>  

<span data-ttu-id="35d7e-113">安装和配置[BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md)。</span><span class="sxs-lookup"><span data-stu-id="35d7e-113">Install and configure the [BizTalk Accelerator for SWIFT](../../adapters-and-accelerators/accelerator-swift/install-configure-and-deploy-the-biztalk-accelerator-for-swift.md).</span></span>

  
## <a name="step-3-install-swiftalliance-gateway-sag"></a><span data-ttu-id="35d7e-114">步骤 3： 安装 SWIFTAlliance 网关 （压降）</span><span class="sxs-lookup"><span data-stu-id="35d7e-114">Step 3: Install SWIFTAlliance Gateway (SAG)</span></span>  
 <span data-ttu-id="35d7e-115">在安装的 FileAct 和交互适配器之前，创建压降消息合作伙伴、 终结点和路由规则，并测试压降连接，可以在其中安装的 FileAct 和交互适配器的计算机。</span><span class="sxs-lookup"><span data-stu-id="35d7e-115">Before you install the FileAct and InterAct adapters, create the SAG Message Partners, End Points, and Routing Rules, and test the SAG connectivity on the computer where you install the FileAct and InterAct adapters.</span></span>

<span data-ttu-id="35d7e-116">请参阅[https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway)有关 SWIFTAlliance 网关的特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="35d7e-116">See [https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway](https://www.swift.com/our-solutions/interfaces-and-integration/alliance-gateway) for specific details on the SWIFTAlliance Gateway.</span></span>  

## <a name="step-4-install-the-biztalk-fileact-and-interact-adapters"></a><span data-ttu-id="35d7e-117">步骤 4： 安装的 BizTalk FileAct 和交互适配器</span><span class="sxs-lookup"><span data-stu-id="35d7e-117">Step 4: Install the BizTalk FileAct and InterAct adapters</span></span>  
  
1. <span data-ttu-id="35d7e-118">运行**Setup.exe**以管理员身份开始安装。</span><span class="sxs-lookup"><span data-stu-id="35d7e-118">Run the **Setup.exe** as administrator to start the installation.</span></span>  
  
2.  <span data-ttu-id="35d7e-119">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="35d7e-119">Select **Install**.</span></span>  
  
3.  <span data-ttu-id="35d7e-120">输入你的用户名和组织名称，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="35d7e-120">Enter your user name and organization name, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="35d7e-121">**接受**许可协议。</span><span class="sxs-lookup"><span data-stu-id="35d7e-121">**Accept** the license agreement.</span></span>
  
5.  <span data-ttu-id="35d7e-122">上**安装选项**页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="35d7e-122">On the **Installation Options** page, do one of the following:</span></span>  
  
    -   <span data-ttu-id="35d7e-123">选择**完成**选项来安装 FileAct 的所有组件和交互适配器。</span><span class="sxs-lookup"><span data-stu-id="35d7e-123">Select the **Complete** option to install all components of the FileAct and InterAct adapters.</span></span>  
  
    -   <span data-ttu-id="35d7e-124">选择**自定义**选项，选择要安装哪些组件。</span><span class="sxs-lookup"><span data-stu-id="35d7e-124">Select the **Custom** option to choose which components to install.</span></span>  
  
     <span data-ttu-id="35d7e-125">验证安装位置，或选择**浏览**选择不同的安装位置。</span><span class="sxs-lookup"><span data-stu-id="35d7e-125">Verify the installation location, or select **Browse** to select a different installation location.</span></span> <span data-ttu-id="35d7e-126">选择“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="35d7e-126">Select **Next**.</span></span>  
  
6.  <span data-ttu-id="35d7e-127">上**摘要**页上，选择**安装**安装列出的组件。</span><span class="sxs-lookup"><span data-stu-id="35d7e-127">On the **Summary** page, select **Install** to install the listed components.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35d7e-128">当**运行配置向导**是选择 （默认值）、 **Microsoft BizTalk FileAct 和交互适配器配置**向导将自动运行时你选择**完成**.</span><span class="sxs-lookup"><span data-stu-id="35d7e-128">When **Run Configuration Wizard** is selected (the default), the **Microsoft BizTalk FileAct and InterAct Adapter Configuration** wizard runs automatically when you select **Finish**.</span></span>  
  
7. <span data-ttu-id="35d7e-129">当安装完成后时，选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="35d7e-129">When the installation completes, select **Finish**.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="35d7e-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="35d7e-130">Next steps</span></span>

[<span data-ttu-id="35d7e-131">配置 FileAct 和交互适配器</span><span class="sxs-lookup"><span data-stu-id="35d7e-131">Configure the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/configure-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="35d7e-132">示例交互和 FileAct 消息</span><span class="sxs-lookup"><span data-stu-id="35d7e-132">Sample InterAct and FileAct messages</span></span>](../../adapters-and-accelerators/fileact-interact/sample-interact-and-fileact-messages.md)  
[<span data-ttu-id="35d7e-133">卸载或修复 FileAct 和交互适配器</span><span class="sxs-lookup"><span data-stu-id="35d7e-133">Uninstall or repair the FileAct and InterAct adapter</span></span>](../../adapters-and-accelerators/fileact-interact/uninstall-or-repair-the-fileact-and-interact-adapter.md)  
[<span data-ttu-id="35d7e-134">读取安装的已知问题</span><span class="sxs-lookup"><span data-stu-id="35d7e-134">Read the installation known issues</span></span>](../../adapters-and-accelerators/fileact-interact/read-the-installation-known-issues.md)
  
## <a name="see-also"></a><span data-ttu-id="35d7e-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35d7e-135">See Also</span></span>  
[<span data-ttu-id="35d7e-136">入门的 FileAct 和交互适配器</span><span class="sxs-lookup"><span data-stu-id="35d7e-136">Getting started with the FileAct and InterAct adapters</span></span>](../../adapters-and-accelerators/fileact-interact/getting-started-with-the-fileact-and-interact-adapters.md)  
[<span data-ttu-id="35d7e-137">了解 FileAct 和交互适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="35d7e-137">Understanding FileAct and InterAct adapter architecture</span></span>](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)