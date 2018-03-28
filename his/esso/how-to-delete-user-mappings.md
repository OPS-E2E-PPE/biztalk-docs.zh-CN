---
title: 如何删除用户映射 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c4cdff-b82d-4cfd-8e20-220a2fe78656
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: a9d0a31c3dbc9d5980f59d9f30d20ec15f603a38
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-delete-user-mappings"></a><span data-ttu-id="1c59f-102">如何删除用户映射</span><span class="sxs-lookup"><span data-stu-id="1c59f-102">How to Delete User Mappings</span></span>
<span data-ttu-id="1c59f-103">使用这些命令来删除一个或多个用户映射，按照指定的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="1c59f-103">Use these commands to delete one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="1c59f-104">下面是示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="1c59f-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="1c59f-105">如果用户不是 Application Users 帐户的成员或 Active Directory 中不存在，你应使用此命令从凭据数据库中删除的用户映射。</span><span class="sxs-lookup"><span data-stu-id="1c59f-105">If a user is not a member of the Application Users account, or does not exist in Active Directory, you should use this command to remove the user mapping from the Credential database.</span></span>  
  
 <span data-ttu-id="1c59f-106">如果更改用户帐户，你必须使用此命令删除的旧的用户映射，然后创建新的用户帐户的新用户映射。</span><span class="sxs-lookup"><span data-stu-id="1c59f-106">If a user account is changed, you must use this command to remove the old user mapping, and then create a new user mapping for the new user account.</span></span> <span data-ttu-id="1c59f-107">有关创建一个映射的详细信息，请参阅[如何创建用户映射](../esso/how-to-create-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="1c59f-107">For more information about creating a mapping, see [How to Create User Mappings](../esso/how-to-create-user-mappings.md).</span></span>  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a><span data-ttu-id="1c59f-108">若要删除使用管理实用程序的用户映射</span><span class="sxs-lookup"><span data-stu-id="1c59f-108">To delete user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="1c59f-109">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="1c59f-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1c59f-110">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1c59f-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1c59f-111">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1c59f-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1c59f-112">类型`ssomanage –deletemappings <mappings file name>`，其中\<*映射文件名*> 是包含你想要删除的用户映射的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1c59f-112">Type `ssomanage –deletemappings <mappings file name>`, where \<*mappings file name*> is the name of the file that contains the user mappings that you want to delete.</span></span>  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a><span data-ttu-id="1c59f-113">若要删除特定用户映射使用管理实用工具</span><span class="sxs-lookup"><span data-stu-id="1c59f-113">To delete a specific user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="1c59f-114">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="1c59f-114">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1c59f-115">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1c59f-115">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1c59f-116">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1c59f-116">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1c59f-117">类型`ssomanage –deletemapping <domain>\<username> <application name>`，其中*\<域 >*是用户帐户的 Windows 域*\<用户名 >*是 Windows 用户名称，并\< *应用程序名称*> 是你想要删除的用户映射的特定应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c59f-117">Type `ssomanage –deletemapping <domain>\<username> <application name>`, where *\<domain>* is the Windows domain for the user account, *\<username>* is the Windows user name, and \<*application name*> is the specific application for which you want to remove the user mapping.</span></span>  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="1c59f-118">若要删除使用客户端实用工具的用户映射</span><span class="sxs-lookup"><span data-stu-id="1c59f-118">To delete a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="1c59f-119">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="1c59f-119">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="1c59f-120">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1c59f-120">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="1c59f-121">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1c59f-121">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1c59f-122">类型`ssoclient –deletemapping <application name>`，其中*\<应用程序名称 >*是你想要删除的用户映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="1c59f-122">Type `ssoclient –deletemapping <application name>`, where *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c59f-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c59f-123">See Also</span></span>  
 <span data-ttu-id="1c59f-124">[SSO 映射](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1c59f-124">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="1c59f-125">[管理关联应用程序](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1c59f-125">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="1c59f-126">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="1c59f-126">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)