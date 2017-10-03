---
title: "单一登录 On5 要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Single Sign-On, requirements [JD Edwards OneWorld adapters]
- adapters [JD Edwards OneWorld adapters], Single Sign-On
- SSO, requirements [JD Edwards OneWorld adapters]
- Single Sign-On, enabling [JD Edwards OneWorld adapters]
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b186eca2c24ef9c2731b66194a0543aba14e8bf1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="c15b4-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="c15b4-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="c15b4-103">若要使用单一登录 (SSO)，需具备以下各项：</span><span class="sxs-lookup"><span data-stu-id="c15b4-103">To use Single Sign-On (SSO), you must have:</span></span>  
  
-   <span data-ttu-id="c15b4-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c15b4-104">Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]</span></span>  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]  
  
-   <span data-ttu-id="c15b4-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c15b4-105">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="c15b4-106">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="c15b4-106">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="c15b4-107">隔离的主机应配置为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c15b4-107">The isolated host should be configured as authentication trusted.</span></span>  
  
### <a name="to-enable-sso"></a><span data-ttu-id="c15b4-108">启用 SSO 的步骤</span><span class="sxs-lookup"><span data-stu-id="c15b4-108">To enable SSO</span></span>  
  
1.  <span data-ttu-id="c15b4-109">在**传输属性**窗口中，选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="c15b4-109">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="c15b4-110">在指定传输属性时选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="c15b4-110">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="c15b4-111">有关创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。</span><span class="sxs-lookup"><span data-stu-id="c15b4-111">For information about creating affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c15b4-112">后执行的操作使用 SSO，请记得重置任何**Web 共享**文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="c15b4-112">After performing work using SSO, remember to reset any **Web-Sharing** folder to **Do not share**.</span></span> <span data-ttu-id="c15b4-113">如果相应文件夹仍为共享模式，则使用该文件夹的应用程序将不会正确更新或卸载，因为该文件夹会被视为在使用中。</span><span class="sxs-lookup"><span data-stu-id="c15b4-113">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15b4-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c15b4-114">See Also</span></span>  
 [<span data-ttu-id="c15b4-115">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="c15b4-115">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)