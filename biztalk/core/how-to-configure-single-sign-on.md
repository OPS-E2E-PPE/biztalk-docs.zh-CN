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
ms.openlocfilehash: 3b23e2bb61f4549e642bcd9a59f56bc232b40038
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019932"
---
# <a name="how-to-configure-single-sign-on"></a>如何配置单一登录
在访问企业单一登录前，应确保为当前用户正确设置了企业单一登录。 对于大多数配置，您将使用两个接口之一。 `ISSOAdmin` 是，可创建新关联应用程序的通用管理接口。 但是，通过使用 ISSOAdmin.GetGlobalInfo 和 ISSOAdmin.UpdateGlobalInfo，您可以设置各种标志和管理值。 其中一个可以实现的任务是确保启用 SSO 票证，如以下过程中所述：  
  
### <a name="to-enable-ticketing"></a>启用票证  
  
1. 创建 `ISSOAdmin` 的一个新实例。  
  
2. 检索当前设置通过`ISSOAdmin.GetGlobalInfo`。  
  
    如果需要，您可能要确认标志此时已设置为正确的值。  
  
3. 更改使用所有相关标志`ISSOAdmin.UpdateGlobalInfo`。  
  
    在此特定情况下，所有标志都将设置为验证并启用票证。  
  
   下例说明了如何使用单一登录启用票证：  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用企业单一登录编程](../core/programming-with-enterprise-single-sign-on.md)