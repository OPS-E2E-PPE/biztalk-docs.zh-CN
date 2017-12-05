---
title: "如何为用户映射设置凭据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4853499dbfd85cd5114212e37f4d22770d64a22
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="1bf8b-102">如何为用户映射设置凭据</span><span class="sxs-lookup"><span data-stu-id="1bf8b-102">How to Set Credentials for a User Mapping</span></span>
<span data-ttu-id="1bf8b-103">使用此命令为用户访问特定的应用程序设置凭据。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-103">Use this command to set the credentials for a user to access a specific application.</span></span>  
  
 <span data-ttu-id="1bf8b-104">在键入密码时，此命令不显示该密码。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-104">This command does not display the password as you type it.</span></span>  
  
 <span data-ttu-id="1bf8b-105">如果用户映射已存在，则此命令将为现有映射设置凭据。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-105">If the user mapping already exists, this command sets the credentials for that existing mapping.</span></span> <span data-ttu-id="1bf8b-106">如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-106">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping"></a><span data-ttu-id="1bf8b-107">为用户映射设置凭据</span><span class="sxs-lookup"><span data-stu-id="1bf8b-107">To set credentials for a user mapping</span></span>  
  
1.  <span data-ttu-id="1bf8b-108">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-108">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1bf8b-109">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-109">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1bf8b-110">默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-110">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1bf8b-111">类型**ssomanage-setcredentials\<域\>\\< 用户名\> \<applicationname\>**，其中 **\<域\>**是用户帐户的 Windows 域**\<用户名\>**是 Windows 用户名称，并 **\<applicationname\>** 是你想要设置的凭据的特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-111">Type **ssomanage –setcredentials \<domain\>\\<username\> \<applicationname\>**, where **\<domain\>** is the Windows domain for the user account, **\<username\>** is the Windows user name, and **\<applicationname\>** is the specific application for which you want to set the credentials for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bf8b-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4.  <span data-ttu-id="1bf8b-113">当 SSO 系统提示您输入用户凭据时，请输入此应用程序的用户密码。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-113">When the SSO system prompts you for the user credentials, enter the user password for this application.</span></span>  
  
5.  <span data-ttu-id="1bf8b-114">如果尚未创建用户映射，则 SSO 系统将提示您输入该应用程序的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-114">If you have not created the user mapping, the SSO system will prompt you for the user ID for the application.</span></span>  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a><span data-ttu-id="1bf8b-115">从客户端实用工具为用户映射设置凭据</span><span class="sxs-lookup"><span data-stu-id="1bf8b-115">To set credentials for a user mapping from the client utility</span></span>  
  
1.  <span data-ttu-id="1bf8b-116">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-116">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1bf8b-117">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-117">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1bf8b-118">默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-118">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1bf8b-119">类型**ssoclient setcredentials\<应用程序名称\>**，其中**\<应用程序名称\>**是关联应用程序的名称你想要删除的用户映射。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-119">Type **ssoclient -setcredentials \<application name\>**, where **\<application name\>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1bf8b-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1bf8b-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf8b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bf8b-121">See Also</span></span>  
 <span data-ttu-id="1bf8b-122">[如何创建用户映射](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1bf8b-122">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="1bf8b-123">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1bf8b-123">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="1bf8b-124">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1bf8b-124">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="1bf8b-125">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="1bf8b-125">Managing User Mappings</span></span>](../core/managing-user-mappings.md)