---
title: 如何启用用户映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enabling, user maps [SSO]
- maps [SSO], enabling
- managing [SSO maps], enabling
ms.assetid: 0f6448c9-944e-45f6-9436-87a4f3743498
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfd87d300314616fe05a033360d84f5d2eb8b8cd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970827"
---
# <a name="how-to-enable-a-user-mapping"></a><span data-ttu-id="1cd85-102">如何启用用户映射</span><span class="sxs-lookup"><span data-stu-id="1cd85-102">How to Enable a User Mapping</span></span>
<span data-ttu-id="1cd85-103">必须首先启用用户映射，然后才能在单一登录系统中使用该映射。</span><span class="sxs-lookup"><span data-stu-id="1cd85-103">You must enable a user mapping before it you can use the mapping in the Single Sign-On system.</span></span>  
  
 <span data-ttu-id="1cd85-104">当你启用的用户映射时，它将显示为 (E) **\<域\>\\< 用户名\>** 时列出的用户映射。</span><span class="sxs-lookup"><span data-stu-id="1cd85-104">When you enable a user mapping, it will appear as (E) **\<domain\>\\<username\>** when you list the user mappings.</span></span>  
  
 <span data-ttu-id="1cd85-105">注意，如果已使用 -setcredentials 命令设置了凭据，则将已启用了映射。</span><span class="sxs-lookup"><span data-stu-id="1cd85-105">Note that if you have set the credentials using the -setcredentials command, the mapping will already be enabled.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="1cd85-106">使用管理实用工具启用用户映射</span><span class="sxs-lookup"><span data-stu-id="1cd85-106">To enable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="1cd85-107">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="1cd85-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1cd85-108">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1cd85-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1cd85-109">默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1cd85-109">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1cd85-110">类型**ssomanage-enablemapping\<域\>\\< 用户名\>\<应用程序名称\>**，其中 **\<域\>** 是用户帐户的 Windows 域**\<用户名\>** 是你想要启用凭据，并选择的Windows用户名**\<应用程序名称\>** 是你想要删除的用户映射，然后按 ENTER 关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="1cd85-110">Type **ssomanage –enablemapping \<domain\>\\<username\>\<application name\>**, where **\<domain\>** is the Windows domain for the user account, **\<username\>** is the Windows user name for which you want to enable the credentials, and **\<application name\>** is the name of the affiliate application you want to remove the user mapping for and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1cd85-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1cd85-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="1cd85-112">使用客户端实用工具启用用户映射</span><span class="sxs-lookup"><span data-stu-id="1cd85-112">To enable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="1cd85-113">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="1cd85-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="1cd85-114">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="1cd85-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="1cd85-115">默认安装目录是**\<驱动器\>**: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="1cd85-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="1cd85-116">类型**ssoclient – enablemapping\<应用程序名称\>**，其中**\<应用程序名称\>** 是关联的应用程序所需的名称若要删除的用户映射。</span><span class="sxs-lookup"><span data-stu-id="1cd85-116">Type **ssoclient –enablemapping \<application name\>**, where **\<application name\>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1cd85-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="1cd85-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd85-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cd85-118">See Also</span></span>  
 <span data-ttu-id="1cd85-119">[如何创建用户映射](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1cd85-119">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="1cd85-120">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="1cd85-120">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="1cd85-121">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="1cd85-121">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="1cd85-122">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="1cd85-122">Managing User Mappings</span></span>](../core/managing-user-mappings.md)