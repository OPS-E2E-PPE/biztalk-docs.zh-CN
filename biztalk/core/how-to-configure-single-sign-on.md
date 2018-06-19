---
title: 如何配置单一登录 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 511edc1d-de82-4d17-88ea-6cacfccde10d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3203be74b21fa742e8e1ec2972e40f0212c4d1bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247765"
---
# <a name="how-to-configure-single-sign-on"></a><span data-ttu-id="10163-102">如何配置单一登录</span><span class="sxs-lookup"><span data-stu-id="10163-102">How to Configure Single Sign-On</span></span>
<span data-ttu-id="10163-103">在访问企业单一登录前，应确保为当前用户正确设置了企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="10163-103">Before accessing Enterprise Single Sign-On, you should make sure that Enterprise Single Sign-On is set correctly for the current user.</span></span> <span data-ttu-id="10163-104">对于大多数配置中，你使用两个接口之一。</span><span class="sxs-lookup"><span data-stu-id="10163-104">For most configurations, you use one of two interfaces.</span></span> <span data-ttu-id="10163-105">`ISSOAdmin`是可用于创建新的从属应用程序的一般管理接口。</span><span class="sxs-lookup"><span data-stu-id="10163-105">`ISSOAdmin` is the general administration interface that enables you to create new affiliation applications.</span></span> <span data-ttu-id="10163-106">但是，通过使用 ISSOAdmin.GetGlobalInfo 和 ISSOAdmin.UpdateGlobalInfo，您可以设置各种标志和管理值。</span><span class="sxs-lookup"><span data-stu-id="10163-106">However, by using ISSOAdmin.GetGlobalInfo and ISSOAdmin.UpdateGlobalInfo, you can set a variety of flags and administration values.</span></span> <span data-ttu-id="10163-107">其中一个可以实现的任务是确保启用 SSO 票证，如以下过程中所述：</span><span class="sxs-lookup"><span data-stu-id="10163-107">One possible task, as described in the following procedure, is to ensure that SSO ticketing has been enabled.</span></span>  
  
### <a name="to-enable-ticketing"></a><span data-ttu-id="10163-108">启用票证</span><span class="sxs-lookup"><span data-stu-id="10163-108">To enable ticketing</span></span>  
  
1.  <span data-ttu-id="10163-109">创建 `ISSOAdmin` 的一个新实例。</span><span class="sxs-lookup"><span data-stu-id="10163-109">Create a new instance of `ISSOAdmin`.</span></span>  
  
2.  <span data-ttu-id="10163-110">检索当前设置通过`ISSOAdmin.GetGlobalInfo`。</span><span class="sxs-lookup"><span data-stu-id="10163-110">Retrieve the current settings through `ISSOAdmin.GetGlobalInfo`.</span></span>  
  
     <span data-ttu-id="10163-111">如果需要，您可能要确认标志此时已设置为正确的值。</span><span class="sxs-lookup"><span data-stu-id="10163-111">If necessary, you may want to confirm that the flags are set to the correct values at this point.</span></span>  
  
3.  <span data-ttu-id="10163-112">更改使用任何相关标志`ISSOAdmin.UpdateGlobalInfo`。</span><span class="sxs-lookup"><span data-stu-id="10163-112">Change any relevant flags using `ISSOAdmin.UpdateGlobalInfo`.</span></span>  
  
     <span data-ttu-id="10163-113">在此特定情况下，所有标志都将设置为验证并启用票证。</span><span class="sxs-lookup"><span data-stu-id="10163-113">In this particular case, all the flags are being set to validate and enable tickets.</span></span>  
  
 <span data-ttu-id="10163-114">下例说明了如何使用单一登录启用票证：</span><span class="sxs-lookup"><span data-stu-id="10163-114">The following example shows how to enable ticketing using Single Sign-On.</span></span>  
  
```  
public static bool EnableTickets()  
{  
   try  
   {  
      ISSOAdmin admin=new ISSOAdmin();  
      int flags=0;  
      int appDeleteMax=1000;  
      int mappingDeleteMax=1000;  
      int ntpLookupMax=-1000;  
      int xplLookupMax=-1000;  
      int ticketTimeout=2;  
      int cacheTimeout=60;  
      string secretServer=null;  
      string ssoAdminGroup=null;  
      string affiliateAppMgrGroup=null;  
      // Get current default settings.  
      admin.GetGlobalInfo(out flags, out appDeleteMax, out mappingDeleteMax, out ntpLookupMax, out xplLookupMax, out ticketTimeout, out cacheTimeout, out secretServer, out ssoAdminGroup, out affiliateAppMgrGroup);  
      // Update global settings.  
      admin.UpdateGlobalInfo(SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, ref appDeleteMax, ref mappingDeleteMax, ref ntpLookupMax, ref xplLookupMax, ref ticketTimeout, ref cacheTimeout, null, null, null);   
   }  
   catch  
   {  
      return false;  
   }  
return true;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="10163-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10163-115">See Also</span></span>  
 [<span data-ttu-id="10163-116">使用企业单一登录进行编程</span><span class="sxs-lookup"><span data-stu-id="10163-116">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)