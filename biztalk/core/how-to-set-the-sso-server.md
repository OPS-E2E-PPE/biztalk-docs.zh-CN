---
title: "如何设置 SSO 服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, selecting [SSO]
- SSO, selecting servers
- managing [SSO], selecting servers
- SSOManage [SSO]
ms.assetid: a0b0176d-b426-4ab1-8a7e-1f96f4214683
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96631531cc28ac1bed4ea2b2b56b4b8f9b80c281
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-sso-server"></a><span data-ttu-id="95668-102">如何设置 SSO 服务器</span><span class="sxs-lookup"><span data-stu-id="95668-102">How to Set the SSO Server</span></span>
<span data-ttu-id="95668-103">每次使用 ssomanage 时，必须先将用户指向您要连接的单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="95668-103">Each time you use ssomanage, you must first point the user to the Single Sign-On server you want to connect to.</span></span>  
  
 <span data-ttu-id="95668-104">可以通过两种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="95668-104">You can do this in one of two ways:</span></span>  
  
-   <span data-ttu-id="95668-105">各用户可以自己指向正确的单一登录服务器。</span><span class="sxs-lookup"><span data-stu-id="95668-105">Individual users can point themselves to the correct Single Sign-On Server.</span></span>  
  
-   <span data-ttu-id="95668-106">单一登录服务器的本地计算机管理员可以将 Single Sign-On Users 帐户的所有成员指向此服务器。</span><span class="sxs-lookup"><span data-stu-id="95668-106">A local computer administrator for the Single Sign-On server can point all the members of the Single Sign-On Users account to this server.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a><span data-ttu-id="95668-107">使用 MMC 管理单元设置企业单一登录服务器</span><span class="sxs-lookup"><span data-stu-id="95668-107">To set the Enterprise Single Sign-On Server using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="95668-108">单击**启动**，单击**所有程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="95668-108">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="95668-109">在 MMC 管理单元中下**控制台根节点**，右键单击**企业单一登录**，然后单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="95668-109">In the MMC Snap-In under the **Console Root**, right-click **Enterprise Single Sign-On**, and click **Select**.</span></span>  
  
3.  <span data-ttu-id="95668-110">浏览到所需服务器。</span><span class="sxs-lookup"><span data-stu-id="95668-110">Browse to the desired server.</span></span>  
  
4.  <span data-ttu-id="95668-111">根据需要选择**设置 SSO 服务器的所有用户**复选框。</span><span class="sxs-lookup"><span data-stu-id="95668-111">If appropriate, select the **Set SSO Server for all users** check box.</span></span>  
  
5.  <span data-ttu-id="95668-112">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="95668-112">Click **OK**.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a><span data-ttu-id="95668-113">若要为单个用户使用命令行设置企业单一登录服务器</span><span class="sxs-lookup"><span data-stu-id="95668-113">To set the Enterprise Single Sign-On Server for a single user using the command line</span></span>  
  
1.  <span data-ttu-id="95668-114">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="95668-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="95668-115">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="95668-115">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="95668-116">默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="95668-116">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="95668-117">类型**ssomanage-服务器\<SSO 服务器名 >**，其中 **\<SSO 服务器名 >**是用户想要连接到单一登录服务器的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="95668-117">Type **ssomanage –server \<SSO server name>**, where **\<SSO server name>** is the computer name of the Single Sign-On Server the user wants to connect to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95668-118">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="95668-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a><span data-ttu-id="95668-119">若要使用命令行的所有用户都设置企业单一登录服务器</span><span class="sxs-lookup"><span data-stu-id="95668-119">To set the Enterprise Single Sign-On Server for all users using the command line</span></span>  
  
1.  <span data-ttu-id="95668-120">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="95668-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="95668-121">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="95668-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="95668-122">默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="95668-122">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="95668-123">类型**ssomanage-serverall \<SSO 服务器名 >**，其中 **\<SSO 服务器名 >**是单一登录在用户的所有成员的单一登录服务器的计算机名称将指向帐户。</span><span class="sxs-lookup"><span data-stu-id="95668-123">Type **ssomanage –serverall \<SSO server name>**, where **\<SSO server name>** is the computer name of the Single Sign-On Server all members of the Single Sign-On Users account will be pointed to.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95668-124">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="95668-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a><span data-ttu-id="95668-125">若要确定企业单一登录到用户所连接的服务器使用命令行</span><span class="sxs-lookup"><span data-stu-id="95668-125">To determine the Enterprise Single Sign-On Server to which a user is connected using the command line</span></span>  
  
1.  <span data-ttu-id="95668-126">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="95668-126">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="95668-127">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="95668-127">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="95668-128">默认安装目录是**\<驱动器 >**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="95668-128">The default installation directory is **\<drive>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="95668-129">类型**ssomanage-showserver**。</span><span class="sxs-lookup"><span data-stu-id="95668-129">Type **ssomanage –showserver**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95668-130">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="95668-130">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95668-131">此命令显示当前用户以及其他用户（如果存在）的设置。</span><span class="sxs-lookup"><span data-stu-id="95668-131">This command displays the settings for the current user as well as for other users if they exist.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95668-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95668-132">See Also</span></span>  
 <span data-ttu-id="95668-133">[如何启用 SSO](../core/how-to-enable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="95668-133">[How to Enable SSO](../core/how-to-enable-sso.md) </span></span>  
 <span data-ttu-id="95668-134">[如何禁用 SSO](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="95668-134">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="95668-135">[如何显示的 SSO 数据库信息](../core/how-to-display-the-sso-database-information.md) </span><span class="sxs-lookup"><span data-stu-id="95668-135">[How to Display the SSO Database Information](../core/how-to-display-the-sso-database-information.md) </span></span>  
 [<span data-ttu-id="95668-136">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="95668-136">Using SSO</span></span>](../core/using-sso.md)