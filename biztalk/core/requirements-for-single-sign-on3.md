---
title: TIBCO Rendevous 适配器的 SSO 要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d5c406b-f548-4df0-8644-fdf6a812a989
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08fc69294b5f2ca7a773adf64175b210604091c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396153"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="14d8b-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="14d8b-102">Requirements for Single Sign-On</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14d8b-103">先决条件</span><span class="sxs-lookup"><span data-stu-id="14d8b-103">Prerequisites</span></span>
<span data-ttu-id="14d8b-104">若要使用单一登录 (SSO)，您必须：</span><span class="sxs-lookup"><span data-stu-id="14d8b-104">To use Single Sign-On (SSO), you must have the following:</span></span>  
  
-   <span data-ttu-id="14d8b-105">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="14d8b-105">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="14d8b-106">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14d8b-106">Visual Studio</span></span>  
  
-   <span data-ttu-id="14d8b-107">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="14d8b-107">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="14d8b-108">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="14d8b-108">A server system that supports SSO</span></span>  
  
-   <span data-ttu-id="14d8b-109">独立主机应配置为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="14d8b-109">The isolated host should be configured as Authentication Trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="14d8b-110">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="14d8b-110">Enable SSO</span></span>  
  
1. <span data-ttu-id="14d8b-111">在中**传输属性**窗口中，选择**是**有关**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="14d8b-111">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2. <span data-ttu-id="14d8b-112">指定传输属性时，请选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="14d8b-112">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
   <span data-ttu-id="14d8b-113">有关详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。</span><span class="sxs-lookup"><span data-stu-id="14d8b-113">For more information, see [Creating Affiliate Applications](../core/creating-affiliate-applications1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14d8b-114">执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="14d8b-114">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="14d8b-115">使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。</span><span class="sxs-lookup"><span data-stu-id="14d8b-115">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d8b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="14d8b-116">See Also</span></span>  
[<span data-ttu-id="14d8b-117">安全性</span><span class="sxs-lookup"><span data-stu-id="14d8b-117">Security</span></span>](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)