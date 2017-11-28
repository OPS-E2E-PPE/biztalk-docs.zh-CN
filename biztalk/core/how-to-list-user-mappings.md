---
title: "如何列出用户映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO maps], listing maps
- maps [SSO], listing maps
ms.assetid: f9b73785-3a59-45c8-9e88-d2d16b5a46aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f6041b40c2b6a3fa468462478754079d41881bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-user-mappings"></a><span data-ttu-id="be4ad-102">如何列出用户映射</span><span class="sxs-lookup"><span data-stu-id="be4ad-102">How to List User Mappings</span></span>
<span data-ttu-id="be4ad-103">使用此命令可以列出指定用户的所有现有映射。</span><span class="sxs-lookup"><span data-stu-id="be4ad-103">Use this command to list all the existing mappings for the specified user.</span></span>  
  
 <span data-ttu-id="be4ad-104">只有 SSO 管理员、应用程序管理员、SSO 关联管理员或用户才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="be4ad-104">You must be an SSO administrator, application administrator, SSO affiliate administrator, or user to do this task.</span></span>  
  
 <span data-ttu-id="be4ad-105">启用的用户映射显示为 (E) \<*域*>\\*\<用户名 >*，而禁用用户映射显示为 (D) \<*域*>\\*\<用户名 >*。</span><span class="sxs-lookup"><span data-stu-id="be4ad-105">Enabled user mappings appear as (E) \<*domain*>\\*\<username>*, while disabled user mappings appear as (D) \<*domain*>\\*\<username>*.</span></span>  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a><span data-ttu-id="be4ad-106">使用管理实用工具列出用户映射</span><span class="sxs-lookup"><span data-stu-id="be4ad-106">To list user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="be4ad-107">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="be4ad-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="be4ad-108">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="be4ad-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="be4ad-109">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="be4ad-109">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="be4ad-110">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="be4ad-110">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="be4ad-111">类型**ssomanage-listmappings *\<域 >\\< 用户名\>*** 若要列出给定的用户有他/她所属关联应用程序中的所有映射指向的位置*\<域 >*是用户帐户的 Microsoft Windows 域和*\<用户名 >*是你要列出的 Windows 用户名称用户映射。</span><span class="sxs-lookup"><span data-stu-id="be4ad-111">Type **ssomanage –listmappings *\<domain>\\<username\>*** to list all the mappings a given user has in the affiliate applications he/she belongs to, where *\<domain>* is the Microsoft Windows domain for the user account, and *\<username>* is the Windows user name for which you want to list the user mappings.</span></span> <span data-ttu-id="be4ad-112">如果用户是关联管理员或 SSO 管理员，此命令将列出该用户在所有关联应用程序中的所有映射。</span><span class="sxs-lookup"><span data-stu-id="be4ad-112">If the user is an Affiliate Administrator or an SSO Administrator, this command will list all the mappings for that user in all the affiliate applications.</span></span>  
  
         <span data-ttu-id="be4ad-113">或</span><span class="sxs-lookup"><span data-stu-id="be4ad-113">Or</span></span>  
  
    -   <span data-ttu-id="be4ad-114">类型**ssomanage-listmappings *\<应用程序名称 >*** 若要列出给定应用程序的所有用户映射。</span><span class="sxs-lookup"><span data-stu-id="be4ad-114">Type **ssomanage –listmappings *\<application name>*** to list all the user mappings for a given application.</span></span>  
  
         <span data-ttu-id="be4ad-115">或</span><span class="sxs-lookup"><span data-stu-id="be4ad-115">Or</span></span>  
  
    -   <span data-ttu-id="be4ad-116">如果你是应用程序管理员，请键入**ssomanage-listmappings *\<域 >\\< 用户名\>* *\<应用程序名称 >*** 列出所有映射给定的用户具有在您是管理员关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="be4ad-116">If you are an application administrator, type **ssomanage –listmappings *\<domain>\\<username\>* *\<application name>*** to list all the mappings a given user has in the affiliate applications for which you are an administrator.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be4ad-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="be4ad-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a><span data-ttu-id="be4ad-118">使用客户端实用工具列出用户映射</span><span class="sxs-lookup"><span data-stu-id="be4ad-118">To list user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="be4ad-119">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="be4ad-119">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="be4ad-120">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="be4ad-120">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="be4ad-121">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="be4ad-121">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="be4ad-122">类型**ssoclient – listmappings**若要列出所有必须的映射。</span><span class="sxs-lookup"><span data-stu-id="be4ad-122">Type **ssoclient –listmappings** to list all the mappings you have.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be4ad-123">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="be4ad-123">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4ad-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be4ad-124">See Also</span></span>  
 <span data-ttu-id="be4ad-125">[如何创建用户映射](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="be4ad-125">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="be4ad-126">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="be4ad-126">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="be4ad-127">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="be4ad-127">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="be4ad-128">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="be4ad-128">Managing User Mappings</span></span>](../core/managing-user-mappings.md)