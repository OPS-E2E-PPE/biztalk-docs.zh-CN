---
title: 如何将映射单一登录凭据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e847bde9-7a4c-4b81-8ad6-6a7cf23d19a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95a56da0d30ec0f30c556dcab01b3789f3e1fb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336271"
---
# <a name="how-to-map-single-sign-on-credentials"></a><span data-ttu-id="d485d-102">如何将单一登录凭据的映射</span><span class="sxs-lookup"><span data-stu-id="d485d-102">How to Map Single Sign-On Credentials</span></span>
<span data-ttu-id="d485d-103">当您知道，在企业单一登录数据库中已具有关联应用程序时，可以将用户的凭据映射到该应用程序。</span><span class="sxs-lookup"><span data-stu-id="d485d-103">When you know that you have affiliated applications in your Enterprise Single Sign-On database, you can map the credentials for a user to that application.</span></span> <span data-ttu-id="d485d-104">将当前用户的凭据映射到关联应用程序需要您使用的组合`ISSOMapper`和`ISSOMapping`接口。</span><span class="sxs-lookup"><span data-stu-id="d485d-104">Mapping the credentials of the current user to an affiliated application requires that you use a combination of the `ISSOMapper` and `ISSOMapping` interfaces.</span></span>  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a><span data-ttu-id="d485d-105">关联应用程序和用户凭据之间进行映射</span><span class="sxs-lookup"><span data-stu-id="d485d-105">To map between an affiliated application and user credentials</span></span>  
  
1. <span data-ttu-id="d485d-106">创建的新实例`ISSOMapper`和`ISSOMapping`。</span><span class="sxs-lookup"><span data-stu-id="d485d-106">Create new instances of `ISSOMapper` and `ISSOMapping`.</span></span>  
  
2. <span data-ttu-id="d485d-107">设置`ISSOMapping`相关值的属性。</span><span class="sxs-lookup"><span data-stu-id="d485d-107">Set the `ISSOMapping` properties to the relevant values.</span></span>  
  
    <span data-ttu-id="d485d-108">相关属性`ISSOMapping`是用户的 Microsoft Windows 域名、 Windows 用户名称、 关联应用程序的名称和外部用户名称。</span><span class="sxs-lookup"><span data-stu-id="d485d-108">The relevant properties for `ISSOMapping` are the Microsoft Windows domain name of the user, the Windows user name, the name of the affiliated application, and the external user name.</span></span>  
  
3. <span data-ttu-id="d485d-109">通过调用 ISSOMapping.Create 创建映射。</span><span class="sxs-lookup"><span data-stu-id="d485d-109">Create the mapping with a call to ISSOMapping.Create.</span></span>  
  
    <span data-ttu-id="d485d-110">调用`ISSOMapping.Create`传播映射到企业单一登录服务器的本地副本。</span><span class="sxs-lookup"><span data-stu-id="d485d-110">Calling `ISSOMapping.Create` propagates the local copy of the mapping out to the Enterprise Single Sign-On server.</span></span>  
  
4. <span data-ttu-id="d485d-111">通过调用映射设置凭据`ISSOMapper.SetExternalCredentials`。</span><span class="sxs-lookup"><span data-stu-id="d485d-111">Set the credentials on the mapping with a call to `ISSOMapper.SetExternalCredentials`.</span></span>  
  
5. <span data-ttu-id="d485d-112">启用通过调用映射`ISSOMapping.Enable`。</span><span class="sxs-lookup"><span data-stu-id="d485d-112">Enable the mapping with a call to `ISSOMapping.Enable`.</span></span>  
  
   <span data-ttu-id="d485d-113">下面的示例演示如何将添加一个指定的企业单一登录应用程序和用户之间的映射。</span><span class="sxs-lookup"><span data-stu-id="d485d-113">The following example shows how to add mapping between a specified Enterprise Single Sign-On application and a user.</span></span>  
  
```  
public static bool AddMapping(string application, string user, string XU, string XP)  
{  
   try  
   {  
      // Set mapping.  
      ISSOMapper mapper=new ISSOMapper();  
      ISSOMapping mapping=new ISSOMapping();  
     string username=user.Substring(user.IndexOf('\\')+1);  
      string userdomain=user.Substring(0, user.IndexOf('\\'));  
      mapping.WindowsDomainName=userdomain;  
      mapping.WindowsUserName=username;  
      mapping.ApplicationName=application;  
      mapping.ExternalUserName=XU;  
      mapping.Create(0);  
      // Set credentials.  
      string[] credentials=new string[]{XP};  
      mapper.SetExternalCredentials(application, XU, ref credentials);  
      mapping.Enable(0);  
   }  
   catch  
   {  
      return false;  
   }  
   return true;  
      }  
```  
  
## <a name="see-also"></a><span data-ttu-id="d485d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d485d-114">See Also</span></span>  
 [<span data-ttu-id="d485d-115">使用企业单一登录编程</span><span class="sxs-lookup"><span data-stu-id="d485d-115">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)