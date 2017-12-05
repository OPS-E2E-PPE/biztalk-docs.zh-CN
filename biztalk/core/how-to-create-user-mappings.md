---
title: "如何创建用户映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019adf0cd41c643ac77790c96a3450bb967ddd6b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="ee30a-102">如何创建用户映射</span><span class="sxs-lookup"><span data-stu-id="ee30a-102">How to Create User Mappings</span></span>
<span data-ttu-id="ee30a-103">使用此命令创建一个或多个用户映射，按照指定的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="ee30a-103">Use this command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="ee30a-104">下面是示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="ee30a-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="ee30a-105">如果更改用户帐户，你必须使用此命令创建新的用户帐户的映射。</span><span class="sxs-lookup"><span data-stu-id="ee30a-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="ee30a-106">你还应删除旧的用户映射。</span><span class="sxs-lookup"><span data-stu-id="ee30a-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="ee30a-107">有关删除映射的详细信息，请参阅[如何删除用户映射](../core/how-to-delete-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="ee30a-107">For more information about removing a mapping, see [How to Delete User Mappings](../core/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="ee30a-108">创建用户映射后，你必须启用它，然后才能使用此映射 SSO 系统中。</span><span class="sxs-lookup"><span data-stu-id="ee30a-108">After you create a user mapping, you must enable it before you can use this mapping in the SSO system.</span></span> <span data-ttu-id="ee30a-109">有关详细信息，请参阅[如何启用用户映射](../core/how-to-enable-a-user-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="ee30a-109">For more information, see [How to Enable a User Mapping](../core/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee30a-110">用户映射支持仅域组。</span><span class="sxs-lookup"><span data-stu-id="ee30a-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="ee30a-111">若要创建使用管理实用程序的用户映射</span><span class="sxs-lookup"><span data-stu-id="ee30a-111">To create user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="ee30a-112">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="ee30a-112">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="ee30a-113">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="ee30a-113">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ee30a-114">默认安装目录是\<*驱动器*\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="ee30a-114">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="ee30a-115">类型**ssomanage-createmappings *\<映射文件名\>***，其中*\<映射文件名\>*是包含你想要创建用户映射的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ee30a-115">Type **ssomanage –createmappings *\<mappings file name\>***, where *\<mappings file name\>* is the name of file that contains the user mapping(s) you want to create.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ee30a-116">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="ee30a-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="ee30a-117">若要创建使用客户端实用工具的用户映射</span><span class="sxs-lookup"><span data-stu-id="ee30a-117">To create user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="ee30a-118">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="ee30a-118">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="ee30a-119">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="ee30a-119">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="ee30a-120">默认安装目录是\<*驱动器*\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="ee30a-120">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="ee30a-121">类型**ssoclient – setcredentials *\<应用程序名称\>***  ，其中*\<应用程序名称\>*是用户想要创建的映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="ee30a-121">Type **ssoclient –setcredentials *\<application name \>***, where *\<application name \>* is the name of affiliate application that the user wants to create a mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ee30a-122">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="ee30a-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee30a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee30a-123">See Also</span></span>  
 <span data-ttu-id="ee30a-124">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="ee30a-124">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="ee30a-125">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ee30a-125">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="ee30a-126">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="ee30a-126">Managing User Mappings</span></span>](../core/managing-user-mappings.md)