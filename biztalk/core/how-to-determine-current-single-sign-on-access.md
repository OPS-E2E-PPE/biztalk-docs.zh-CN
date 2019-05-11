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
ms.openlocfilehash: 781fde1a4b7af82c851fb80a9df32a6eb93d8ce7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338589"
---
# <a name="how-to-determine-current-single-sign-on-access"></a><span data-ttu-id="ddc65-102">如何确定当前的单一登录访问</span><span class="sxs-lookup"><span data-stu-id="ddc65-102">How to Determine Current Single Sign-On Access</span></span>
<span data-ttu-id="ddc65-103">可能需要对用户执行的首要任务之一是确定哪些关联应用程序已被设置为当前用户。</span><span class="sxs-lookup"><span data-stu-id="ddc65-103">One of the first tasks you might need to perform for a user is to determine what affiliated applications have already been set up for the current user.</span></span> <span data-ttu-id="ddc65-104">您可以执行此查询与调用 issomapper.getapplications。</span><span class="sxs-lookup"><span data-stu-id="ddc65-104">You can perform this query with a call to ISSOMapper.GetApplications.</span></span>  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a><span data-ttu-id="ddc65-105">若要为当前用户的应用程序实现单一登录数据库中查询</span><span class="sxs-lookup"><span data-stu-id="ddc65-105">To query the Single Sign-On database for the applications available to the current user</span></span>  
  
1. <span data-ttu-id="ddc65-106">创建的新实例`ISSOMapper`。</span><span class="sxs-lookup"><span data-stu-id="ddc65-106">Create a new instance of `ISSOMapper`.</span></span>  
  
    <span data-ttu-id="ddc65-107">一般情况下，`ISSOMapper`是从单一登录 (SSO) 检索信息而设计的接口。</span><span class="sxs-lookup"><span data-stu-id="ddc65-107">In general, `ISSOMapper` is an interface designed to retrieve information from Single Sign-On (SSO).</span></span> <span data-ttu-id="ddc65-108">最有可能会使用`ISSOMapper`中许多类似的查询。</span><span class="sxs-lookup"><span data-stu-id="ddc65-108">You will most likely use `ISSOMapper` in many similar queries.</span></span>  
  
2. <span data-ttu-id="ddc65-109">通过调用 getapplications 来检索所有与应用程序了属于当前用户。</span><span class="sxs-lookup"><span data-stu-id="ddc65-109">Retrieve all applications that are affiliated with the current user by calling GetApplications.</span></span>  
  
    <span data-ttu-id="ddc65-110">GetApplications 将自动返回仅当前用户的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="ddc65-110">GetApplications automatically returns only the affiliated applications of the current user.</span></span>  
  
   <span data-ttu-id="ddc65-111">下面的代码示例演示如何查询单一登录数据库。</span><span class="sxs-lookup"><span data-stu-id="ddc65-111">The following code example demonstrates how to query the Single Sign-On database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ddc65-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddc65-112">See Also</span></span>  
 [<span data-ttu-id="ddc65-113">使用企业单一登录编程</span><span class="sxs-lookup"><span data-stu-id="ddc65-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)