---
title: 单一登录的要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1111377-2fe1-4d65-ac0d-c89d2f1740b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69bd8a232ba49f9e4ebb2eb3e53a70704bf0d80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240395"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="848c2-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="848c2-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="848c2-103">若要使用单一登录 (SSO)，您必须安装以下软件：</span><span class="sxs-lookup"><span data-stu-id="848c2-103">To use Single Sign-On (SSO), you must have the following software installed:</span></span>  
  
-   <span data-ttu-id="848c2-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="848c2-104">Microsoft BizTalk Server</span></span>
  
-   <span data-ttu-id="848c2-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="848c2-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="848c2-106">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="848c2-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="848c2-107">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="848c2-107">A Server System that supports SSO</span></span>  
  
-   <span data-ttu-id="848c2-108">独立主机应配置为**受信任验证**。</span><span class="sxs-lookup"><span data-stu-id="848c2-108">The isolated host should be configured as **Authentication Trusted**.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="848c2-109">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="848c2-109">Enable SSO</span></span>  
  
1. <span data-ttu-id="848c2-110">在中**传输属性**窗口中，选择**是**有关**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="848c2-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2. <span data-ttu-id="848c2-111">指定传输属性时，请选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="848c2-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
   <span data-ttu-id="848c2-112">有关创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications4.md)。</span><span class="sxs-lookup"><span data-stu-id="848c2-112">For information about creating an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications4.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="848c2-113">执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="848c2-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="848c2-114">使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。</span><span class="sxs-lookup"><span data-stu-id="848c2-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="848c2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="848c2-115">See Also</span></span>  
 [<span data-ttu-id="848c2-116">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="848c2-116">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)