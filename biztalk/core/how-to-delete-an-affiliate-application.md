---
title: 如何删除关联应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications [SSO], deleting
- managing [SSO applications], deleting
- deleting, applications [SSO]
ms.assetid: c7ec065e-ef10-49ff-a350-105dd08dc4a9
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b24dc6a17f6bbe30af7354b88be822cf7dcb7c08
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "65338622"
---
# <a name="how-to-delete-an-affiliate-application"></a><span data-ttu-id="08f52-102">如何删除关联应用程序</span><span class="sxs-lookup"><span data-stu-id="08f52-102">How to Delete an Affiliate Application</span></span>
<span data-ttu-id="08f52-103">可以使用 MMC 管理单元或命令行从 SSO 数据库中删除指定的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="08f52-103">You can use the MMC Snap-In or the command line to delete the specified affiliate application from the SSO database.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="08f52-104">当删除关联应用程序时，SSO 系统将自动删除与之关联的所有映射。</span><span class="sxs-lookup"><span data-stu-id="08f52-104">When you delete an affiliate application, the SSO system automatically deletes all mappings associated with it.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="08f52-105">您必须是 SSO 管理员或 SSO 关联管理员才能执行此任务。</span><span class="sxs-lookup"><span data-stu-id="08f52-105">You must be an SSO administrator or SSO affiliate administrator to perform this task.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a><span data-ttu-id="08f52-106">若要删除关联应用程序使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="08f52-106">To delete an affiliate application using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="08f52-107">上**启动**菜单上，单击**程序**，单击**Microsoft 企业单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="08f52-107">On the **Start** menu, click **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="08f52-108">中的 Mmc 管理单元的作用域窗格中，展开**企业单一登录**节点。</span><span class="sxs-lookup"><span data-stu-id="08f52-108">In the scope pane of the MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="08f52-109">右键单击关联应用程序，然后依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="08f52-109">Right-click the affiliate application, and then click **Delete**.</span></span>  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a><span data-ttu-id="08f52-110">若要删除关联应用程序使用命令行</span><span class="sxs-lookup"><span data-stu-id="08f52-110">To delete an affiliate application using the command line</span></span>  
  
1. <span data-ttu-id="08f52-111">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="08f52-111">On the **Start** menu, click **run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="08f52-112">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="08f52-112">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="08f52-113">默认安装目录 *\<驱动器\>* : \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="08f52-113">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="08f52-114">类型 \* \* ssomanage-deleteapp \*\<应用程序名称\>\*\*<em>，其中 \*\<应用程序名称\></em>是你想要删除从关联应用程序的名称SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="08f52-114">Type \*\*ssomanage –deleteapp \*\<application name\>\*\*<em>, where \*\<application name\></em> is the name of the affiliate application you want to remove from the SSO database.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="08f52-115">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="08f52-115">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08f52-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="08f52-116">See Also</span></span>  
 <span data-ttu-id="08f52-117">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="08f52-117">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 <span data-ttu-id="08f52-118">[如何启用关联应用程序](../core/how-to-enable-an-affiliate-application.md) </span><span class="sxs-lookup"><span data-stu-id="08f52-118">[How to Enable an Affiliate Application](../core/how-to-enable-an-affiliate-application.md) </span></span>  
 <span data-ttu-id="08f52-119">[管理用户映射](../core/managing-user-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="08f52-119">[Managing User Mappings](../core/managing-user-mappings.md) </span></span>  
 [<span data-ttu-id="08f52-120">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="08f52-120">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)