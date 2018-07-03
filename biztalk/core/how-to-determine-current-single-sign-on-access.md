---
title: 如何确定当前的单一登录访问 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cab68dfc-27cd-4f7c-a0df-20c670306358
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c57cfae2c2b7545854fa7891f099a19ff7bb0098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014766"
---
# <a name="how-to-determine-current-single-sign-on-access"></a><span data-ttu-id="52801-102">如何确定当前的单一登录访问</span><span class="sxs-lookup"><span data-stu-id="52801-102">How to Determine Current Single Sign-On Access</span></span>
<span data-ttu-id="52801-103">可能需要对用户执行的首要任务之一是确定已为当前用户安装了哪些关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="52801-103">One of the first tasks you might need to perform for a user is to determine what affiliated applications have already been set up for the current user.</span></span> <span data-ttu-id="52801-104">通过调用 ISSOMapper.GetApplications 可以执行此查询。</span><span class="sxs-lookup"><span data-stu-id="52801-104">You can perform this query with a call to ISSOMapper.GetApplications.</span></span>  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a><span data-ttu-id="52801-105">在单一登录数据库中查询对当前用户可用的应用程序</span><span class="sxs-lookup"><span data-stu-id="52801-105">To query the Single Sign-On database for the applications available to the current user</span></span>  
  
1. <span data-ttu-id="52801-106">创建 `ISSOMapper` 的一个新实例。</span><span class="sxs-lookup"><span data-stu-id="52801-106">Create a new instance of `ISSOMapper`.</span></span>  
  
    <span data-ttu-id="52801-107">一般情况下，`ISSOMapper`是从单一登录 (SSO) 检索信息而设计的接口。</span><span class="sxs-lookup"><span data-stu-id="52801-107">In general, `ISSOMapper` is an interface designed to retrieve information from Single Sign-On (SSO).</span></span> <span data-ttu-id="52801-108">最有可能会使用`ISSOMapper`中许多类似的查询。</span><span class="sxs-lookup"><span data-stu-id="52801-108">You will most likely use `ISSOMapper` in many similar queries.</span></span>  
  
2. <span data-ttu-id="52801-109">通过调用 GetApplications 来检索与当前用户相关联的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="52801-109">Retrieve all applications that are affiliated with the current user by calling GetApplications.</span></span>  
  
    <span data-ttu-id="52801-110">GetApplications 将自动仅返回当前用户的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="52801-110">GetApplications automatically returns only the affiliated applications of the current user.</span></span>  
  
   <span data-ttu-id="52801-111">以下代码示例说明了如何查询单一登录数据库：</span><span class="sxs-lookup"><span data-stu-id="52801-111">The following code example demonstrates how to query the Single Sign-On database.</span></span>  
  
```  
private static string[] Applications=null;  
. . .  
public static string[] GetCurrentUserApplications()  
{  
   if(Applications==null)  
   {  
      string[] descs;  
      string[] contacts;  
      ISSOMapper mapper=new ISSOMapper();  
      mapper.GetApplications(out Applications, out descs, out contacts);  
   }  
   return Applications;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="52801-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="52801-112">See Also</span></span>  
 [<span data-ttu-id="52801-113">使用企业单一登录编程</span><span class="sxs-lookup"><span data-stu-id="52801-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)