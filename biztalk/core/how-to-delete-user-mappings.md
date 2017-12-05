---
title: "如何删除用户映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], deleting
- managing [SSO maps], deleting user maps
ms.assetid: de511113-b0b0-4920-91dc-4c9e380fda58
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03f7c1fa75b6fe7bb4c78e18c97fccd1404f89c9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-delete-user-mappings"></a><span data-ttu-id="27f14-102">如何删除用户映射</span><span class="sxs-lookup"><span data-stu-id="27f14-102">How to Delete User Mappings</span></span>
<span data-ttu-id="27f14-103">使用这些命令来删除一个或多个用户映射，按照指定的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="27f14-103">Use these commands to delete one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="27f14-104">下面是示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="27f14-104">The following is an example XML file.</span></span>  
  
```  
<sso>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name1</externalApplication>   
<externalUserId>App1UserName</externalUserId>   
</mapping>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name2</externalApplication>   
<externalUserId>App2UserName</externalUserId>   
</mapping>  
</sso>  
```  
  
 <span data-ttu-id="27f14-105">如果用户不是 Application Users 帐户的成员或 Active Directory 中不存在，你应使用此命令从 SSO 数据库中删除的用户映射。</span><span class="sxs-lookup"><span data-stu-id="27f14-105">If a user is not a member of the Application Users account, or does not exist in Active Directory, you should use this command to remove the user mapping from the SSO database.</span></span>  
  
 <span data-ttu-id="27f14-106">如果更改用户帐户，你必须使用此命令删除的旧的用户映射，然后创建新的用户帐户的新用户映射。</span><span class="sxs-lookup"><span data-stu-id="27f14-106">If a user account is changed, you must use this command to remove the old user mapping, and then create a new user mapping for the new user account.</span></span> <span data-ttu-id="27f14-107">有关创建一个映射的详细信息，请参阅[如何创建用户映射](../core/how-to-create-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="27f14-107">For more information about creating a mapping, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a><span data-ttu-id="27f14-108">若要删除使用管理实用程序的用户映射</span><span class="sxs-lookup"><span data-stu-id="27f14-108">To delete user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="27f14-109">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="27f14-109">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="27f14-110">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="27f14-110">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="27f14-111">默认安装目录是\<*驱动器*\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="27f14-111">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="27f14-112">类型**ssomanage-deletemappings *\<映射文件名\>***，其中\<*映射文件名*\>是包含你想要删除用户映射的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="27f14-112">Type **ssomanage –deletemappings *\<mappings file name\>***, where \<*mappings file name*\> is the name of the file that contains the user mapping(s) you want to delete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27f14-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="27f14-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a><span data-ttu-id="27f14-114">若要删除特定用户映射使用管理实用工具</span><span class="sxs-lookup"><span data-stu-id="27f14-114">To delete a specific user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="27f14-115">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="27f14-115">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="27f14-116">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="27f14-116">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="27f14-117">默认安装目录是*\<驱动器*\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="27f14-117">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="27f14-118">类型 **ssomanage-deletemapping *\<域\>*\\*\<用户名\>* *\<应用程序名称\>***，其中*\<域\>*是用户帐户的 Windows 域*\<用户名\>*是 Windows 用户名称，并\<*应用程序名称*\>是所需的特定应用程序删除的用户映射。</span><span class="sxs-lookup"><span data-stu-id="27f14-118">Type **ssomanage –deletemapping *\<domain\>*\\*\<username\>* *\<application name\>***, where *\<domain\>* is the Windows domain for the user account, *\<username\>* is the Windows user name, and \<*application name*\> is the specific application for which you want to remove the user mapping.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27f14-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="27f14-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="27f14-120">若要删除使用客户端实用工具的用户映射</span><span class="sxs-lookup"><span data-stu-id="27f14-120">To delete a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="27f14-121">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="27f14-121">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="27f14-122">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="27f14-122">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="27f14-123">默认安装目录是*\<驱动器*\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="27f14-123">The default installation directory is *\<drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="27f14-124">类型**ssoclient – deletemapping *\<应用程序名称\>***，其中*\<应用程序名称\>*是你想要删除的用户映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="27f14-124">Type **ssoclient –deletemapping *\<application name\>***, where *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27f14-125">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="27f14-125">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f14-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27f14-126">See Also</span></span>  
 <span data-ttu-id="27f14-127">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="27f14-127">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="27f14-128">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="27f14-128">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="27f14-129">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="27f14-129">Managing User Mappings</span></span>](../core/managing-user-mappings.md)