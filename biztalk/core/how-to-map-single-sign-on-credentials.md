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
# <a name="how-to-map-single-sign-on-credentials"></a>如何将单一登录凭据的映射
当您知道，在企业单一登录数据库中已具有关联应用程序时，可以将用户的凭据映射到该应用程序。 将当前用户的凭据映射到关联应用程序需要您使用的组合`ISSOMapper`和`ISSOMapping`接口。  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a>关联应用程序和用户凭据之间进行映射  
  
1. 创建的新实例`ISSOMapper`和`ISSOMapping`。  
  
2. 设置`ISSOMapping`相关值的属性。  
  
    相关属性`ISSOMapping`是用户的 Microsoft Windows 域名、 Windows 用户名称、 关联应用程序的名称和外部用户名称。  
  
3. 通过调用 ISSOMapping.Create 创建映射。  
  
    调用`ISSOMapping.Create`传播映射到企业单一登录服务器的本地副本。  
  
4. 通过调用映射设置凭据`ISSOMapper.SetExternalCredentials`。  
  
5. 启用通过调用映射`ISSOMapping.Enable`。  
  
   下面的示例演示如何将添加一个指定的企业单一登录应用程序和用户之间的映射。  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用企业单一登录编程](../core/programming-with-enterprise-single-sign-on.md)