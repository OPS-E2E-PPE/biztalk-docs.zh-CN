---
title: 如何启用关联应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 051bc35f-55e6-4811-9559-b1bb66a570ce
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 53dcd9886bc808f84b112146971a6f9519c404e2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-an-affiliate-application"></a><span data-ttu-id="a9b58-102">如何启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="a9b58-102">How to Enable an Affiliate Application</span></span>
<span data-ttu-id="a9b58-103">你可以使用 Mmc 管理单元或**enableapp**命令以启用指定的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9b58-103">You can use the MMC Snap-In or the **enableapp** command to enable the specified affiliate application.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="a9b58-104">使用 MMC 管理单元启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="a9b58-104">To enable an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="a9b58-105">单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="a9b58-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="a9b58-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="a9b58-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="a9b58-107">右键单击 affililate 应用程序，并依次 **启用**。</span><span class="sxs-lookup"><span data-stu-id="a9b58-107">Right-click the affililate application, and then click **Enable**.</span></span>  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="a9b58-108">使用命令行启用关联应用程序</span><span class="sxs-lookup"><span data-stu-id="a9b58-108">To enable an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="a9b58-109">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a9b58-109">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="a9b58-110">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="a9b58-110">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="a9b58-111">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="a9b58-111">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="a9b58-112">类型`ssomanage –enableapp <application name>`，其中\<*应用程序名称*> 是你想要启用的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="a9b58-112">Type `ssomanage –enableapp <application name>`, where \<*application name*> is the name of the affiliate application you want to enable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b58-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9b58-113">See Also</span></span>  
 <span data-ttu-id="a9b58-114">[SSO 关联应用程序](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="a9b58-114">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="a9b58-115">[如何创建关联应用程序](../esso/how-to-create-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="a9b58-115">[How to Create an Affiliate Application](../esso/how-to-create-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="a9b58-116">[管理用户映射](../esso/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="a9b58-116">[Managing User Mappings](../esso/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="a9b58-117">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="a9b58-117">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)