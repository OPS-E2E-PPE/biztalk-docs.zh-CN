---
title: "如何启用关联应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], enabling
- managing [SSO applications], enabling
- enabling, applications [SSO]
ms.assetid: 81c94e1b-cd3d-482e-9a78-9b1476af9e5f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2e0d03b233ffdf6bc0db759133062928aa22ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="5793c-102">如何启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="5793c-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="5793c-103">可以使用 MMC 管理单元或命令行来启用指定的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="5793c-103">You can use the MMC Snap-In or the command line to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="5793c-104">使用 MMC 管理单元启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="5793c-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="5793c-105">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="5793c-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="5793c-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="5793c-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="5793c-107">右键单击 affililate 应用程序，并依次**启用**。</span><span class="sxs-lookup"><span data-stu-id="5793c-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="5793c-108">使用命令行启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="5793c-108">To enable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="5793c-109">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="5793c-109">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="5793c-110">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="5793c-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="5793c-111">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="5793c-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="5793c-112">类型**ssomanage-enableapp *\<应用程序名称 >***，其中\<*应用程序名称*> 是的关联应用程序的名称你想要启用。</span><span class="sxs-lookup"><span data-stu-id="5793c-112">Type **ssomanage –enableapp *\<application name>***, where \<*application name*> is the name of the affiliate application you want to enable.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5793c-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="5793c-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5793c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5793c-114">See Also</span></span>  
 <span data-ttu-id="5793c-115">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="5793c-115">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="5793c-116">[如何创建关联应用程序](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="5793c-116">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="5793c-117">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="5793c-117">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="5793c-118">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="5793c-118">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)