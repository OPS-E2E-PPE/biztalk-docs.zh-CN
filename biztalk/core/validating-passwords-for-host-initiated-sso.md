---
title: 验证密码，从而为主机启动的 SSO |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, host initiated [SSO]
- host initiated SSO, passwords
ms.assetid: 3cc1d68a-27ac-46ce-ba1e-21139a9df55e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac003083157c69be0fcabaeb37ff7064b76a6e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279557"
---
# <a name="validating-passwords-for-host-initiated-sso"></a>验证密码，从而为主机启动的 SSO
当主机启动的 SSO 创建关联应用程序时，默认情况下被启用非 Windows 用户的密码验证。 这意味着在应用程序调用 SSO 以获得访问资源的 Windows 用户标记，他们必须提供非 Windows 用户帐户和非 Windows 密码。 如果密码与该非 Windows 用户的 SSO 数据库中的密码不匹配，访问被拒绝。 如有必要，可以关联应用程序禁用密码验证功能。 密码验证功能适用于这两个个人和主机的主机组类型关联应用程序启动的 SSO。  
  
 各类型主机启动的 SSO 关联应用程序是一个示例 XML 文件：  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserGroupAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminGroupAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags groupApp="no"  configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 在单个应用程序的情况下为主机启动的 SSO，appUserAccount 是组帐户，其中包含具有 1 对 1 映射使用其相应的非 Windows 帐户的 Windows 域帐户用户的列表。  
  
 主机组类型主机启动的 SSO 关联应用程序是一个示例 XML 文件：  
  
```  
<sso>  
<application name="SAP">  
<description>The SAP application</description>   
<contact>someone@example.com</contact>   
<appuserAccount>domain\AppUserAccount</appuserAccount>   
<appAdminAccount>domain\AppAdminGroupAccount</appAdminAccount>   
<field ordinal="0" label="User Id" masked="no" />   
<field ordinal="1" label="Password" masked="yes" />   
<flags  configStoreApp="no" allowTickets="no" validateTickets="yes" allowLocalAccounts="no" timeoutTickets="yes" adminAccountSame="no" enableApp="no" />  
</application>  
</sso>  
  
```  
  
 启动的 SSO 应用程序的主机组中，appUserAccount 必须是单独的用户帐户。 它是所有非 Windows 帐户映射到此帐户。  
  
## <a name="see-also"></a>请参阅  
 [主机启动的 SSO](../core/host-initiated-sso.md)