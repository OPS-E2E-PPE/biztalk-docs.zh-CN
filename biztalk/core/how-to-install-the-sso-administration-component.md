---
title: 安装 SSO 管理组件 |Microsoft 文档
description: 若要获取 SSO 管理的自定义安装并且使用 ssomanage 或 SSO 管理 BizTalk Server 中输入服务器名称
ms.custom: ''
ms.date: 09/27/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 096839e2-7129-498d-92ee-5afeea8dbe0d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2bb01defe700408a551a144eae67d0405565f4
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2017
ms.locfileid: "22317982"
---
# <a name="how-to-install-the-sso-administration-component"></a><span data-ttu-id="fece3-103">如何安装 SSO 管理组件</span><span class="sxs-lookup"><span data-stu-id="fece3-103">How to Install the SSO Administration Component</span></span>

## <a name="overview"></a><span data-ttu-id="fece3-104">概述</span><span class="sxs-lookup"><span data-stu-id="fece3-104">Overview</span></span>
<span data-ttu-id="fece3-105">你可以作为独立的功能来安装企业单一登录管理组件。</span><span class="sxs-lookup"><span data-stu-id="fece3-105">You can install the Enterprise Single Sign-On Administration component as a stand-alone feature.</span></span> <span data-ttu-id="fece3-106">在需要远程管理 SSO 系统时这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="fece3-106">This is useful if you need to administer the SSO system remotely.</span></span> <span data-ttu-id="fece3-107">其硬件和软件要求与典型的企业 SSO 运行时服务安装的硬件和软件要求相同。</span><span class="sxs-lookup"><span data-stu-id="fece3-107">The hardware and software requirements are the same as for a typical Enterprise SSO Runtime Services installation.</span></span>  
  
 <span data-ttu-id="fece3-108">安装后管理组件，您输入要用于管理 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="fece3-108">After installing the administration component, you enter the SSO Server to be used for management.</span></span> <span data-ttu-id="fece3-109">可以使用命令行工具 (ssomanage.exe) 或 SSO 管理 Mmc 管理单元来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="fece3-109">You can do this with either the command line tool (ssomanage.exe), or the SSO Administration MMC Snap-In.</span></span> <span data-ttu-id="fece3-110">此主题中列出这两个过程。</span><span class="sxs-lookup"><span data-stu-id="fece3-110">Both procedures are listed in this topic.</span></span>  
  
 <span data-ttu-id="fece3-111">安装 SSO 管理实用工具 (ssomanage.exe) 时，不会在“开始”菜单上创建用于访问该命令行实用工具的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="fece3-111">Installing the SSO administrative utility (ssomanage.exe) does not create shortcuts on the Start menu to access the command line utilities.</span></span> <span data-ttu-id="fece3-112">若要在安装后运行的 SSO 管理实用工具，必须打开命令提示符，并导航到在 SSO 目录`Program Files\Common Files\Enterprise Single Sign-On`。</span><span class="sxs-lookup"><span data-stu-id="fece3-112">To run the SSO administrative utilities after installation, you must open a command prompt, and navigate to the SSO directory at `Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
 <span data-ttu-id="fece3-113">企业 SSO 管理功能还包括一个 mmc 管理单元。</span><span class="sxs-lookup"><span data-stu-id="fece3-113">The Enterprise SSO Administration feature also includes an MMC Snap-in.</span></span> <span data-ttu-id="fece3-114">为管理单元在对函数必须在计算机上安装 MMC 3.0。</span><span class="sxs-lookup"><span data-stu-id="fece3-114">MMC 3.0 must be installed on your computer for the Snap-in to function.</span></span>  
  
 <span data-ttu-id="fece3-115">若要打开企业 SSO MMC 管理单元中从**启动**菜单上，选择**所有程序**，选择**Microsoft Enterprise 上单一登录**，，然后**SSO管理**。</span><span class="sxs-lookup"><span data-stu-id="fece3-115">To open the Enterprise SSO MMC Snap-in from the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a><span data-ttu-id="fece3-116">安装企业单一登录管理组件</span><span class="sxs-lookup"><span data-stu-id="fece3-116">Install the Enterprise Single Sign-On administrative component</span></span>  
  
-   <span data-ttu-id="fece3-117">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并选择仅企业单一登录管理功能。</span><span class="sxs-lookup"><span data-stu-id="fece3-117">Do a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and select only the Enterprise Single Sign-On Administration feature.</span></span> <span data-ttu-id="fece3-118">有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，这下列出**其他软件**。</span><span class="sxs-lookup"><span data-stu-id="fece3-118">For [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], this is listed under **Additional Software**.</span></span>  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a><span data-ttu-id="fece3-119">输入使用 MMC 管理单元中的服务器</span><span class="sxs-lookup"><span data-stu-id="fece3-119">Enter the server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="fece3-120">当在未安装管理组件的计算机上安装管理组件后，请打开 SSO 管理单元。</span><span class="sxs-lookup"><span data-stu-id="fece3-120">After installing the administrative component on a computer where it is not currently installed, open the SSO Administration Snap-In.</span></span>  
  
     <span data-ttu-id="fece3-121">在**启动**菜单上，选择**所有程序**，选择**Microsoft Enterprise 上单一登录**，然后选择**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="fece3-121">In the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then select **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="fece3-122">在 MMC 管理单元中下**控制台根节点**，右键单击**企业单一登录**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="fece3-122">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
     <span data-ttu-id="fece3-123">**选择 SSO 服务器**对话框将出现。</span><span class="sxs-lookup"><span data-stu-id="fece3-123">The **Select SSO Server** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="fece3-124">输入或浏览到要指定的 SSO 服务器名。</span><span class="sxs-lookup"><span data-stu-id="fece3-124">Enter or browse to the SSO server name you want to specify.</span></span> <span data-ttu-id="fece3-125">若要指定所有用户的 SSO 服务器的计算机上，选择**设置 SSO 服务器的所有用户**。</span><span class="sxs-lookup"><span data-stu-id="fece3-125">To specify the SSO server for all users on the computer, select **Set SSO Server for all users**.</span></span>  
  
4.  <span data-ttu-id="fece3-126">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fece3-126">Click **OK**.</span></span>  
  
## <a name="enter-the-server-using-the-command-line-tool"></a><span data-ttu-id="fece3-127">输入使用命令行工具的服务器</span><span class="sxs-lookup"><span data-stu-id="fece3-127">Enter the server using the command line tool</span></span>  
  
1.  <span data-ttu-id="fece3-128">依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="fece3-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="fece3-129">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="fece3-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="fece3-130">默认安装目录是`\Program Files\Common Files\Enterprise Single Sign-On`。</span><span class="sxs-lookup"><span data-stu-id="fece3-130">The default installation directory is `\Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
3.  <span data-ttu-id="fece3-131">通过选择以下选项之一来输入 SSO 服务器：</span><span class="sxs-lookup"><span data-stu-id="fece3-131">Enter the SSO Server by selecting one of the following options:</span></span>  
  
    1.  <span data-ttu-id="fece3-132">类型**ssomanage-服务器**输入你想要执行管理操作时，连接到的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="fece3-132">Type **ssomanage –server** to enter the SSO Server you want to connect to when performing administration operations.</span></span>  
  
         <span data-ttu-id="fece3-133">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="fece3-133">\- OR -</span></span>  
  
    2.  <span data-ttu-id="fece3-134">类型**ssomanage serverall**输入执行管理操作时，此计算机的所有用户将都连接到 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="fece3-134">Type **ssomanage -serverall** to enter the SSO Server all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fece3-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fece3-135">See Also</span></span>  
 <span data-ttu-id="fece3-136">[如何安装 SSO 客户端实用工具](../core/how-to-install-the-sso-client-utility.md) </span><span class="sxs-lookup"><span data-stu-id="fece3-136">[How to Install the SSO Client Utility](../core/how-to-install-the-sso-client-utility.md) </span></span>  
 <span data-ttu-id="fece3-137">[配置 SSO](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="fece3-137">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="fece3-138">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="fece3-138">Installing SSO</span></span>](../core/installing-sso.md)
