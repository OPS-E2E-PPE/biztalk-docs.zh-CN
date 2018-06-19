---
title: 在消息 SSO 和 TIBCO 企业的 BizTalk 适配器服务 |Microsoft 文档
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
ms.openlocfilehash: 577fa596fadee68c94dfa510de101d01b0ab06e4
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013412"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service"></a><span data-ttu-id="604f8-102">TIBCO Enterprise Message Service 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="604f8-102">Single Sign-On and BizTalk Adapter for TIBCO Enterprise Message Service</span></span>

## <a name="overview"></a><span data-ttu-id="604f8-103">概述</span><span class="sxs-lookup"><span data-stu-id="604f8-103">Overview</span></span>
<span data-ttu-id="604f8-104">适配器在单一登录 (SSO) 和 Microsoft BizTalk 适配器 TIBCO 企业消息服务 (EMS) 一起使用时从 SSO 凭据数据库; 获取凭据因此，你无需输入服务器系统中的登录凭据**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="604f8-104">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS), the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="604f8-105">在设计时，适配器将会在启动 BizTalk Server 项目的用户的上下文中，为指定的关联应用程序获取用于系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="604f8-105">At design time, the adapter obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="604f8-106">此用户应为应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="604f8-106">That user should be an Application User.</span></span> <span data-ttu-id="604f8-107">运行时，将 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 接收适配器用作使用 SSO 时的简单直通方案中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="604f8-107">At run time, use the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Receive Adapter as a receive location in the pass-through scenarios when you use SSO.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="604f8-108">处理请求</span><span class="sxs-lookup"><span data-stu-id="604f8-108">Processing Requests</span></span>  
 <span data-ttu-id="604f8-109">当 Internet 信息服务 (IIS) 从 Web 客户端接收到 HTTP 请求时，IIS 将验证该用户。</span><span class="sxs-lookup"><span data-stu-id="604f8-109">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="604f8-110">使用 ISAPI 扩展插件模拟 Windows 用户，并调用要获得加密的票证的 SSO 凭据存储区。</span><span class="sxs-lookup"><span data-stu-id="604f8-110">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="604f8-111">此票证在消息上下文中以 SSOTicket 属性形式存储。</span><span class="sxs-lookup"><span data-stu-id="604f8-111">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="604f8-112">消息即定向到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="604f8-112">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="604f8-113">当用于 TIBCO EMS 的 BizTalk 适配器从 MessageBox 数据库接收消息时，它使用加密票证和关联应用程序名来调用 ValidateAndRedeemTicket，以从 SSO 存储中检索登录凭据。</span><span class="sxs-lookup"><span data-stu-id="604f8-113">When BizTalk Adapter for TIBCO EMS receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="604f8-114">然后，适配器将使用外部凭据连接该系统并处理请求。</span><span class="sxs-lookup"><span data-stu-id="604f8-114">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="604f8-115">SSO 配置是 BizTalk Server 安装程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="604f8-115">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="604f8-116">如果你收到 SSO 错误，请验证使用域帐户时配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="604f8-116">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="604f8-117">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="604f8-117">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604f8-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="604f8-118">See Also</span></span>  
 <span data-ttu-id="604f8-119">[创建关联应用程序](../core/creating-affiliate-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="604f8-119">[Creating Affiliate Applications](../core/creating-affiliate-applications5.md) </span></span>  
 [<span data-ttu-id="604f8-120">安全适配器</span><span class="sxs-lookup"><span data-stu-id="604f8-120">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-tibco-ems.md)