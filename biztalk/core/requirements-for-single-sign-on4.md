---
title: "单一登录要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98d5164fa194f9a02314b897b267d9873879a9c0
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="5df3c-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="5df3c-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="5df3c-103">用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供单一登录 (SSO) 支持。</span><span class="sxs-lookup"><span data-stu-id="5df3c-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="5df3c-104">由企业单一登录工具创建的关联应用程序表示诸如 TIBCO EMS 等服务器系统。</span><span class="sxs-lookup"><span data-stu-id="5df3c-104">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="5df3c-105">若要使用单一登录，需具备以下各项：</span><span class="sxs-lookup"><span data-stu-id="5df3c-105">To use Single Sign-On, you must have:</span></span>  
  
-   <span data-ttu-id="5df3c-106">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5df3c-106">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="5df3c-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5df3c-107">Visual Studio</span></span>  
  
-   <span data-ttu-id="5df3c-108">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5df3c-108">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="5df3c-109">支持 SSO 某个服务器系统</span><span class="sxs-lookup"><span data-stu-id="5df3c-109">A server system that supports SSO</span></span>  
  
 <span data-ttu-id="5df3c-110">独立主机应配置为受信任验证</span><span class="sxs-lookup"><span data-stu-id="5df3c-110">The isolated host should be configured as authentication trusted</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="5df3c-111">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="5df3c-111">Enable SSO</span></span>  
  
1.  <span data-ttu-id="5df3c-112">在**传输属性**窗口中，选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="5df3c-112">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="5df3c-113">在指定传输属性时选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="5df3c-113">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="5df3c-114">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。</span><span class="sxs-lookup"><span data-stu-id="5df3c-114">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5df3c-115">后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="5df3c-115">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="5df3c-116">使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。</span><span class="sxs-lookup"><span data-stu-id="5df3c-116">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df3c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5df3c-117">See Also</span></span>  
 [<span data-ttu-id="5df3c-118">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="5df3c-118">Using Single Sign-On</span></span>](../core/using-single-sign-on4.md)