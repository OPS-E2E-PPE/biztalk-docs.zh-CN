---
title: "验证密码为主机启动的 SSO |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, host initiated [SSO]
- host initiated SSO, passwords
ms.assetid: 3cc1d68a-27ac-46ce-ba1e-21139a9df55e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03a33eb83630831863f231ff9594e3082f0faa98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-passwords-for-host-initiated-sso"></a><span data-ttu-id="8ab01-102">验证密码为主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="8ab01-102">Validating Passwords for Host Initiated SSO</span></span>
<span data-ttu-id="8ab01-103">在为主机启动的 SSO 创建关联应用程序时，默认情况下将启用对非 Windows 用户进行的密码验证。</span><span class="sxs-lookup"><span data-stu-id="8ab01-103">When an affiliate application for host initiated SSO is created, password validation for the non-Windows user is enabled by default.</span></span> <span data-ttu-id="8ab01-104">这意味着如果应用程序调用 SSO 以获得用于访问资源的 Windows 用户标记，则其必须提供非 Windows 用户帐户以及非 Windows 密码。</span><span class="sxs-lookup"><span data-stu-id="8ab01-104">This means when applications call SSO to obtain the Windows user token to access resources, they must provide the non-Windows user account and the non-Windows password.</span></span> <span data-ttu-id="8ab01-105">如果密码与 SSO 数据库中该非 Windows 用户的密码不匹配，则访问将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="8ab01-105">If the password does not match the password in the SSO database for that non-Windows user, access is denied.</span></span> <span data-ttu-id="8ab01-106">如有必要，可为关联应用程序禁用密码验证功能。</span><span class="sxs-lookup"><span data-stu-id="8ab01-106">If necessary, the password validation feature can be disabled for the affiliate application.</span></span> <span data-ttu-id="8ab01-107">密码验证功能同时适用于主机启动的 SSO 的“单项”类型和“主机组”类型的关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ab01-107">The password validation feature applies to both individual and host group type affiliate applications for host initiated SSO.</span></span>  
  
 <span data-ttu-id="8ab01-108">以下列出了一个“单项”类型主机启动的 SSO 关联应用程序的示例 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="8ab01-108">An example XML file for Individual type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="8ab01-109">对于主机启动的 SSO 的“单项”应用程序，appUserAccount 是一个组帐户，其中包含与其对应的非 Windows 帐户之间存在一对一映射的 Windows 域帐户用户的列表。</span><span class="sxs-lookup"><span data-stu-id="8ab01-109">In the case of individual applications for host initiated SSO, the appUserAccount is a group account that contains the list of Windows domain account users that have a 1 to 1 mapping with their corresponding non-Windows accounts.</span></span>  
  
 <span data-ttu-id="8ab01-110">以下列出了一个“主机组”类型主机启动的 SSO 关联应用程序的示例 XML 文件：</span><span class="sxs-lookup"><span data-stu-id="8ab01-110">An example XML file for host group type host initiated SSO affiliate application is:</span></span>  
  
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
  
 <span data-ttu-id="8ab01-111">在主机启动的 SSO 的组应用程序中，appUserAccount 必须是一个单独的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8ab01-111">In group applications for host initiated SSO, the appUserAccount must be an individual user account.</span></span> <span data-ttu-id="8ab01-112">所有的非 Windows 帐户均映射到此帐户。</span><span class="sxs-lookup"><span data-stu-id="8ab01-112">It is this account that all non-Windows accounts are mapped to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ab01-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ab01-113">See Also</span></span>  
 [<span data-ttu-id="8ab01-114">主机启动的 SSO</span><span class="sxs-lookup"><span data-stu-id="8ab01-114">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)