---
title: 单一登录的要求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae4b5c1f-1718-4628-9159-2fb877498913
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62bc38cadb304f753a408c9c9573056c70b34671
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240314"
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="7ee90-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="7ee90-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="7ee90-103">若要使用单一登录 (SSO)，需要：</span><span class="sxs-lookup"><span data-stu-id="7ee90-103">To use Single Sign-On (SSO), you need:</span></span>  
  
- <span data-ttu-id="7ee90-104">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7ee90-104">BizTalk Server</span></span>
  
- <span data-ttu-id="7ee90-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7ee90-105">Visual Studio</span></span>  
  
- <span data-ttu-id="7ee90-106">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="7ee90-106">Enterprise Single Sign-On</span></span>  
  
- <span data-ttu-id="7ee90-107">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="7ee90-107">A Server System that supports SSO</span></span>  
  
  <span data-ttu-id="7ee90-108">独立主机应配置为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="7ee90-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="7ee90-109">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="7ee90-109">Enable SSO</span></span>  
  
1. <span data-ttu-id="7ee90-110">在中**传输属性**窗口中，选择**是**有关**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="7ee90-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2. <span data-ttu-id="7ee90-111">指定传输属性时，请选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="7ee90-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
   <span data-ttu-id="7ee90-112">有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee90-112">For information about how to create an affiliate application, see [Creating Affiliate Applications](../core/creating-affiliate-applications2.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ee90-113">执行相应操作后使用 SSO，请重置到任何 Web 共享文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="7ee90-113">After performing work using SSO, remember to reset any Web-Sharing folder to **Do not share**.</span></span> <span data-ttu-id="7ee90-114">使用该文件夹的应用程序将不更新，或如果共享的文件夹，因为它被视为在使用中正确卸载。</span><span class="sxs-lookup"><span data-stu-id="7ee90-114">Applications that use that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee90-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee90-115">See Also</span></span>  
 <span data-ttu-id="7ee90-116">[运行 SSO 项目](../core/running-sso-projects1.md) </span><span class="sxs-lookup"><span data-stu-id="7ee90-116">[Running SSO Projects](../core/running-sso-projects1.md) </span></span>  
 [<span data-ttu-id="7ee90-117">保护适配器</span><span class="sxs-lookup"><span data-stu-id="7ee90-117">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)