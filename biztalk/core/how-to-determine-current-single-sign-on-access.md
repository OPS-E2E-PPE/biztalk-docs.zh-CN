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
# <a name="how-to-determine-current-single-sign-on-access"></a>如何确定当前的单一登录访问
可能需要对用户执行的首要任务之一是确定哪些关联应用程序已被设置为当前用户。 您可以执行此查询与调用 issomapper.getapplications。  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a>若要为当前用户的应用程序实现单一登录数据库中查询  
  
1. 创建的新实例`ISSOMapper`。  
  
    一般情况下，`ISSOMapper`是从单一登录 (SSO) 检索信息而设计的接口。 最有可能会使用`ISSOMapper`中许多类似的查询。  
  
2. 通过调用 getapplications 来检索所有与应用程序了属于当前用户。  
  
    GetApplications 将自动返回仅当前用户的关联应用程序。  
  
   下面的代码示例演示如何查询单一登录数据库。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用企业单一登录编程](../core/programming-with-enterprise-single-sign-on.md)