---
title: 如何清除应用程序缓存 |Microsoft 文档
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a897791-d32f-46a4-8c5d-2b2161e92bd9
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 24954e8314bc94d4570eb57acbf1d4b03bebb65b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250937"
---
# <a name="how-to-clear-the-application-cache"></a><span data-ttu-id="61162-102">如何清除应用程序缓存</span><span class="sxs-lookup"><span data-stu-id="61162-102">How to Clear the Application Cache</span></span>
<span data-ttu-id="61162-103">使用 Mmc 管理单元或**purgecache**命令，以删除凭据缓存 （所有的信息与关联应用程序关联） 的内容的所有单一登录 (SSO) 服务器上指定的应用程序。</span><span class="sxs-lookup"><span data-stu-id="61162-103">Use the MMC Snap-In or the **purgecache** command to remove the contents of the credential cache (all the information that is associated with the affiliate application) for the specified application on all Single Sign-On (SSO) servers.</span></span>  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a><span data-ttu-id="61162-104">若要清除缓存使用 Mmc 管理单元</span><span class="sxs-lookup"><span data-stu-id="61162-104">To clear the cache using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="61162-105">单击**启动**，指向**程序**，单击**Microsoft Enterprise 上单一登录**，然后单击**SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="61162-105">Click **Start**, point to **Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="61162-106">在 ENTSSO MMC 管理单元的作用域窗格中，展开“企业单一登录”  节点。</span><span class="sxs-lookup"><span data-stu-id="61162-106">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="61162-107">单击 **Affiliate 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="61162-107">Click **Affiliate Applications**.</span></span>  
  
4.  <span data-ttu-id="61162-108">在结果窗格中，右键单击关联应用程序，然后单击 **清除**。</span><span class="sxs-lookup"><span data-stu-id="61162-108">In the results pane, right-click the affiliate application, and click **Clear**.</span></span>  
  
### <a name="to-clear-the-cache-using-the-command-line"></a><span data-ttu-id="61162-109">若要清除缓存使用命令行</span><span class="sxs-lookup"><span data-stu-id="61162-109">To clear the cache using the command line</span></span>  
  
1.  <span data-ttu-id="61162-110">单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="61162-110">Click **Start**, click **Run**, type `cmd`, and then press ENTER.</span></span>  
  
2.  <span data-ttu-id="61162-111">在命令提示符处，转到企业单一登录安装目录。</span><span class="sxs-lookup"><span data-stu-id="61162-111">At the command prompt, go to the Enterprise Single Sign-On installation directory.</span></span>  
  
     <span data-ttu-id="61162-112">默认安装目录是\<*驱动器*>: \program Files\Enterprise 单一登录。</span><span class="sxs-lookup"><span data-stu-id="61162-112">The default installation directory is \<*drive*>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="61162-113">类型`ssomanage –purgecache <application name>`，其中\<*应用程序名称*> 是你想要清除的缓存的关联应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="61162-113">Type `ssomanage –purgecache <application name>`, where \<*application name*> is the name of the affiliate application that you want to purge the cache for.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61162-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61162-114">See Also</span></span>  
 <span data-ttu-id="61162-115">[SSO 关联应用程序](../esso/sso-affiliate-applications.md) </span><span class="sxs-lookup"><span data-stu-id="61162-115">[SSO Affiliate Applications](../esso/sso-affiliate-applications.md) </span></span>  
 [<span data-ttu-id="61162-116">管理关联应用程序</span><span class="sxs-lookup"><span data-stu-id="61162-116">Managing Affiliate Applications</span></span>](../esso/managing-affiliate-applications.md)