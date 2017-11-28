---
title: "单一登录要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61932b44364670515f02f89a1441a5d54030bc94
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="41b07-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="41b07-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="41b07-103">若要使用单一登录 (SSO)，必须安装以下软件：</span><span class="sxs-lookup"><span data-stu-id="41b07-103">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="41b07-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="41b07-104">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="41b07-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="41b07-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="41b07-106">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="41b07-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="41b07-107">支持 SSO 某个服务器系统</span><span class="sxs-lookup"><span data-stu-id="41b07-107">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="41b07-108">独立主机应配置为受信任验证。</span><span class="sxs-lookup"><span data-stu-id="41b07-108">The isolated host should be configured as Authentication Trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="41b07-109">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="41b07-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="41b07-110">在**传输属性**窗口中，选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="41b07-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="41b07-111">在指定传输属性时选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="41b07-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="41b07-112">有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。</span><span class="sxs-lookup"><span data-stu-id="41b07-112">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41b07-113">后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="41b07-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="41b07-114">使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。</span><span class="sxs-lookup"><span data-stu-id="41b07-114">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b07-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41b07-115">See Also</span></span>  
 [<span data-ttu-id="41b07-116">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="41b07-116">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)