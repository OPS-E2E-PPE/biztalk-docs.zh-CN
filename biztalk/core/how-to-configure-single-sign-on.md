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
# <a name="how-to-configure-single-sign-on"></a>如何配置单一登录
在访问前企业单一登录，需确保企业单一登录已正确设置了为当前用户。 对于大多数配置，您将使用两个接口之一。 `ISSOAdmin` 是，可创建新关联应用程序的通用管理接口。 但是，通过使用 ISSOAdmin.GetGlobalInfo 和 ISSOAdmin.UpdateGlobalInfo，您可以设置各种标志和管理值。 一个可能的任务，如以下过程中所述，确保 SSO 票证已启用的。  
  
### <a name="to-enable-ticketing"></a>若要启用票证  
  
1. 创建的新实例`ISSOAdmin`。  
  
2. 检索当前设置通过`ISSOAdmin.GetGlobalInfo`。  
  
    如有必要，您可能想要确认标志此时设置为正确的值。  
  
3. 更改使用所有相关标志`ISSOAdmin.UpdateGlobalInfo`。  
  
    在此特定情况下是被所有标志都设置为验证并启用票证。  
  
   下面的示例演示如何启用票证使用单一登录。  
  
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