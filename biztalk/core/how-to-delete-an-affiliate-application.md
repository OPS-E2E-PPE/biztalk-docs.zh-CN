---
title: "如何删除关联应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ddb40109ff402f1c1794a90e591a43e11407fba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="6abd6-102">如何删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="6abd6-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="6abd6-103">可以使用 MMC 管理单元或命令行从 SSO 数据库中删除指定的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="6abd6-103">You can use the MMC Snap-In or the command line to delete the specified affiliate application from the SSO database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6abd6-104">在删除关联应用程序时，SSO 系统将自动删除与之关联的所有映射。</span><span class="sxs-lookup"><span data-stu-id="6abd6-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6abd6-105">只有 SSO 管理员或 SSO 关联管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="6abd6-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="6abd6-106">使用 MMC 管理单元删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="6abd6-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="6abd6-107">上**启动**菜单上，单击**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="6abd6-107">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="6abd6-108">在的 MMC 管理单元中的作用域窗格中，展开**企业单一登录**节点。</span><span class="sxs-lookup"><span data-stu-id="6abd6-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="6abd6-109">右键单击关联应用程序，并依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="6abd6-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="6abd6-110">使用命令行删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="6abd6-110">To delete an affiliate application using the command line</span></span>  
  
1.  <span data-ttu-id="6abd6-111">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="6abd6-111">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="6abd6-112">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="6abd6-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="6abd6-113">默认安装目录是*\<驱动器 >*: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="6abd6-113">The default installation directory is *\<drive>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="6abd6-114">类型**ssomanage-deleteapp *\<应用程序名称 >***，其中*\<应用程序名称 >*是关联应用程序的名称你想要从 SSO 数据库中删除。</span><span class="sxs-lookup"><span data-stu-id="6abd6-114">Type **ssomanage –deleteapp *\<application name>***, where *\<application name>* is the name of the affiliate application you want to remove from the SSO database.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6abd6-115">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="6abd6-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6abd6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6abd6-116">See Also</span></span>  
 <span data-ttu-id="6abd6-117">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="6abd6-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="6abd6-118">[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="6abd6-118">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="6abd6-119">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="6abd6-119">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="6abd6-120">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="6abd6-120">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)