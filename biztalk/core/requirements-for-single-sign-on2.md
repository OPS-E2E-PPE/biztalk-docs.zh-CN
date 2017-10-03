---
title: "单一登录 On2 要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enabling SSO
- Single Sign-On, requirements
- SSO, enabling
- Single Sign-On, enabling
- SSO requirements
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c886792f36808152c4a27733544b09015c68f061
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="f0ff3-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="f0ff3-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="f0ff3-103">若要使用单一登录 (SSO)，你需要：</span><span class="sxs-lookup"><span data-stu-id="f0ff3-103">To use Single Sign-On (SSO), you need:</span></span>  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="f0ff3-104">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f0ff3-104">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="f0ff3-105">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="f0ff3-105">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="f0ff3-106">隔离的主机应配置为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="f0ff3-106">The isolated host should be configured as authentication trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="f0ff3-107">启用 SSO 的步骤</span><span class="sxs-lookup"><span data-stu-id="f0ff3-107">To enable SSO</span></span>  
  
1.  <span data-ttu-id="f0ff3-108">在**传输属性**窗口中，选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="f0ff3-108">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="f0ff3-109">在指定传输属性时选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0ff3-109">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="f0ff3-110">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)。</span><span class="sxs-lookup"><span data-stu-id="f0ff3-110">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0ff3-111">后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="f0ff3-111">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="f0ff3-112">使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。</span><span class="sxs-lookup"><span data-stu-id="f0ff3-112">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ff3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0ff3-113">See Also</span></span>  
 <span data-ttu-id="f0ff3-114">[运行 SSO 项目](../core/running-sso-projects1.md) </span><span class="sxs-lookup"><span data-stu-id="f0ff3-114">[Running SSO Projects](../core/running-sso-projects1.md) </span></span>  
 [<span data-ttu-id="f0ff3-115">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="f0ff3-115">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)