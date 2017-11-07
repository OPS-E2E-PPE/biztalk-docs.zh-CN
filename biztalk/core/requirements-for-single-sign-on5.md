---
title: "单一登录要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 318b9977-ce24-48d6-971b-49a059a1bdbc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd2a1fb342911c904044c8099901c5056f17ac9f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="requirements-for-single-sign-on"></a><span data-ttu-id="8266f-102">单一登录的要求</span><span class="sxs-lookup"><span data-stu-id="8266f-102">Requirements for Single Sign-On</span></span>
<span data-ttu-id="8266f-103">若要使用单一登录 (SSO)，需具备以下各项：</span><span class="sxs-lookup"><span data-stu-id="8266f-103">To use Single Sign-On (SSO), you must have:</span></span>  
  
-   <span data-ttu-id="8266f-104">Microsoft BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="8266f-104">Microsoft BizTalk Server</span></span> 
  
-   <span data-ttu-id="8266f-105">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8266f-105">Visual Studio</span></span>  
  
-   <span data-ttu-id="8266f-106">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="8266f-106">Enterprise Single Sign-On</span></span>  
  
-   <span data-ttu-id="8266f-107">支持 SSO 的服务器系统</span><span class="sxs-lookup"><span data-stu-id="8266f-107">A Server System that supports SSO</span></span>  
  
 <span data-ttu-id="8266f-108">隔离的主机应配置为受信任的身份验证。</span><span class="sxs-lookup"><span data-stu-id="8266f-108">The isolated host should be configured as authentication trusted.</span></span>  
  
## <a name="enable-sso"></a><span data-ttu-id="8266f-109">启用 SSO</span><span class="sxs-lookup"><span data-stu-id="8266f-109">Enable SSO</span></span>  
  
1.  <span data-ttu-id="8266f-110">在**传输属性**窗口中，选择**是**为**使用 SSO**。</span><span class="sxs-lookup"><span data-stu-id="8266f-110">In the **Transport Properties** window, select **Yes** for **Use SSO**.</span></span>  
  
2.  <span data-ttu-id="8266f-111">在指定传输属性时选择相应的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="8266f-111">Select an appropriate affiliate application when specifying transport properties.</span></span>  
  
     <span data-ttu-id="8266f-112">有关创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications3.md)。</span><span class="sxs-lookup"><span data-stu-id="8266f-112">For information about creating affiliate applications, see [Creating Affiliate Applications](../core/creating-affiliate-applications3.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8266f-113">后执行的操作使用 SSO，请记得重置任何**Web 共享**文件夹**不共享**。</span><span class="sxs-lookup"><span data-stu-id="8266f-113">After performing work using SSO, remember to reset any **Web-Sharing** folder to **Do not share**.</span></span> <span data-ttu-id="8266f-114">如果相应文件夹仍为共享模式，则使用该文件夹的应用程序将不会正确更新或卸载，因为该文件夹会被视为在使用中。</span><span class="sxs-lookup"><span data-stu-id="8266f-114">Applications using that folder will not update or uninstall correctly if the folder is shared because it is considered to be in use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8266f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8266f-115">See Also</span></span>  
 [<span data-ttu-id="8266f-116">适配器中的安全</span><span class="sxs-lookup"><span data-stu-id="8266f-116">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)