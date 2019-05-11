---
title: 用于 JD Edwards EnterpriseOne 的单一登录和 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83fefe6ae447a5f68c9516e6fb92ab6e1c0b0614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393032"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="74957-102">用于 JD Edwards EnterpriseOne 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="74957-102">Single Sign-On and BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="74957-103">当您在用于 JD Edwards EnterpriseOne 的 Microsoft 适配器使用单一登录 (SSO) 时，适配器将从 SSO 凭据数据库获取凭据。</span><span class="sxs-lookup"><span data-stu-id="74957-103">When you use Single Sign-On (SSO) with Microsoft   Adapter for JD Edwards EnterpriseOne, the adapter obtains the credentials from the SSO Credentials database.</span></span> <span data-ttu-id="74957-104">因此，不需要输入服务器系统的登录凭据**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="74957-104">Therefore, you do not need to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="74957-105">在设计时用于 JD Edwards EnterpriseOne 的 BizTalk 适配器获取的系统 （适用于指定的关联应用程序） 的上下文的启动的用户的凭据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。</span><span class="sxs-lookup"><span data-stu-id="74957-105">At design-time, BizTalk Adapter for JD Edwards EnterpriseOne obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="74957-106">该用户应为应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="74957-106">That user should be an Application User.</span></span> <span data-ttu-id="74957-107">在运行时，使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 接收适配器用作使用 SSO 时的简单直通方案中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="74957-107">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="74957-108">处理请求</span><span class="sxs-lookup"><span data-stu-id="74957-108">Processing Requests</span></span>  
 <span data-ttu-id="74957-109">当 Internet 信息服务 (IIS) 从 Web 客户端收到 HTTP 请求时，IIS 会进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="74957-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="74957-110">ISAPI 扩展模拟 Windows 用户，并调用要获取加密的票证的 SSO 凭据存储区。</span><span class="sxs-lookup"><span data-stu-id="74957-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="74957-111">此票证在消息的上下文中以 SSOTicket 属性形式存储。</span><span class="sxs-lookup"><span data-stu-id="74957-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="74957-112">消息然后定向到 Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="74957-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="74957-113">当用于 JD Edwards EnterpriseOne 的 BizTalk 适配器从 Messagebox 数据库接收消息时，它将调用`ValidateAndRedeemTicket`使用加密票证和关联应用程序名来从 SSO 存储中检索登录凭据。</span><span class="sxs-lookup"><span data-stu-id="74957-113">When BizTalk Adapter for JD Edwards EnterpriseOne receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="74957-114">然后，适配器使用的外部凭据连接到系统并处理该请求。</span><span class="sxs-lookup"><span data-stu-id="74957-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74957-115">SSO 配置是 BizTalk Server 安装程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="74957-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="74957-116">如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="74957-116">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="74957-117">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="74957-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74957-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="74957-118">See Also</span></span>  
 <span data-ttu-id="74957-119">[创建关联应用程序](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="74957-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="74957-120">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="74957-120">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)