---
title: TIBCO EMS 适配器的 SSO 要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 645c7b3f-f860-4c20-b5ca-a8fb93736344
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a07e4ecf344b06c9d1f98297acb3b3a851283e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399122"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="1483c-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="1483c-102">Requirements for Single Sign-On</span></span>

## <a name="overview"></a><span data-ttu-id="1483c-103">概述</span><span class="sxs-lookup"><span data-stu-id="1483c-103">Overview</span></span>
<span data-ttu-id="1483c-104">用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器提供单一登录 (SSO) 支持。</span><span class="sxs-lookup"><span data-stu-id="1483c-104">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="1483c-105">由企业单一登录工具创建关联应用程序代表诸如 TIBCO EMS 等服务器系统。</span><span class="sxs-lookup"><span data-stu-id="1483c-105">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO EMS.</span></span>  
  
 <span data-ttu-id="1483c-106">若要使用单一登录，必须具有：</span><span class="sxs-lookup"><span data-stu-id="1483c-106">To use Single Sign-On, you must have:</span></span>  
  
- <span data-ttu-id="1483c-107">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="1483c-107">Microsoft BizTalk Server</span></span>
  
- <span data-ttu-id="1483c-108">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1483c-108">Visual Studio</span></span>  
  
- <span data-ttu-id="1483c-109">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="1483c-109">Enterprise Single Sign-On</span></span>  
  
- <span data-ttu-id="1483c-110">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="1483c-110">A server system that supports SSO</span></span>  
  
  <span data-ttu-id="1483c-111">独立主机应配置为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="1483c-111">The isolated host should be configured as authentication trusted.</span></span>
  
## <a name="enable-sso"></a><span data-ttu-id="1483c-112">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="1483c-112">Enable SSO</span></span>  
  
1.  <span data-ttu-id="1483c-113">在中**传输属性**窗口中，选择**是**有关**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="1483c-113">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="1483c-114">指定传输属性时，请选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="1483c-114">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="1483c-115">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。</span><span class="sxs-lookup"><span data-stu-id="1483c-115">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications5.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1483c-116">执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="1483c-116">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="1483c-117">使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。</span><span class="sxs-lookup"><span data-stu-id="1483c-117">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1483c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="1483c-118">See Also</span></span>  
[<span data-ttu-id="1483c-119">保护适配器</span><span class="sxs-lookup"><span data-stu-id="1483c-119">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)