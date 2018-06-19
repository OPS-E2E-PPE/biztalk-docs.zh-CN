---
title: 如何禁用的用户映射 |Microsoft 文档
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
ms.openlocfilehash: 6b17ab68356d5d39f3f839f736261d4a7ef79c78
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "25968947"
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="af0f0-102">如何禁用的用户映射</span><span class="sxs-lookup"><span data-stu-id="af0f0-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="af0f0-103">当需要关闭与给定映射关联的所有操作时，可以禁用用户映射。</span><span class="sxs-lookup"><span data-stu-id="af0f0-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="af0f0-104">在删除用户映射之前必须禁用该映射。</span><span class="sxs-lookup"><span data-stu-id="af0f0-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="af0f0-105">当禁用用户映射时，它将显示为 (D) *\<域\>\\< 用户名\>* 时列出的用户映射。</span><span class="sxs-lookup"><span data-stu-id="af0f0-105">When you disable a user mapping, it will appear as (D) *\<domain\>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="af0f0-106">使用管理实用工具禁用用户映射</span><span class="sxs-lookup"><span data-stu-id="af0f0-106">To disable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="af0f0-107">上 **启动** 菜单上，单击 **运行**, ，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="af0f0-107">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="af0f0-108">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="af0f0-108">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="af0f0-109">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="af0f0-109">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="af0f0-110">类型 **ssomanage-disablemapping *\<域\>*\\*\<用户名\>\<应用程序名称\>* * *，其中*\<域\>* 是用户帐户的 Windows 域和*\<用户名\>* 是 Windows 用户名称想要禁用凭据，为和*\<应用程序名称\>* 是你想要删除的用户映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="af0f0-110">Type **ssomanage –disablemapping *\<domain\>*\\*\<username\> \<application name\>***, where *\<domain\>* is the Windows domain for the user account, and *\<username\>* is the Windows user name for which you want to disable the credentials, and *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af0f0-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="af0f0-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="af0f0-112">使用客户端实用工具禁用用户映射</span><span class="sxs-lookup"><span data-stu-id="af0f0-112">To disable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="af0f0-113">上 **启动** 菜单上，单击 **运行**, ，然后键入 **cmd**。</span><span class="sxs-lookup"><span data-stu-id="af0f0-113">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="af0f0-114">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="af0f0-114">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="af0f0-115">默认安装目录是*\<驱动器\>*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="af0f0-115">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="af0f0-116">类型 * * ssoclient – disablemapping *\<应用程序名称\>* * *，其中*\<应用程序名称\>* 是你想要删除的用户映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="af0f0-116">Type **ssoclient –disablemapping *\<application name\>***, where *\<application name\>* is the name of the affiliate application you want to remove the user mapping for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="af0f0-117">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="af0f0-117">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0f0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af0f0-118">See Also</span></span>  
 <span data-ttu-id="af0f0-119">[SSO 映射](../core/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="af0f0-119">[SSO Mappings](../core/sso-mappings.md) </span></span>  
 <span data-ttu-id="af0f0-120">[管理关联应用程序](../core/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="af0f0-120">[Managing Affiliate Applications](../core/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="af0f0-121">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="af0f0-121">Managing User Mappings</span></span>](../core/managing-user-mappings.md)