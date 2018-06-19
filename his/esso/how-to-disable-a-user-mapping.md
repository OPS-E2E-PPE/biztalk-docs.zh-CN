---
title: 如何禁用的用户映射 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c745dd-4d39-46e5-88bf-b803ae2e0a1b
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 93694ed8a3238be51b255bcad79122169461d885
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250969"
---
# <a name="how-to-disable-a-user-mapping"></a><span data-ttu-id="a0ad2-102">如何禁用的用户映射</span><span class="sxs-lookup"><span data-stu-id="a0ad2-102">How to Disable a User Mapping</span></span>
<span data-ttu-id="a0ad2-103">当需要关闭与给定映射关联的所有操作时，可以禁用用户映射。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-103">You can disable a user mapping when you want to turn off all operations associated with a given mapping.</span></span> <span data-ttu-id="a0ad2-104">在删除用户映射之前必须禁用该映射。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-104">You must disable a user mapping before you can remove it.</span></span>  
  
 <span data-ttu-id="a0ad2-105">当禁用用户映射时，它将显示为 (D) *\<域 >\\< 用户名\>* 时列出的用户映射。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-105">When you disable a user mapping, it will appear as (D) *\<domain>\\<username\>* when you list the user mappings.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a><span data-ttu-id="a0ad2-106">使用管理实用工具禁用用户映射</span><span class="sxs-lookup"><span data-stu-id="a0ad2-106">To disable a user mapping using the administration utility</span></span>  
  
1.  <span data-ttu-id="a0ad2-107">单击**启动**，单击**运行**，类型`cmd`，然后按**ENTER**。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-107">Click **Start**, click **Run**, type `cmd`, and then press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="a0ad2-108">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-108">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="a0ad2-109">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-109">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a0ad2-110">类型`ssomanage –disablemapping <domain>\<username><application name>`，其中*\<域 >* 是用户帐户的 Windows 域*\<用户名 >* 是你想要禁用的 Windows 用户名称凭据，和*\<应用程序名称 >* 是你想要删除的用户映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-110">Type `ssomanage –disablemapping <domain>\<username><application name>`, where *\<domain>* is the Windows domain for the user account, *\<username>* is the Windows user name for which you want to disable the credentials, and *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a><span data-ttu-id="a0ad2-111">使用客户端实用工具禁用用户映射</span><span class="sxs-lookup"><span data-stu-id="a0ad2-111">To disable a user mapping using the client utility</span></span>  
  
1.  <span data-ttu-id="a0ad2-112">单击**启动**，单击**运行**，类型`cmd`，然后按**ENTER**。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-112">Click **Start**, click **Run**, type `cmd`, and then press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="a0ad2-113">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-113">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="a0ad2-114">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-114">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a0ad2-115">类型`ssoclient –disablemapping <application name>`，其中*\<应用程序名称 >* 是你想要删除的用户映射的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a0ad2-115">Type `ssoclient –disablemapping <application name>`, where *\<application name>* is the name of the affiliate application for which you want to remove the user mapping.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ad2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0ad2-116">See Also</span></span>  
 <span data-ttu-id="a0ad2-117">[SSO 映射](../esso/sso-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="a0ad2-117">[SSO Mappings](../esso/sso-mappings.md) </span></span>  
 <span data-ttu-id="a0ad2-118">[管理关联应用程序](../esso/managing-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a0ad2-118">[Managing Affiliate Applications](../esso/managing-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="a0ad2-119">管理用户映射</span><span class="sxs-lookup"><span data-stu-id="a0ad2-119">Managing User Mappings</span></span>](../esso/managing-user-mappings.md)