---
title: 如何启用 SSO |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], creating
- SSO, enabling
- maps [SSO], creating
- managing [SSO], enabling
- SSO, maps
- SSO, applications
- creating, applications [SSO]
- managing [SSO], creating affiliate applications
ms.assetid: dda89d15-6b70-4c40-b658-2f6cbdd545c8
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a843c0f6cdea32ba5218140069163058fcd42442
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-sso"></a><span data-ttu-id="05424-102">如何启用 SSO</span><span class="sxs-lookup"><span data-stu-id="05424-102">How to Enable SSO</span></span>
<span data-ttu-id="05424-103">可以通过使用 MMC 管理单元中或命令行启用整个企业单一登录 (SSO) 系统。</span><span class="sxs-lookup"><span data-stu-id="05424-103">You can enable the entire Enterprise Single Sign-On (SSO) system by using either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="05424-104">运行启用命令后，没有一个短暂的延迟之前启用所有单一登录服务器，因为每个轮询 SSO 数据库的最新的全局信息。</span><span class="sxs-lookup"><span data-stu-id="05424-104">After you run the enabling command, there is a short delay before all Single Sign-On Servers are enabled, as each polls the SSO database for the latest global information.</span></span>  
  
 <span data-ttu-id="05424-105">如果你想要配置 SSO 系统中的关联应用程序和映射，你还必须创建关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="05424-105">If you want to configure affiliate applications and mappings in the SSO system, you must also create an affiliate application.</span></span> <span data-ttu-id="05424-106">SSO affiliate 后管理员创建关联应用程序、 应用程序管理员可以对其，进行更改和应用程序用户 （最终用户） 可以创建自己的映射。</span><span class="sxs-lookup"><span data-stu-id="05424-106">After an SSO affiliate administrator creates an affiliate application, an application administrator can make changes to it, and application users (end-users) can create their own mappings.</span></span> <span data-ttu-id="05424-107">有关详细信息，请参阅[管理 Affiliate 应用程序](../core/managing-affiliate-applications.md)和[管理用户映射](../core/managing-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="05424-107">For more information, see [Managing Affiliate Applications](../core/managing-affiliate-applications.md) and [Managing User Mappings](../core/managing-user-mappings.md).</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a><span data-ttu-id="05424-108">若要启用 SSO 系统 MMC 管理单元中使用</span><span class="sxs-lookup"><span data-stu-id="05424-108">To enable the SSO system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="05424-109">单击 **启动**, ，单击 **所有程序**, ，单击 **Microsoft Enterprise 上单一登录**, ，然后单击 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="05424-109">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="05424-110">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="05424-110">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="05424-111">右键单击 **系统**, ，然后单击 **启用**。</span><span class="sxs-lookup"><span data-stu-id="05424-111">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a><span data-ttu-id="05424-112">若要启用 SSO 系统使用命令行</span><span class="sxs-lookup"><span data-stu-id="05424-112">To enable the SSO system using the command line</span></span>  
  
1.  <span data-ttu-id="05424-113">依次单击 **“开始”**和 **“运行”**，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="05424-113">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="05424-114">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="05424-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="05424-115">默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="05424-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="05424-116">类型 **ssomanage-enablesso**。</span><span class="sxs-lookup"><span data-stu-id="05424-116">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05424-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="05424-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a><span data-ttu-id="05424-118">若要启用创建的 SSO affiliate 应用程序和映射</span><span class="sxs-lookup"><span data-stu-id="05424-118">To enable SSO to create affiliate applications and mappings</span></span>  
  
1.  <span data-ttu-id="05424-119">以 SSO administrator 帐户或 SSO 服务器，SSO 关联管理员登录，或者在计算机上具有 SSO 的 SSO 管理子服务。</span><span class="sxs-lookup"><span data-stu-id="05424-119">Log on as an SSO administrator or SSO affiliate administrator to the SSO Server, or on a computer that has the SSO administration sub services of SSO.</span></span>  
  
2.  <span data-ttu-id="05424-120">上 **启动** 菜单上，单击 **运行**, ，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="05424-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3.  <span data-ttu-id="05424-121">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="05424-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="05424-122">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="05424-122">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4.  <span data-ttu-id="05424-123">类型 **ssomanage enablesso** 启用企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="05424-123">Type **ssomanage -enablesso** to enable the Enterprise Single Sign-On service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05424-124">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="05424-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5.  <span data-ttu-id="05424-125">作为 SSO affiliate 管理员登录。</span><span class="sxs-lookup"><span data-stu-id="05424-125">Log on as an SSO affiliate administrator.</span></span>  
  
6.  <span data-ttu-id="05424-126">类型**ssomanage createapps *\<应用程序文件\>*** 创建关联应用程序，其中\<应用程序文件\>是 XML 文件包含关联应用程序的定义。</span><span class="sxs-lookup"><span data-stu-id="05424-126">Type **ssomanage -createapps *\<application file\>*** to create an affiliate application, where \<application file\> is the XML file that contains definitions for the affiliate applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="05424-127">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="05424-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05424-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="05424-128">See Also</span></span>  
 <span data-ttu-id="05424-129">[如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="05424-129">[How to Set the SSO Server](../core/how-to-set-the-sso-server.md) </span></span>  
 <span data-ttu-id="05424-130">[如何禁用 SSO](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="05424-130">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="05424-131">[如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="05424-131">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="05424-132">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="05424-132">Using SSO</span></span>](../core/using-sso.md)