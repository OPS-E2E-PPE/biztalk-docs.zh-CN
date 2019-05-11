---
title: 如何禁用用户映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14d1715268630f4eed26f8004fc3d61cde15830b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338110"
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="7b489-102">如何禁用用户映射</span><span class="sxs-lookup"><span data-stu-id="7b489-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="7b489-103">您可以禁用用户映射时您想要关闭与给定映射关联的所有操作。</span><span class="sxs-lookup"><span data-stu-id="7b489-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="7b489-104">必须禁用用户映射，然后才能删除它。</span><span class="sxs-lookup"><span data-stu-id="7b489-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="7b489-105">当禁用用户映射时，它将显示为 (D) *\<域\>\\< 用户名\>* 时列出用户映射。</span><span class="sxs-lookup"><span data-stu-id="7b489-105">When you disable a user mapping, it will appear as (D) *\<domain\>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="7b489-106">若要禁用用户映射使用管理实用工具</span><span class="sxs-lookup"><span data-stu-id="7b489-106">To disable a user mapping using the administration utility</span></span>  
  
1. <span data-ttu-id="7b489-107">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="7b489-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="7b489-108">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="7b489-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7b489-109">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="7b489-109">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="7b489-110">类型**ssomanage-disablemapping *\<域\>*\\*\<用户名\>\<应用程序名称\>**  <em>，其中 *\<域\></em>是 Windows 域用户帐户，并且*\<用户名\>\* 是你想要禁用其凭据的 Windows 用户名和*\<应用程序名称\>* 是你想要删除其用户映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="7b489-110">Type **ssomanage –disablemapping *\<domain\>*\\*\<username\> \<application name\>**<em>, where \*\<domain\></em> is the Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to disable the credentials, and *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7b489-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7b489-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="7b489-112">若要禁用用户映射使用客户端实用工具</span><span class="sxs-lookup"><span data-stu-id="7b489-112">To disable a user mapping using the client utility</span></span>  
  
1. <span data-ttu-id="7b489-113">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="7b489-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="7b489-114">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="7b489-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="7b489-115">默认安装目录*\<驱动器\>*: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="7b489-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="7b489-116">类型 \* \* ssoclient-disablemapping \*\<应用程序名称\>\*\*<em>，其中 \*\<应用程序名称\></em>是你想要删除关联应用程序的名称用户映射。</span><span class="sxs-lookup"><span data-stu-id="7b489-116">Type \*\*ssoclient –disablemapping \*\<application name\>\*\*<em>, where \*\<application name\></em> is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7b489-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="7b489-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b489-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b489-118">See Also</span></span>  
 <span data-ttu-id="7b489-119">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="7b489-119">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="7b489-120">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="7b489-120">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="7b489-121">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="7b489-121">Managing User Mappings</span></span>](../core/managing-user-mappings.md)