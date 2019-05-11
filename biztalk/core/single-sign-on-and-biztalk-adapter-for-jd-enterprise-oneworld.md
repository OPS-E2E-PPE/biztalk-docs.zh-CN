---
title: 用于 JD Enterprise OneWorld 的单一登录和 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec5be842305bbad1fb6e6963b4fcdd770a989224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393036"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a><span data-ttu-id="41e02-102">用于 JD Enterprise OneWorld 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="41e02-102">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>
<span data-ttu-id="41e02-103">单一登录 (SSO) 凭据获取从 SSO 凭据数据库;因此，不需要输入中的服务器系统的登录凭据**传输属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="41e02-103">Single Sign-On (SSO) credentials are obtained from the SSO credentials database; therefore, you do not need to enter the server system's logon credentials in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="41e02-104">在设计时用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器获取用于启动 BizTalk Server 项目的用户的上下文 （适用于指定的关联应用程序） 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="41e02-104">At design-time, Microsoft BizTalk Adapter for JD Edwards OneWorld obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="41e02-105">该用户应为应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="41e02-105">That user should be an Application User.</span></span>  
  
 <span data-ttu-id="41e02-106">在运行时使用的 BizTalk 适配器用于 JD Edwards OneWorld 的简单直通方案中的接收位置以使用 SSO 时。</span><span class="sxs-lookup"><span data-stu-id="41e02-106">At run time, use the BizTalk Adapter for JD Edwards OneWorld as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
 <span data-ttu-id="41e02-107">当 Internet 信息服务 (IIS) 从 Web 客户端收到 HTTP 请求时，IIS 会进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="41e02-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="41e02-108">ISAPI 扩展模拟 Windows 用户，并调用要获取加密的票证的 SSO 凭据存储区。</span><span class="sxs-lookup"><span data-stu-id="41e02-108">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="41e02-109">此票证在消息的上下文中以 SSOTicket 属性形式存储。</span><span class="sxs-lookup"><span data-stu-id="41e02-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="41e02-110">消息然后定向到 Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="41e02-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="41e02-111">当适配器从 Messagebox 数据库接收消息时，它调用 IBTSTicket.ValidateAndRedeemTicket 方法使用加密票证和关联应用程序名来从 SSO 存储中检索登录凭据。</span><span class="sxs-lookup"><span data-stu-id="41e02-111">When the adapter receives the message from the Message Box database, it calls the IBTSTicket.ValidateAndRedeemTicket method with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="41e02-112">用于 JD Edwards OneWorld 的 BizTalk 适配器使用的外部凭据连接到系统并处理该请求。</span><span class="sxs-lookup"><span data-stu-id="41e02-112">BizTalk Adapter for JD Edwards OneWorld then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41e02-113">SSO 配置是 BizTalk Server 安装程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="41e02-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="41e02-114">如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="41e02-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="41e02-115">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="41e02-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e02-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="41e02-116">See Also</span></span>  
 <span data-ttu-id="41e02-117">[创建关联应用程序](../core/creating-affiliate-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="41e02-117">[Creating Affiliate Applications](../core/creating-affiliate-applications3.md) </span></span>  
 [<span data-ttu-id="41e02-118">适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="41e02-118">Security in the adapter</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)