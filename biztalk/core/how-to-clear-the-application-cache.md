---
title: 如何清除应用程序缓存 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- caching, applications
- managing [SSO applications], clearing cache
- applications [SSO], caching
ms.assetid: 6230b9a4-c7b8-47b4-854b-12853d9bf5b0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1a1405c3c4a024d7347e85be7abde432f693182
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387005"
---
# <a name="how-to-clear-the-application-cache"></a><span data-ttu-id="05566-102">如何清除应用程序缓存</span><span class="sxs-lookup"><span data-stu-id="05566-102">How to Clear the Application Cache</span></span>
<span data-ttu-id="05566-103">您可以使用 MMC 管理单元或命令行删除凭据缓存 （所有的信息与关联应用程序相关联） 的内容上的所有单一登录服务器的指定应用程序。</span><span class="sxs-lookup"><span data-stu-id="05566-103">You can use the MMC Snap-In or the command line to remove the contents of the credential cache (all the information associated with the affiliate application) for the specified application on all of the Single Sign-On Servers.</span></span>  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a><span data-ttu-id="05566-104">若要清除的缓存使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="05566-104">To clear the cache using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="05566-105">在“开始”  菜单上，依次单击“所有程序” 、“Microsoft Enterprise Single Sign-On” 和“SSO 管理” 。</span><span class="sxs-lookup"><span data-stu-id="05566-105">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="05566-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="05566-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="05566-107">单击**关联应用程序**。</span><span class="sxs-lookup"><span data-stu-id="05566-107">Click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="05566-108">在结果窗格中，右键单击关联应用程序，然后单击**清除**。</span><span class="sxs-lookup"><span data-stu-id="05566-108">In the results pane, right-click the affiliate application, and click **Clear**.</span></span>  
  
### <a name="to-clear-the-cache-using-the-command-line"></a><span data-ttu-id="05566-109">若要清除的缓存使用命令行</span><span class="sxs-lookup"><span data-stu-id="05566-109">To clear the cache using the command line</span></span>  
  
1. <span data-ttu-id="05566-110">上**启动**菜单上，单击**运行**，然后键入**cmd**。</span><span class="sxs-lookup"><span data-stu-id="05566-110">On the **Start** menu, click **Run**, and then type **cmd**.</span></span>  
  
2. <span data-ttu-id="05566-111">在命令行中，转至企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="05566-111">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="05566-112">默认安装目录\<*驱动器*\>: \Program Files\Common Files\Enterprise Single Sign-on。</span><span class="sxs-lookup"><span data-stu-id="05566-112">The default installation directory is \<*drive*\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3. <span data-ttu-id="05566-113">类型<strong>ssomanage-purgecache *\<应用程序名称\></strong><em>，其中\<</em>应用程序的名称*\>名称关联应用程序想要清除的缓存。</span><span class="sxs-lookup"><span data-stu-id="05566-113">Type <strong>ssomanage –purgecache *\<application name\></strong><em>, where \<</em>application name*\> is the name of the affiliate application you want to purge the cache for.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="05566-114">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="05566-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05566-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="05566-115">See Also</span></span>  
 <span data-ttu-id="05566-116">[SSO 关联应用程序](../core/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="05566-116">[SSO Affiliate Applications](../core/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="05566-117">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="05566-117">Managing Affiliate Applications</span></span>](../core/managing-affiliate-applications.md)