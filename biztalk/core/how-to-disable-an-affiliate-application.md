---
title: "如何禁用关联应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, applications
- managing [SSO applications], disabling
- applications [SSO], disabling
ms.assetid: febf1687-f0d0-4f87-b462-23535bbddf6d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe1a19ee34a98be4130be2ac72e9ad27e83b0c13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-an-affiliate-application"></a><span data-ttu-id="21748-102">如何禁用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="21748-102">How to Disable an Affiliate Application</span></span>
<span data-ttu-id="21748-103">可以使用 MMC 管理单元或命令行来禁用指定的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="21748-103">You can use the MMC Snap-In or the command line to disable the specified affiliate application.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="21748-104">使用 MMC 管理单元禁用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="21748-104">To disable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="21748-105">上**启动**菜单上，单击**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="21748-105">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="21748-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="21748-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="21748-107">右键单击关联应用程序，并依次**禁用**。</span><span class="sxs-lookup"><span data-stu-id="21748-107">Right-click the affiliate application, and then click **Disable**.</span></span>  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="21748-108">使用命令行禁用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="21748-108">To disable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="21748-109">单击**启动**，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="21748-109">Click **Start**, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="21748-110">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="21748-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="21748-111">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="21748-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="21748-112">类型**ssomanage-disableapp *\<应用程序名称 >***，其中\<*应用程序名称*> 是的关联应用程序的名称你想要禁用。</span><span class="sxs-lookup"><span data-stu-id="21748-112">Type **ssomanage –disableapp *\<application name>***, where \<*application name*> is the name of the affiliate application you want to disable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="21748-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="21748-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21748-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21748-114">See Also</span></span>  
 <span data-ttu-id="21748-115">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="21748-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="21748-116">[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="21748-116">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="21748-117">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="21748-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="21748-118">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="21748-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)