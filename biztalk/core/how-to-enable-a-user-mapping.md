---
title: 如何启用用户映射 |Microsoft Docs
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
ms.openlocfilehash: 917f3eb2d1438bb53b9a8a583e3985b0843f09b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385136"
---
# <a name="how-to-enable-a-user-mapping"></a><span data-ttu-id="2ea1b-102">如何启用用户映射</span><span class="sxs-lookup"><span data-stu-id="2ea1b-102">How to Enable a User Mapping</span></span>
<span data-ttu-id="2ea1b-103">必须启用用户映射，然后才能在单一登录系统中使用该映射。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-103">You must enable a user mapping before it you can use the mapping in the Single Sign-On system.</span></span>  
  
 <span data-ttu-id="2ea1b-104">启用用户映射时，它将显示为 (E) **\<域\>\\< 用户名\>** 时列出用户映射。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-104">When you enable a user mapping, it will appear as (E) **\<domain\>\\<username\>** when you list the user mappings.</span></span>  
  
 <span data-ttu-id="2ea1b-105">请注意，是否将使用-setcredentials 命令的凭据，该映射将已启用。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-105">Note that if you have set the credentials using the -setcredentials command, the mapping will already be enabled.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="2ea1b-106">若要启用用户映射使用管理实用工具</span><span class="sxs-lookup"><span data-stu-id="2ea1b-106">To enable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="2ea1b-107">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="2ea1b-108">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2ea1b-109">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-109">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="2ea1b-110">类型**ssomanage-enablemapping\<域\>\\< 用户名\>\<应用程序名称\>**，其中 **\<域\>** 是用户帐户的 Windows 域**\<用户名\>** 是 Windows 用户名，你想要启用凭据，并选择**\<应用程序名称\>** 是你想要删除的用户映射，然后按 ENTER 关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-110">Type **ssomanage –enablemapping \<domain\>\\<username\>\<application name\>**, where **\<domain\>** is the Windows domain for the user account, **\<username\>** is the Windows user name for which you want to enable the credentials, and **\<application name\>** is the name of the affiliate application you want to remove the user mapping for and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ea1b-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-enable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="2ea1b-112">若要启用使用客户端实用工具的用户映射</span><span class="sxs-lookup"><span data-stu-id="2ea1b-112">To enable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="2ea1b-113">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="2ea1b-114">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="2ea1b-115">默认安装目录**\<驱动器\>**: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-115">The default installation directory is **\<drive\>**:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="2ea1b-116">类型**ssoclient-enablemapping\<应用程序名称\>**，其中**\<应用程序名称\>** 是所需的关联应用程序的名称若要删除其用户映射。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-116">Type **ssoclient –enablemapping \<application name\>**, where **\<application name\>** is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ea1b-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="2ea1b-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ea1b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ea1b-118">See Also</span></span>  
 <span data-ttu-id="2ea1b-119">[如何创建用户映射](../core/how-to-create-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="2ea1b-119">[How to Create User Mappings](../core/how-to-create-user-mappings.md) </span></span>  
 <span data-ttu-id="2ea1b-120">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="2ea1b-120">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="2ea1b-121">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="2ea1b-121">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="2ea1b-122">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="2ea1b-122">Managing User Mappings</span></span>](../core/managing-user-mappings.md)