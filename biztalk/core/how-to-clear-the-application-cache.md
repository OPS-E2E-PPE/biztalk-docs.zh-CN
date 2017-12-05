---
title: "如何清除应用程序缓存 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- caching, applications
- managing [SSO applications], clearing cache
- applications [SSO], caching
ms.assetid: 6230b9a4-c7b8-47b4-854b-12853d9bf5b0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184569a3eed693a7b699b2ad14cfb8461cc496e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-clear-the-application-cache"></a><span data-ttu-id="97134-102">如何清除应用程序缓存</span><span class="sxs-lookup"><span data-stu-id="97134-102">How to Clear the Application Cache</span></span>
<span data-ttu-id="97134-103">你可以使用 MMC 管理单元中或命令行删除凭据缓存 （所有与关联的信息关联应用程序） 的内容的所有单一登录在服务器上的指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="97134-103">You can use the MMC Snap-In or the command line to remove the contents of the credential cache (all the information associated with the affiliate application) for the specified application on all of the Single Sign-On Servers.</span></span>  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a><span data-ttu-id="97134-104">若要清除缓存使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="97134-104">To clear the cache using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="97134-105">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="97134-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="97134-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="97134-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="97134-107">单击**Affiliate 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="97134-107">Click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="97134-108">在结果窗格中，右键单击关联应用程序，然后单击**清除**。</span><span class="sxs-lookup"><span data-stu-id="97134-108">In the results pane, right-click the affiliate application, and click **Clear**.</span></span>  
  
### <a name="to-clear-the-cache-using-the-command-line"></a><span data-ttu-id="97134-109">若要清除缓存使用命令行</span><span class="sxs-lookup"><span data-stu-id="97134-109">To clear the cache using the command line</span></span>  
  
1.  <span data-ttu-id="97134-110">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="97134-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="97134-111">在命令行上，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="97134-111">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="97134-112">默认安装目录是\<*驱动器*\>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="97134-112">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="97134-113">类型**ssomanage-purgecache *\<应用程序名称\>***，其中\<*应用程序名称*\>是的名称关联应用程序，你想要清除的缓存。</span><span class="sxs-lookup"><span data-stu-id="97134-113">Type **ssomanage –purgecache *\<application name\>***, where \<*application name*\> is the name of the affiliate application you want to purge the cache for.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97134-114">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="97134-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97134-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97134-115">See Also</span></span>  
 <span data-ttu-id="97134-116">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="97134-116">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="97134-117">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="97134-117">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)