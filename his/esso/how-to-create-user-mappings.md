---
title: 如何创建用户映射 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb91879c-73f4-4e9e-9e5b-534f48cd5584
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 89fd7ab2ca83d23a37944447997becd2d3f008c2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250961"
---
# <a name="how-to-create-user-mappings"></a><span data-ttu-id="d1102-102">如何创建用户映射</span><span class="sxs-lookup"><span data-stu-id="d1102-102">How to Create User Mappings</span></span>
<span data-ttu-id="d1102-103">使用**createmappings**命令以创建一个或多个用户映射，按照指定的 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="d1102-103">Use the **createmappings** command to create one or more user mappings, as specified in the XML file.</span></span> <span data-ttu-id="d1102-104">下面是示例 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d1102-104">The following is an example XML file.</span></span>  
  
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
  
 <span data-ttu-id="d1102-105">如果更改用户帐户，你必须使用此命令创建新的用户帐户的映射。</span><span class="sxs-lookup"><span data-stu-id="d1102-105">If a user account is changed, you must use this command to create a mapping for the new user account.</span></span> <span data-ttu-id="d1102-106">你还应删除旧的用户映射。</span><span class="sxs-lookup"><span data-stu-id="d1102-106">You should also remove the old user mapping.</span></span> <span data-ttu-id="d1102-107">有关删除映射的详细信息，请参阅[如何删除用户映射](../esso/how-to-delete-user-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="d1102-107">For more information about removing a mapping, see [How to Delete User Mappings](../esso/how-to-delete-user-mappings.md).</span></span>  
  
 <span data-ttu-id="d1102-108">创建用户映射后，你必须启用它，然后才能在单一登录 (SSO) 系统中使用此映射。</span><span class="sxs-lookup"><span data-stu-id="d1102-108">After you create a user mapping, you must enable it before you can use this mapping in the Single Sign-On (SSO) system.</span></span> <span data-ttu-id="d1102-109">有关详细信息，请参阅[如何启用用户映射](../esso/how-to-enable-a-user-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="d1102-109">For more information, see [How to Enable a User Mapping](../esso/how-to-enable-a-user-mapping.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d1102-110">用户映射支持仅域组。</span><span class="sxs-lookup"><span data-stu-id="d1102-110">Only domain groups are supported for user mappings.</span></span>  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a><span data-ttu-id="d1102-111">若要创建使用管理实用程序的用户映射</span><span class="sxs-lookup"><span data-stu-id="d1102-111">To create user mappings using the administration utility</span></span>  
  
1.  <span data-ttu-id="d1102-112">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="d1102-112">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="d1102-113">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d1102-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="d1102-114">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="d1102-114">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d1102-115">类型`ssomanage –createmappings <mappings file name>`，其中*\<映射文件名称 >* 是包含你想要创建的用户映射的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="d1102-115">Type `ssomanage –createmappings <mappings file name>`, where *\<mappings file name>* is the name of the file that contains the user mappings that you want to create.</span></span>  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a><span data-ttu-id="d1102-116">若要创建使用客户端实用工具的用户映射</span><span class="sxs-lookup"><span data-stu-id="d1102-116">To create user mappings using the client utility</span></span>  
  
1.  <span data-ttu-id="d1102-117">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="d1102-117">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="d1102-118">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="d1102-118">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="d1102-119">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="d1102-119">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="d1102-120">类型`ssoclient –setcredentials <application name >`，其中*\<应用程序名称 >* 是用户想要创建的映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="d1102-120">Type `ssoclient –setcredentials <application name >`, where *\<application name >* is the name of the affiliate application that the user wants to create a mapping for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1102-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1102-121">See Also</span></span>  
 <span data-ttu-id="d1102-122">[SSO 映射](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d1102-122">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="d1102-123">[管理关联应用程序](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="d1102-123">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="d1102-124">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="d1102-124">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)