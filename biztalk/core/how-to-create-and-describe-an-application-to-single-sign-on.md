---
title: 如何创建和描述为单一登录的应用程序 |Microsoft 文档
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
ms.openlocfilehash: 423439795d9a3822427edbee2e062c3c0aa6bb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249085"
---
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a>如何创建和描述为单一登录的应用程序
您可能需要执行的一个常见管理任务是向企业单一登录 (SSO) 数据库中添加关联应用程序。 通过向企业 SSO 数据库中添加关联应用程序，您可以将用户和凭据与关联应用程序相关联。  
  
> [!NOTE]
>  创建关联的应用程序要求属于“SSO Affiliate Administrator”帐户或具有更高权限的帐户。  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a>在 SSO 数据库中创建和描述应用程序  
  
1.  创建一个新`ISSOAdmin`对象。  
  
2.  创建新的应用程序通过调用`ISSOAdmin.CreateApplication`。  
  
3.  添加描述通过调用应用程序的相关字段`ISSOAdmin.CreateFieldInfo`。  
  
     在执行此步骤的过程中，您告诉数据库应用程序具有用户和相关联的密码。  
  
4.  新创建的说明推送至通过调用服务器`ISSOAdmin.UpdateApplication`或`ISSOAdmin2.UpdateApplication2`。  
  
     两种方法之间的差异在于`UpdateApplication2`使用`IPropertyBag`当更新的方式来描述应用程序，而`UpdateApplication`具有多个参数。  
  
5.  清除你通过调用所做的更改的本地缓存`ISSOAdmin.PurgeCacheForApplication`。  
  
     清除本地缓存是一种安全措施，它可以防止在步骤 3 中描述的名称和密码存在于不安全的位置。  
  
 下面的示例描述了如何创建应用程序和添加字段信息。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [使用企业单一登录进行编程](../core/programming-with-enterprise-single-sign-on.md)