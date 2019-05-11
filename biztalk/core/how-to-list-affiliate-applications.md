---
title: 如何列出关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], listing applications
- applications [SSO], listing applications
ms.assetid: b51ff597-824e-4488-a47f-3a9b3d4437c6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b254be21078a53f7efa7291606bdd0038466bb3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336933"
---
# <a name="how-to-list-affiliate-applications"></a><span data-ttu-id="d3891-102">如何列出关联应用程序</span><span class="sxs-lookup"><span data-stu-id="d3891-102">How to List Affiliate Applications</span></span>
<span data-ttu-id="d3891-103">使用此命令列出所有关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3891-103">Use this command to list all the affiliate applications.</span></span> <span data-ttu-id="d3891-104">如果用户是应用程序管理员帐户的成员，此命令将仅显示为其用户是管理员的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3891-104">If the user is a member of the Application Administrators account, this command will only display the application for which the user is an administrator.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-administration-utility"></a><span data-ttu-id="d3891-105">使用管理实用工具列出关联应用程序</span><span class="sxs-lookup"><span data-stu-id="d3891-105">To list affiliate applications using the administration utility</span></span>  
  
1.  <span data-ttu-id="d3891-106">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="d3891-106">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d3891-107">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d3891-107">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d3891-108">默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="d3891-108">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d3891-109">类型**ssomanage-listapps [all]** 其中**所有**是一个可选参数，还将显示使用的配置存储功能的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3891-109">Type **ssomanage -listapps [all]** where **all** is an optional parameter that will also display applications using the Configuration Store feature.</span></span> <span data-ttu-id="d3891-110">如果运行此命令的用户是应用程序管理员，它将仅列出它们是管理员的应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3891-110">If the user running this command is an Application administrator, it will only list the applications for which they are an administrator.</span></span> <span data-ttu-id="d3891-111">如果运行此命令的用户是关联管理员或 SSO 管理员，它将列出所有关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3891-111">If the user running this command is an Affiliate Administrator or an SSO Administrator, it will list all the affiliate applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3891-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d3891-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-list-affiliate-applications-using-the-client-utility"></a><span data-ttu-id="d3891-113">使用客户端实用工具列出关联应用程序</span><span class="sxs-lookup"><span data-stu-id="d3891-113">To list affiliate applications using the client utility</span></span>  
  
1.  <span data-ttu-id="d3891-114">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="d3891-114">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="d3891-115">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d3891-115">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d3891-116">默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="d3891-116">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d3891-117">类型**ssoclient – listapps**以列出关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3891-117">Type **ssoclient –listapps** to list the affiliate applications.</span></span> <span data-ttu-id="d3891-118">这将列出仅的关联应用程序执行此任务的用户所在的即，它们需要属于该关联应用程序的应用程序用户组帐户。</span><span class="sxs-lookup"><span data-stu-id="d3891-118">This will list only the affiliate applications that the user performing this task is a member of, i.e., they need to belong the application user group account for that affiliate application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3891-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d3891-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3891-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3891-120">See Also</span></span>  
 <span data-ttu-id="d3891-121">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d3891-121">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="d3891-122">[如何创建关联应用程序](../core/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="d3891-122">[How to Create an Affiliate Application](../core/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="d3891-123">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d3891-123">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="d3891-124">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="d3891-124">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)