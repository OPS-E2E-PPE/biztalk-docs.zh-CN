---
title: "单一登录 On3 要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 005f095ae09b3018b9c8fe796520205103c7961a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="ff171-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="ff171-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="ff171-103">若要使用单一登录 (SSO)，必须安装以下软件：</span><span class="sxs-lookup"><span data-stu-id="ff171-103">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="ff171-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff171-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="ff171-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="ff171-105">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="ff171-106">支持 SSO 某个服务器系统</span><span class="sxs-lookup"><span data-stu-id="ff171-106">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="ff171-107">独立主机应配置为受信任验证。</span><span class="sxs-lookup"><span data-stu-id="ff171-107">The isolated host should be configured as Authentication Trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="ff171-108">启用 SSO 的步骤</span><span class="sxs-lookup"><span data-stu-id="ff171-108">To enable SSO</span></span>  
  
1.  <span data-ttu-id="ff171-109">在**传输属性**窗口中，选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="ff171-109">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="ff171-110">在指定传输属性时选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="ff171-110">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="ff171-111">有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。</span><span class="sxs-lookup"><span data-stu-id="ff171-111">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff171-112">后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="ff171-112">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="ff171-113">使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。</span><span class="sxs-lookup"><span data-stu-id="ff171-113">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff171-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff171-114">See Also</span></span>  
 [<span data-ttu-id="ff171-115">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="ff171-115">Using Single Sign-On</span></span>](../core/using-single-sign-on5.md)