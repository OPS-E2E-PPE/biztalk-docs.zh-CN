---
title: 如何启用和禁用主机启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, disabling
- disabling, host initiated SSO
- enabling, host initiated SSO
- host initiated SSO, enabling
ms.assetid: a11d314a-6ff9-4d0a-89c3-c412541c2cec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f187572f671328c77576749b1bf8f3564f025005
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979318"
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a><span data-ttu-id="24728-102">如何启用和禁用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="24728-102">How to Enable and Disable Host Initiated SSO</span></span>
<span data-ttu-id="24728-103">默认情况下，单一登录系统中不启用主机启动的单一登录，而必须由 SSO 管理员启用。</span><span class="sxs-lookup"><span data-stu-id="24728-103">By default, host initiated Single Sign-On is not enabled in the Single Sign-On system, and must be enabled by the SSO Administrator.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="24728-104">使用 MMC 管理单元启用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="24728-104">To enable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="24728-105">上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="24728-105">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="24728-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="24728-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="24728-107">右键单击“系统” ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="24728-107">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="24728-108">单击**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="24728-108">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="24728-109">选择**启用主机启动的 SSO**框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="24728-109">Select the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="24728-110">使用命令行启用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="24728-110">To enable host initiated SSO using the command line</span></span>  
  
1. <span data-ttu-id="24728-111">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="24728-111">On the **Start** menu, click **Run**.</span></span>  
  
2. <span data-ttu-id="24728-112">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="24728-112">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="24728-113">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="24728-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="24728-114">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="24728-114">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="24728-115">类型**ssomanage-启用 hisso**。</span><span class="sxs-lookup"><span data-stu-id="24728-115">Type **ssomanage -enable hisso**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="24728-116">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="24728-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
   <span data-ttu-id="24728-117">禁用 SSO 将应用于整个 SSO 系统，与主机启动的 SSO 相关的所有操作都将关闭。</span><span class="sxs-lookup"><span data-stu-id="24728-117">Disabling SSO applies to the entire SSO system, and all operations related to host initiated SSO are turned off.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a><span data-ttu-id="24728-118">使用 MMC 管理单元禁用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="24728-118">To disable host initiated SSO using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="24728-119">上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="24728-119">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="24728-120">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="24728-120">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="24728-121">右键单击“系统” ，然后单击“属性” 。</span><span class="sxs-lookup"><span data-stu-id="24728-121">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="24728-122">单击**选项**选项卡。</span><span class="sxs-lookup"><span data-stu-id="24728-122">Click the **Options** tab.</span></span>  
  
5.  <span data-ttu-id="24728-123">清除**启用主机启动的 SSO**框中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="24728-123">Clear the **Enable host initiated SSO** box, and click **OK**.</span></span>  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a><span data-ttu-id="24728-124">使用命令行禁用主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="24728-124">To disable host initiated SSO using the command line</span></span>  
  
1.  <span data-ttu-id="24728-125">在 **“开始”** 菜单上，单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="24728-125">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="24728-126">在中**运行**对话框中，键入**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="24728-126">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="24728-127">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="24728-127">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="24728-128">默认值是\<驱动器\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="24728-128">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="24728-129">类型**ssomanage-禁用 hisso**根据需要。</span><span class="sxs-lookup"><span data-stu-id="24728-129">Type **ssomanage -disable hisso** as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="24728-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="24728-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24728-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="24728-131">See Also</span></span>  
 [<span data-ttu-id="24728-132">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="24728-132">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)