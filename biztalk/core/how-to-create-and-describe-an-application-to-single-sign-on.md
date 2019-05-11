---
title: 如何创建和描述以单一登录的应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d717885-b132-4ba0-a93b-03377ac5eb97
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b914cc54e48aaa4a58d3f370f50132265f97def
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385511"
---
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a>如何创建和描述以单一登录的应用程序
可能需要执行一个常见管理任务添加到企业单一登录 (SSO) 数据库的关联应用程序。 添加到企业 SSO 数据库的关联应用程序，可将用户和凭据与关联应用程序相关联。  
  
> [!NOTE]
>  创建关联应用程序需要在"SSO 关联管理员"帐户或更高的成员身份。  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a>若要创建和描述在 SSO 数据库中的应用程序  
  
1. 创建一个新`ISSOAdmin`对象。  
  
2. 创建新的应用程序通过调用`ISSOAdmin.CreateApplication`。  
  
3. 添加描述通过调用应用程序的相关字段`ISSOAdmin.CreateFieldInfo`。  
  
    在此步骤中，您告诉数据库应用程序具有用户和相关联的密码。  
  
4. 新创建的描述推送到通过调用服务器`ISSOAdmin.UpdateApplication`或`ISSOAdmin2.UpdateApplication2`。  
  
    两个方法之间的差异在于`UpdateApplication2`使用`IPropertyBag`的方式来描述应用程序更新，而`UpdateApplication`具有多个参数。  
  
5. 通过调用所做的更改的本地缓存中清除`ISSOAdmin.PurgeCacheForApplication`。  
  
    清除本地缓存是一种安全措施，它可以防止名称和描述中步骤 3 以不安全的位置中存在的密码。  
  
   下面的示例演示如何创建应用程序并添加字段信息。  
  
```  
public static bool AddApplication(string name, string admins, string users)  
    {  
       try  
       {  
          ISSOAdmin admin=new ISSOAdmin();  
          // Create application.  
          admin.CreateApplication(name, "SSO Sample Application", "administrator@ssoaffiliateapplication.com", users, admins, SSOFlag.SSO_WINDOWS_TO_EXTERNAL | SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, 2);  
          // Add fields.  
          admin.CreateFieldInfo(name, "User Id", SSOFlag.SSO_FLAG_NONE);  
          admin.CreateFieldInfo(name, "Password", SSOFlag.SSO_FLAG_FIELD_INFO_MASK);  
          // Enable application.  
          admin.UpdateApplication(name, null, null, null, null, SSOFlag.SSO_FLAG_ENABLED, SSOFlag.SSO_FLAG_ENABLED);  
          // Purge changes.  
          admin.PurgeCacheForApplication(name);  
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