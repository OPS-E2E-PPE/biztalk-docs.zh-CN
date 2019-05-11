---
title: 如何配置单一登录 |Microsoft Docs
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
ms.openlocfilehash: f5175b0bec313246cb9de8d85869029053469327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341247"
---
# <a name="how-to-configure-single-sign-on"></a><span data-ttu-id="9155a-102">如何配置单一登录</span><span class="sxs-lookup"><span data-stu-id="9155a-102">How to Configure Single Sign-On</span></span>
<span data-ttu-id="9155a-103">在访问前企业单一登录，需确保企业单一登录已正确设置了为当前用户。</span><span class="sxs-lookup"><span data-stu-id="9155a-103">Before accessing Enterprise Single Sign-On, you should make sure that Enterprise Single Sign-On is set correctly for the current user.</span></span> <span data-ttu-id="9155a-104">对于大多数配置，您将使用两个接口之一。</span><span class="sxs-lookup"><span data-stu-id="9155a-104">For most configurations, you use one of two interfaces.</span></span> <span data-ttu-id="9155a-105">`ISSOAdmin` 是，可创建新关联应用程序的通用管理接口。</span><span class="sxs-lookup"><span data-stu-id="9155a-105">`ISSOAdmin` is the general administration interface that enables you to create new affiliation applications.</span></span> <span data-ttu-id="9155a-106">但是，通过使用 ISSOAdmin.GetGlobalInfo 和 ISSOAdmin.UpdateGlobalInfo，您可以设置各种标志和管理值。</span><span class="sxs-lookup"><span data-stu-id="9155a-106">However, by using ISSOAdmin.GetGlobalInfo and ISSOAdmin.UpdateGlobalInfo, you can set a variety of flags and administration values.</span></span> <span data-ttu-id="9155a-107">一个可能的任务，如以下过程中所述，确保 SSO 票证已启用的。</span><span class="sxs-lookup"><span data-stu-id="9155a-107">One possible task, as described in the following procedure, is to ensure that SSO ticketing has been enabled.</span></span>  
  
### <a name="to-enable-ticketing"></a><span data-ttu-id="9155a-108">若要启用票证</span><span class="sxs-lookup"><span data-stu-id="9155a-108">To enable ticketing</span></span>  
  
1. <span data-ttu-id="9155a-109">创建的新实例`ISSOAdmin`。</span><span class="sxs-lookup"><span data-stu-id="9155a-109">Create a new instance of `ISSOAdmin`.</span></span>  
  
2. <span data-ttu-id="9155a-110">检索当前设置通过`ISSOAdmin.GetGlobalInfo`。</span><span class="sxs-lookup"><span data-stu-id="9155a-110">Retrieve the current settings through `ISSOAdmin.GetGlobalInfo`.</span></span>  
  
    <span data-ttu-id="9155a-111">如有必要，您可能想要确认标志此时设置为正确的值。</span><span class="sxs-lookup"><span data-stu-id="9155a-111">If necessary, you may want to confirm that the flags are set to the correct values at this point.</span></span>  
  
3. <span data-ttu-id="9155a-112">更改使用所有相关标志`ISSOAdmin.UpdateGlobalInfo`。</span><span class="sxs-lookup"><span data-stu-id="9155a-112">Change any relevant flags using `ISSOAdmin.UpdateGlobalInfo`.</span></span>  
  
    <span data-ttu-id="9155a-113">在此特定情况下是被所有标志都设置为验证并启用票证。</span><span class="sxs-lookup"><span data-stu-id="9155a-113">In this particular case, all the flags are being set to validate and enable tickets.</span></span>  
  
   <span data-ttu-id="9155a-114">下面的示例演示如何启用票证使用单一登录。</span><span class="sxs-lookup"><span data-stu-id="9155a-114">The following example shows how to enable ticketing using Single Sign-On.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9155a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="9155a-115">See Also</span></span>  
 [<span data-ttu-id="9155a-116">使用企业单一登录编程</span><span class="sxs-lookup"><span data-stu-id="9155a-116">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)