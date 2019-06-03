---
title: 如何启用 SSO |Microsoft Docs
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 863a17fc08ea09b79dc89ecb4a285c9cf7aa2d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385094"
---
# <a name="how-to-enable-sso"></a><span data-ttu-id="38986-102">如何启用 SSO</span><span class="sxs-lookup"><span data-stu-id="38986-102">How to Enable SSO</span></span>
<span data-ttu-id="38986-103">可以通过使用 MMC 管理单元或命令行启用整个企业单一登录 (SSO) 系统。</span><span class="sxs-lookup"><span data-stu-id="38986-103">You can enable the entire Enterprise Single Sign-On (SSO) system by using either the MMC Snap-In or the command line.</span></span>  
  
 <span data-ttu-id="38986-104">在运行启用命令后，没有一个短暂的延迟之前启用了所有单一登录服务器，因为每个轮询 SSO 数据库的最新的全局信息。</span><span class="sxs-lookup"><span data-stu-id="38986-104">After you run the enabling command, there is a short delay before all Single Sign-On Servers are enabled, as each polls the SSO database for the latest global information.</span></span>  
  
 <span data-ttu-id="38986-105">如果你想要在 SSO 系统中配置关联应用程序和映射，您还必须创建关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="38986-105">If you want to configure affiliate applications and mappings in the SSO system, you must also create an affiliate application.</span></span> <span data-ttu-id="38986-106">SSO 关联之后管理员创建关联应用程序、 应用程序管理员可以对其进行更改和应用程序用户 （最终用户） 可以创建他们自己的映射。</span><span class="sxs-lookup"><span data-stu-id="38986-106">After an SSO affiliate administrator creates an affiliate application, an application administrator can make changes to it, and application users (end-users) can create their own mappings.</span></span> <span data-ttu-id="38986-107">有关详细信息，请参阅[管理关联应用程序](../core/managing-affiliate-applications.md)并[管理用户映射](../core/managing-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="38986-107">For more information, see [Managing Affiliate Applications](../core/managing-affiliate-applications.md) and [Managing User Mappings](../core/managing-user-mappings.md).</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a><span data-ttu-id="38986-108">若要启用 SSO 系统 MMC 管理单元中使用</span><span class="sxs-lookup"><span data-stu-id="38986-108">To enable the SSO system using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="38986-109">单击**启动**，单击**所有程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="38986-109">Click **Start**, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="38986-110">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="38986-110">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="38986-111">右键单击**系统**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="38986-111">Right-click **System**, and then click **Enable**.</span></span>  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a><span data-ttu-id="38986-112">若要启用 SSO 系统使用命令行</span><span class="sxs-lookup"><span data-stu-id="38986-112">To enable the SSO system using the command line</span></span>  
  
1.  <span data-ttu-id="38986-113">依次单击 **“开始”** 和 **“运行”**，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="38986-113">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="38986-114">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="38986-114">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="38986-115">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="38986-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="38986-116">类型**ssomanage – enablesso**。</span><span class="sxs-lookup"><span data-stu-id="38986-116">Type **ssomanage –enablesso**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="38986-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="38986-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a><span data-ttu-id="38986-118">若要启用 SSO 创建关联应用程序和映射</span><span class="sxs-lookup"><span data-stu-id="38986-118">To enable SSO to create affiliate applications and mappings</span></span>  
  
1. <span data-ttu-id="38986-119">SSO 管理员或 SSO 关联管理员到 SSO 服务器，以登录或 SSO 的 SSO 管理辅助服务具有一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="38986-119">Log on as an SSO administrator or SSO affiliate administrator to the SSO Server, or on a computer that has the SSO administration sub services of SSO.</span></span>  
  
2. <span data-ttu-id="38986-120">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="38986-120">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
3. <span data-ttu-id="38986-121">在命令行提示符下，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="38986-121">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="38986-122">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="38986-122">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
4. <span data-ttu-id="38986-123">类型**ssomanage enablesso**启用企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="38986-123">Type **ssomanage -enablesso** to enable the Enterprise Single Sign-On service.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="38986-124">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="38986-124">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
5. <span data-ttu-id="38986-125">作为 SSO 关联管理员身份登录。</span><span class="sxs-lookup"><span data-stu-id="38986-125">Log on as an SSO affiliate administrator.</span></span>  
  
6. <span data-ttu-id="38986-126">类型**ssomanage-createapps *\<应用程序文件\>*** 创建关联应用程序，其中\<应用程序文件\>是 XML 文件包含关联应用程序的定义的。</span><span class="sxs-lookup"><span data-stu-id="38986-126">Type **ssomanage -createapps *\<application file\>*** to create an affiliate application, where \<application file\> is the XML file that contains definitions for the affiliate applications.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="38986-127">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="38986-127">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38986-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="38986-128">See Also</span></span>  
 <span data-ttu-id="38986-129">[如何设置 SSO 服务器](../core/how-to-set-the-sso-server.md) </span><span class="sxs-lookup"><span data-stu-id="38986-129">[How to Set the SSO Server](../core/how-to-set-the-sso-server.md) </span></span>  
 <span data-ttu-id="38986-130">[如何禁用 SSO](../core/how-to-disable-sso.md) </span><span class="sxs-lookup"><span data-stu-id="38986-130">[How to Disable SSO](../core/how-to-disable-sso.md) </span></span>  
 <span data-ttu-id="38986-131">[如何更新 SSO 数据库](../core/how-to-update-the-sso-database.md) </span><span class="sxs-lookup"><span data-stu-id="38986-131">[How to Update the SSO Database](../core/how-to-update-the-sso-database.md) </span></span>  
 [<span data-ttu-id="38986-132">使用 SSO</span><span class="sxs-lookup"><span data-stu-id="38986-132">Using SSO</span></span>](../core/using-sso.md)