---
title: SSO 和 BizTalk 适配器用于 TIBCO Enterprise 消息服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68e85ceb-bf4c-489a-a2c2-1558e718ceed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9d0da66a8088c41e61e9c31d1ee722a76b7170
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392918"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="3185d-102">用于 TIBCO Enterprise Message Service 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="3185d-102">Single Sign-On and BizTalk Adapter for TIBCO Enterprise Message Service</span></span>

## <a name="overview"></a><span data-ttu-id="3185d-103">概述</span><span class="sxs-lookup"><span data-stu-id="3185d-103">Overview</span></span>
<span data-ttu-id="3185d-104">当您使用单一登录 (SSO) 的 Microsoft BizTalk 适配器用于 TIBCO Enterprise Message Service (EMS) 时，适配器将从 SSO 凭据数据库中; 获取凭据因此，您无需输入服务器系统的登录凭据**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="3185d-104">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS), the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="3185d-105">在设计时，适配器将获取上下文的用户的启动 BizTalk Server 项目 （适用于指定的关联应用程序） 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="3185d-105">At design time, the adapter obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="3185d-106">该用户应为应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="3185d-106">That user should be an Application User.</span></span> <span data-ttu-id="3185d-107">在运行时，使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收适配器用作使用 SSO 时的简单直通方案中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="3185d-107">At run time, use the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when you use SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="3185d-108">处理请求</span><span class="sxs-lookup"><span data-stu-id="3185d-108">Processing Requests</span></span>  
 <span data-ttu-id="3185d-109">当 Internet 信息服务 (IIS) 从 Web 客户端收到 HTTP 请求时，IIS 会进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="3185d-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="3185d-110">ISAPI 扩展模拟 Windows 用户，并调用要获取加密的票证的 SSO 凭据存储区。</span><span class="sxs-lookup"><span data-stu-id="3185d-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="3185d-111">此票证在消息的上下文中以 SSOTicket 属性形式存储。</span><span class="sxs-lookup"><span data-stu-id="3185d-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="3185d-112">消息然后定向到 Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="3185d-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="3185d-113">当用于 TIBCO EMS 的 BizTalk 适配器从 Messagebox 数据库接收消息时，它调用 validateandredeemticket，以使用加密票证和关联应用程序名来从 SSO 存储中检索登录凭据。</span><span class="sxs-lookup"><span data-stu-id="3185d-113">When BizTalk Adapter for TIBCO EMS receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="3185d-114">然后，适配器使用的外部凭据连接到系统并处理该请求。</span><span class="sxs-lookup"><span data-stu-id="3185d-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3185d-115">SSO 配置是 BizTalk Server 安装程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="3185d-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="3185d-116">如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="3185d-116">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="3185d-117">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="3185d-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3185d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3185d-118">See Also</span></span>  
 <span data-ttu-id="3185d-119">[创建关联应用程序](../core/creating-affiliate-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="3185d-119">[Creating Affiliate Applications](../core/creating-affiliate-applications5.md) </span></span>  
 [<span data-ttu-id="3185d-120">保护适配器</span><span class="sxs-lookup"><span data-stu-id="3185d-120">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)