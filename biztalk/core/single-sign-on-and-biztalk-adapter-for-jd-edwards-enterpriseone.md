---
title: "有关博士 Edwards EnterpriseOne 单一登录和 BizTalk 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182e73ed45a1473286a301cf859e619cc5d21287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="4c48d-102">JD Edwards EnterpriseOne 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="4c48d-102">Single Sign-On and BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="4c48d-103">当您对用于 JD Edwards EnterpriseOne 的 Microsoft 适配器使用单一登录 (SSO) 时,适配器从 SSO 凭据数据库获取凭据。</span><span class="sxs-lookup"><span data-stu-id="4c48d-103">When you use Single Sign-On (SSO) with Microsoft   Adapter for JD Edwards EnterpriseOne, the adapter obtains the credentials from the SSO Credentials database.</span></span> <span data-ttu-id="4c48d-104">因此，不需要输入中的服务器系统的登录凭据**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="4c48d-104">Therefore, you do not need to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="4c48d-105">在设计时，用于 JD Edwards EnterpriseOne 的 BizTalk 适配器即会在启动 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目的用户上下文中，为指定的关联应用程序获取用于系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="4c48d-105">At design-time, BizTalk Adapter for JD Edwards EnterpriseOne obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project.</span></span> <span data-ttu-id="4c48d-106">此用户应为应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="4c48d-106">That user should be an Application User.</span></span> <span data-ttu-id="4c48d-107">运行时，将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收适配器用作使用 SSO 时的直通方案中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="4c48d-107">At run time, use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="4c48d-108">处理请求</span><span class="sxs-lookup"><span data-stu-id="4c48d-108">Processing Requests</span></span>  
 <span data-ttu-id="4c48d-109">当 Internet 信息服务 (IIS) 从 Web 客户端接收到 HTTP 请求时，IIS 将验证该用户。</span><span class="sxs-lookup"><span data-stu-id="4c48d-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="4c48d-110">使用 ISAPI 扩展插件模拟 Windows 用户，并调用要获得加密的票证的 SSO 凭据存储区。</span><span class="sxs-lookup"><span data-stu-id="4c48d-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="4c48d-111">此票证在消息上下文中以 SSOTicket 属性形式存储。</span><span class="sxs-lookup"><span data-stu-id="4c48d-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="4c48d-112">消息即定向到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="4c48d-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="4c48d-113">当用于 JD Edwards EnterpriseOne 的 BizTalk 适配器从 MessageBox 数据库接收消息时，它会使用加密票证和关联应用程序名来调用 `ValidateAndRedeemTicket`，以从 SSO 存储中检索登录凭据。</span><span class="sxs-lookup"><span data-stu-id="4c48d-113">When BizTalk Adapter for JD Edwards EnterpriseOne receives the message from the Message Box database, it calls `ValidateAndRedeemTicket` with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="4c48d-114">然后，适配器将使用外部凭据连接该系统并处理请求。</span><span class="sxs-lookup"><span data-stu-id="4c48d-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c48d-115">SSO 配置是 BizTalk Server 安装程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c48d-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="4c48d-116">如果收到 SSO 错误，请确认您配置 BizTalk Server 时使用的是域帐户，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="4c48d-116">If you get SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="4c48d-117">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="4c48d-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c48d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c48d-118">See Also</span></span>  
 <span data-ttu-id="4c48d-119">[创建关联应用程序](../core/creating-affiliate-applications4.md) </span><span class="sxs-lookup"><span data-stu-id="4c48d-119">[Creating Affiliate Applications](../core/creating-affiliate-applications4.md) </span></span>  
 [<span data-ttu-id="4c48d-120">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="4c48d-120">Using Single Sign-On</span></span>](../core/using-single-sign-on1.md)