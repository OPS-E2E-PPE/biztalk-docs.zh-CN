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
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a><span data-ttu-id="b34b0-102">如何创建和描述以单一登录的应用程序</span><span class="sxs-lookup"><span data-stu-id="b34b0-102">How to Create and Describe an Application to Single Sign-On</span></span>
<span data-ttu-id="b34b0-103">可能需要执行一个常见管理任务添加到企业单一登录 (SSO) 数据库的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="b34b0-103">A common administrative task that you might need to perform is adding an affiliate application into the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="b34b0-104">添加到企业 SSO 数据库的关联应用程序，可将用户和凭据与关联应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="b34b0-104">Adding an affiliate application to the Enterprise SSO database enables you to associate users and credentials with the affiliated application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b34b0-105">创建关联应用程序需要在"SSO 关联管理员"帐户或更高的成员身份。</span><span class="sxs-lookup"><span data-stu-id="b34b0-105">Creating an affiliated application requires membership in the "SSO Affiliate Administrator" account or above.</span></span>  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a><span data-ttu-id="b34b0-106">若要创建和描述在 SSO 数据库中的应用程序</span><span class="sxs-lookup"><span data-stu-id="b34b0-106">To create and describe an application in the SSO database</span></span>  
  
1. <span data-ttu-id="b34b0-107">创建一个新`ISSOAdmin`对象。</span><span class="sxs-lookup"><span data-stu-id="b34b0-107">Create a new `ISSOAdmin` object.</span></span>  
  
2. <span data-ttu-id="b34b0-108">创建新的应用程序通过调用`ISSOAdmin.CreateApplication`。</span><span class="sxs-lookup"><span data-stu-id="b34b0-108">Create a new application with a call to `ISSOAdmin.CreateApplication`.</span></span>  
  
3. <span data-ttu-id="b34b0-109">添加描述通过调用应用程序的相关字段`ISSOAdmin.CreateFieldInfo`。</span><span class="sxs-lookup"><span data-stu-id="b34b0-109">Add the relevant fields describing the application with a call to `ISSOAdmin.CreateFieldInfo`.</span></span>  
  
    <span data-ttu-id="b34b0-110">在此步骤中，您告诉数据库应用程序具有用户和相关联的密码。</span><span class="sxs-lookup"><span data-stu-id="b34b0-110">During this step, you tell the database that an application has users and associated passwords.</span></span>  
  
4. <span data-ttu-id="b34b0-111">新创建的描述推送到通过调用服务器`ISSOAdmin.UpdateApplication`或`ISSOAdmin2.UpdateApplication2`。</span><span class="sxs-lookup"><span data-stu-id="b34b0-111">Push the newly created description out to the server with a call to `ISSOAdmin.UpdateApplication` or `ISSOAdmin2.UpdateApplication2`.</span></span>  
  
    <span data-ttu-id="b34b0-112">两个方法之间的差异在于`UpdateApplication2`使用`IPropertyBag`的方式来描述应用程序更新，而`UpdateApplication`具有多个参数。</span><span class="sxs-lookup"><span data-stu-id="b34b0-112">The difference between the two methods is that `UpdateApplication2` uses an `IPropertyBag` as the way to describe the application updates, while `UpdateApplication` has multiple parameters.</span></span>  
  
5. <span data-ttu-id="b34b0-113">通过调用所做的更改的本地缓存中清除`ISSOAdmin.PurgeCacheForApplication`。</span><span class="sxs-lookup"><span data-stu-id="b34b0-113">Purge the local cache for the changes you made by calling `ISSOAdmin.PurgeCacheForApplication`.</span></span>  
  
    <span data-ttu-id="b34b0-114">清除本地缓存是一种安全措施，它可以防止名称和描述中步骤 3 以不安全的位置中存在的密码。</span><span class="sxs-lookup"><span data-stu-id="b34b0-114">Purging the local cache is a security measure that prevents having the names and passwords that you describe in step 3 to exist in an unsecured location.</span></span>  
  
   <span data-ttu-id="b34b0-115">下面的示例演示如何创建应用程序并添加字段信息。</span><span class="sxs-lookup"><span data-stu-id="b34b0-115">The following example shows how to create an application and add field information.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b34b0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b34b0-116">See Also</span></span>  
 [<span data-ttu-id="b34b0-117">使用企业单一登录编程</span><span class="sxs-lookup"><span data-stu-id="b34b0-117">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)