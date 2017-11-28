---
title: "单一登录要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 472893a2a65d762f17747dac78b67b373165c0cf
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="b8674-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="b8674-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="b8674-103">若要使用单一登录 (SSO)，你需要：</span><span class="sxs-lookup"><span data-stu-id="b8674-103">To use Single Sign-On (SSO), you need:</span></span>  
  
-   <span data-ttu-id="b8674-104">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="b8674-104">BizTalk Server</span></span>
  
-   <span data-ttu-id="b8674-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8674-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="b8674-106">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b8674-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="b8674-107">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="b8674-107">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="b8674-108">隔离的主机应配置为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="b8674-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="b8674-109">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="b8674-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="b8674-110">在**传输属性**窗口中，选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="b8674-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="b8674-111">在指定传输属性时选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b8674-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
 <span data-ttu-id="b8674-112">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)。</span><span class="sxs-lookup"><span data-stu-id="b8674-112">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8674-113">后执行的操作使用 SSO，请记得重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="b8674-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="b8674-114">使用该文件夹的应用程序将不更新，或如果共享文件夹，因为它被视为可在使用正常卸载。</span><span class="sxs-lookup"><span data-stu-id="b8674-114">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8674-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8674-115">See Also</span></span>  
 <span data-ttu-id="b8674-116">[运行 SSO 项目](../core/running-sso-projects1.md) </span><span class="sxs-lookup"><span data-stu-id="b8674-116">[Running SSO Projects](../core/running-sso-projects1.md) </span></span>  
 [<span data-ttu-id="b8674-117">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="b8674-117">Using Single Sign-On</span></span>](../core/using-single-sign-on2.md)