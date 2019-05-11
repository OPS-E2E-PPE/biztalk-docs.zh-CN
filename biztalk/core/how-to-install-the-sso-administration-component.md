---
title: 安装 SSO 管理组件 |Microsoft Docs
description: 若要获取 SSO 管理自定义安装和使用 ssomanage 或 SSO 管理 BizTalk Server 中输入服务器名称
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
ms.openlocfilehash: f5c431b90d1d128831f18d2ec1f53acfc891d91d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336923"
---
# <a name="how-to-install-the-sso-administration-component"></a><span data-ttu-id="b395b-103">如何安装 SSO 管理组件</span><span class="sxs-lookup"><span data-stu-id="b395b-103">How to Install the SSO Administration Component</span></span>

## <a name="overview"></a><span data-ttu-id="b395b-104">概述</span><span class="sxs-lookup"><span data-stu-id="b395b-104">Overview</span></span>
<span data-ttu-id="b395b-105">可以作为独立的功能来安装企业单一登录管理组件。</span><span class="sxs-lookup"><span data-stu-id="b395b-105">You can install the Enterprise Single Sign-On Administration component as a stand-alone feature.</span></span> <span data-ttu-id="b395b-106">这是很有用，如果需要远程管理 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="b395b-106">This is useful if you need to administer the SSO system remotely.</span></span> <span data-ttu-id="b395b-107">与典型的企业 SSO 运行时服务安装相同的硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="b395b-107">The hardware and software requirements are the same as for a typical Enterprise SSO Runtime Services installation.</span></span>  
  
 <span data-ttu-id="b395b-108">在安装后管理组件，您输入要用于进行管理的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="b395b-108">After installing the administration component, you enter the SSO Server to be used for management.</span></span> <span data-ttu-id="b395b-109">可以使用命令行工具 (ssomanage.exe) 或 SSO 管理 Mmc 管理单元来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b395b-109">You can do this with either the command line tool (ssomanage.exe), or the SSO Administration MMC Snap-In.</span></span> <span data-ttu-id="b395b-110">本主题列出了这两个过程。</span><span class="sxs-lookup"><span data-stu-id="b395b-110">Both procedures are listed in this topic.</span></span>  
  
 <span data-ttu-id="b395b-111">安装 SSO 管理实用工具 (ssomanage.exe) 不会在开始菜单访问命令行实用程序创建快捷方式。</span><span class="sxs-lookup"><span data-stu-id="b395b-111">Installing the SSO administrative utility (ssomanage.exe) does not create shortcuts on the Start menu to access the command line utilities.</span></span> <span data-ttu-id="b395b-112">若要在安装后运行 SSO 管理实用工具，必须打开命令提示符，并导航到的 SSO 目录`Program Files\Common Files\Enterprise Single Sign-On`。</span><span class="sxs-lookup"><span data-stu-id="b395b-112">To run the SSO administrative utilities after installation, you must open a command prompt, and navigate to the SSO directory at `Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
 <span data-ttu-id="b395b-113">企业 SSO 管理功能还包括一个 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="b395b-113">The Enterprise SSO Administration feature also includes an MMC Snap-in.</span></span> <span data-ttu-id="b395b-114">对于中的管理单元函数必须在计算机上安装 MMC 3.0。</span><span class="sxs-lookup"><span data-stu-id="b395b-114">MMC 3.0 must be installed on your computer for the Snap-in to function.</span></span>  
  
 <span data-ttu-id="b395b-115">若要打开企业 SSO MMC 管理单元中的**启动**菜单中，选择**所有程序**，选择**Microsoft 企业单一登录**，然后**SSO管理**。</span><span class="sxs-lookup"><span data-stu-id="b395b-115">To open the Enterprise SSO MMC Snap-in from the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then **SSO Administration**.</span></span>  
  
## <a name="install-the-enterprise-single-sign-on-administrative-component"></a><span data-ttu-id="b395b-116">安装企业单一登录管理组件</span><span class="sxs-lookup"><span data-stu-id="b395b-116">Install the Enterprise Single Sign-On administrative component</span></span>  
  
- <span data-ttu-id="b395b-117">执行的自定义安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并选择仅企业单一登录管理功能。</span><span class="sxs-lookup"><span data-stu-id="b395b-117">Do a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and select only the Enterprise Single Sign-On Administration feature.</span></span> <span data-ttu-id="b395b-118">有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，这列入**其他软件**。</span><span class="sxs-lookup"><span data-stu-id="b395b-118">For [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], this is listed under **Additional Software**.</span></span>  
  
## <a name="enter-the-server-using-the-mmc-snap-in"></a><span data-ttu-id="b395b-119">输入使用 MMC 管理单元中的服务器</span><span class="sxs-lookup"><span data-stu-id="b395b-119">Enter the server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="b395b-120">在安装后管理组件，它当前未安装的计算机上，打开 SSO 管理管理单元。</span><span class="sxs-lookup"><span data-stu-id="b395b-120">After installing the administrative component on a computer where it is not currently installed, open the SSO Administration Snap-In.</span></span>  
  
     <span data-ttu-id="b395b-121">在中**启动**菜单中，选择**所有程序**，选择**Microsoft 企业单一登录**，然后选择**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="b395b-121">In the **Start** menu, select **All Programs**, select **Microsoft Enterprise Single Sign-On**, and then select **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="b395b-122">在 Mmc 管理单元下**控制台根节点**，右键单击**企业单一登录**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="b395b-122">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
     <span data-ttu-id="b395b-123">**选择 SSO Server**对话框将出现。</span><span class="sxs-lookup"><span data-stu-id="b395b-123">The **Select SSO Server** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="b395b-124">输入或浏览到想要指定的 SSO 服务器名称。</span><span class="sxs-lookup"><span data-stu-id="b395b-124">Enter or browse to the SSO server name you want to specify.</span></span> <span data-ttu-id="b395b-125">若要指定 SSO 服务器的所有用户的计算机上，选择**为所有用户设置 SSO 服务器**。</span><span class="sxs-lookup"><span data-stu-id="b395b-125">To specify the SSO server for all users on the computer, select **Set SSO Server for all users**.</span></span>  
  
4.  <span data-ttu-id="b395b-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="b395b-126">Click **OK**.</span></span>  
  
## <a name="enter-the-server-using-the-command-line-tool"></a><span data-ttu-id="b395b-127">输入使用命令行工具的服务器</span><span class="sxs-lookup"><span data-stu-id="b395b-127">Enter the server using the command line tool</span></span>  
  
1.  <span data-ttu-id="b395b-128">依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="b395b-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="b395b-129">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="b395b-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="b395b-130">默认安装目录是`\Program Files\Common Files\Enterprise Single Sign-On`。</span><span class="sxs-lookup"><span data-stu-id="b395b-130">The default installation directory is `\Program Files\Common Files\Enterprise Single Sign-On`.</span></span>  
  
3.  <span data-ttu-id="b395b-131">通过选择下列选项之一来输入 SSO 服务器：</span><span class="sxs-lookup"><span data-stu-id="b395b-131">Enter the SSO Server by selecting one of the following options:</span></span>  
  
    1.  <span data-ttu-id="b395b-132">类型**ssomanage – server**输入想要执行管理操作时连接到的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="b395b-132">Type **ssomanage –server** to enter the SSO Server you want to connect to when performing administration operations.</span></span>  
  
         <span data-ttu-id="b395b-133">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="b395b-133">\- OR -</span></span>  
  
    2.  <span data-ttu-id="b395b-134">类型**ssomanage-serverall，** 输入执行管理操作时，此计算机的所有用户将都连接到 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="b395b-134">Type **ssomanage -serverall** to enter the SSO Server all users of this computer will connect to when performing administration operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b395b-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="b395b-135">See Also</span></span>  
 <span data-ttu-id="b395b-136">[如何安装 SSO 客户端实用工具](../core/how-to-install-the-sso-client-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b395b-136">[How to Install the SSO Client Utility](../core/how-to-install-the-sso-client-utility.md) </span></span>  
 <span data-ttu-id="b395b-137">[配置 SSO](../core/configuring-sso.md) </span><span class="sxs-lookup"><span data-stu-id="b395b-137">[Configuring SSO](../core/configuring-sso.md) </span></span>  
 [<span data-ttu-id="b395b-138">安装 SSO</span><span class="sxs-lookup"><span data-stu-id="b395b-138">Installing SSO</span></span>](../core/installing-sso.md)
