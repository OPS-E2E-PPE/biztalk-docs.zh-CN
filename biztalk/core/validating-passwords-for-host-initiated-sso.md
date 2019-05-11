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
# <a name="validating-passwords-for-host-initiated-sso"></a><span data-ttu-id="aa811-102">验证密码，从而为主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="aa811-102">Validating Passwords for Host Initiated SSO</span></span>
<span data-ttu-id="aa811-103">当主机启动的 SSO 创建关联应用程序时，默认情况下被启用非 Windows 用户的密码验证。</span><span class="sxs-lookup"><span data-stu-id="aa811-103">When an affiliate application for host initiated SSO is created, password validation for the non-Windows user is enabled by default.</span></span> <span data-ttu-id="aa811-104">这意味着在应用程序调用 SSO 以获得访问资源的 Windows 用户标记，他们必须提供非 Windows 用户帐户和非 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="aa811-104">This means when applications call SSO to obtain the Windows user token to access resources, they must provide the non-Windows user account and the non-Windows password.</span></span> <span data-ttu-id="aa811-105">如果密码与该非 Windows 用户的 SSO 数据库中的密码不匹配，访问被拒绝。</span><span class="sxs-lookup"><span data-stu-id="aa811-105">If the password does not match the password in the SSO database for that non-Windows user, access is denied.</span></span> <span data-ttu-id="aa811-106">如有必要，可以关联应用程序禁用密码验证功能。</span><span class="sxs-lookup"><span data-stu-id="aa811-106">If necessary, the password validation feature can be disabled for the affiliate application.</span></span> <span data-ttu-id="aa811-107">密码验证功能适用于这两个个人和主机的主机组类型关联应用程序启动的 SSO。</span><span class="sxs-lookup"><span data-stu-id="aa811-107">The password validation feature applies to both individual and host group type affiliate applications for host initiated SSO.</span></span>  
  
 <span data-ttu-id="aa811-108">各类型主机启动的 SSO 关联应用程序是一个示例 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="aa811-108">An example XML file for Individual type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="aa811-109">在单个应用程序的情况下为主机启动的 SSO，appUserAccount 是组帐户，其中包含具有 1 对 1 映射使用其相应的非 Windows 帐户的 Windows 域帐户用户的列表。</span><span class="sxs-lookup"><span data-stu-id="aa811-109">In the case of individual applications for host initiated SSO, the appUserAccount is a group account that contains the list of Windows domain account users that have a 1 to 1 mapping with their corresponding non-Windows accounts.</span></span>  
  
 <span data-ttu-id="aa811-110">主机组类型主机启动的 SSO 关联应用程序是一个示例 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="aa811-110">An example XML file for host group type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="aa811-111">启动的 SSO 应用程序的主机组中，appUserAccount 必须是单独的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aa811-111">In group applications for host initiated SSO, the appUserAccount must be an individual user account.</span></span> <span data-ttu-id="aa811-112">它是所有非 Windows 帐户映射到此帐户。</span><span class="sxs-lookup"><span data-stu-id="aa811-112">It is this account that all non-Windows accounts are mapped to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa811-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa811-113">See Also</span></span>  
 [<span data-ttu-id="aa811-114">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="aa811-114">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)