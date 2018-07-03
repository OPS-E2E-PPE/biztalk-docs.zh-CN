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
# <a name="how-to-determine-current-single-sign-on-access"></a>如何确定当前的单一登录访问
可能需要对用户执行的首要任务之一是确定已为当前用户安装了哪些关联应用程序。 通过调用 ISSOMapper.GetApplications 可以执行此查询。  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a>在单一登录数据库中查询对当前用户可用的应用程序  
  
1. 创建 `ISSOMapper` 的一个新实例。  
  
    一般情况下，`ISSOMapper`是从单一登录 (SSO) 检索信息而设计的接口。 最有可能会使用`ISSOMapper`中许多类似的查询。  
  
2. 通过调用 GetApplications 来检索与当前用户相关联的所有应用程序。  
  
    GetApplications 将自动仅返回当前用户的关联应用程序。  
  
   以下代码示例说明了如何查询单一登录数据库：  
  
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