---
title: 如何删除关联应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec290d38-0220-4bf2-b596-2d6453e51c8d
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: d0632f7e4217cb9bbccd2ee604688f22eb6de348
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="c66a4-102">如何删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="c66a4-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="c66a4-103">使用 Mmc 管理单元或**deleteapps**命令以从凭据数据库中删除指定的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="c66a4-103">Use the MMC Snap-In or the **deleteapps** command to delete the specified affiliate application from the Credential database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c66a4-104">在删除关联应用程序时，SSO 系统将自动删除与之关联的所有映射。</span><span class="sxs-lookup"><span data-stu-id="c66a4-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c66a4-105">只有 SSO 管理员或 SSO 关联管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="c66a4-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="c66a4-106">使用 MMC 管理单元删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="c66a4-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="c66a4-107">单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="c66a4-107">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="c66a4-108">在的 MMC 管理单元中的作用域窗格中，展开 **企业单一登录** 节点。</span><span class="sxs-lookup"><span data-stu-id="c66a4-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="c66a4-109">右键单击关联应用程序，并依次 **删除**。</span><span class="sxs-lookup"><span data-stu-id="c66a4-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="c66a4-110">使用命令行删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="c66a4-110">To delete an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="c66a4-111">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c66a4-111">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="c66a4-112">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="c66a4-112">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="c66a4-113">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="c66a4-113">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="c66a4-114">类型`ssomanage –deleteapp <application name>`，其中*\<应用程序名称 >*是你想要从凭据数据库中删除关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="c66a4-114">Type `ssomanage –deleteapp <application name>`, where *\<application name>* is the name of the affiliate application you want to remove from the Credential database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c66a4-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c66a4-115">See Also</span></span>  
 <span data-ttu-id="c66a4-116">[SSO 关联应用程序](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="c66a4-116">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="c66a4-117">[如何启用关联应用程序](../esso/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="c66a4-117">[How to Enable an Affiliate Application](../esso/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="c66a4-118">[管理用户映射](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="c66a4-118">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="c66a4-119">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="c66a4-119">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)