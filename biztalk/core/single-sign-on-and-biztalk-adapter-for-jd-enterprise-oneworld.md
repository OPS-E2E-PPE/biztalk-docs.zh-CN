---
title: "有关博士企业 OneWorld 单一登录和 BizTalk 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Single Sign-On
ms.assetid: 44fea3a4-8073-4b64-94e5-1eacbae845d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9d3d102c3ab79ea719587fdb3632612e75faa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld"></a><span data-ttu-id="d24e7-102">有关博士企业 OneWorld 单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="d24e7-102">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>
<span data-ttu-id="d24e7-103">单一登录 (SSO) 凭据是从数据库中获取 SSO 凭据;因此，不需要输入中的服务器系统的登录凭据**传输属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="d24e7-103">Single Sign-On (SSO) credentials are obtained from the SSO credentials database; therefore, you do not need to enter the server system's logon credentials in the **Transport Properties** window.</span></span>  
  
 <span data-ttu-id="d24e7-104">在设计时，用于 JD Edwards OneWorld 的 BizTalk 适配器即会在启动 BizTalk Server 项目的用户的上下文中，为指定的关联应用程序获取用于系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="d24e7-104">At design-time, Microsoft BizTalk Adapter for JD Edwards OneWorld obtains the credentials for the system (for the specified affiliate application) under the context of the user who started BizTalk Server project.</span></span> <span data-ttu-id="d24e7-105">此用户应为应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="d24e7-105">That user should be an Application User.</span></span>  
  
 <span data-ttu-id="d24e7-106">运行时，将 JD Edwards OneWorld 的 BizTalk 适配器用作使用 SSO 时的简单直通方案中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="d24e7-106">At run time, use the BizTalk Adapter for JD Edwards OneWorld as a receive location in the pass-through scenarios when using SSO.</span></span>  
  
 <span data-ttu-id="d24e7-107">当 Internet 信息服务 (IIS) 从 Web 客户端接收到 HTTP 请求时，IIS 将验证该用户。</span><span class="sxs-lookup"><span data-stu-id="d24e7-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="d24e7-108">使用 ISAPI 扩展插件模拟 Windows 用户，并调用要获得加密的票证的 SSO 凭据存储区。</span><span class="sxs-lookup"><span data-stu-id="d24e7-108">The ISAPI extension impersonates the Windows user and calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="d24e7-109">此票证在消息上下文中以 SSOTicket 属性形式存储。</span><span class="sxs-lookup"><span data-stu-id="d24e7-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="d24e7-110">消息即定向到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="d24e7-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="d24e7-111">适配器从 MessageBox 数据库接收消息时，它使用加密票证和关联应用程序名来调用 IBTSTicket.ValidateAndRedeemTicket 方法，以从 SSO 存储中检索登录凭据。</span><span class="sxs-lookup"><span data-stu-id="d24e7-111">When the adapter receives the message from the Message Box database, it calls the IBTSTicket.ValidateAndRedeemTicket method with the encrypted ticket along with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="d24e7-112">然后，用于 JD Edwards OneWorld 的 BizTalk 适配器使用外部凭据连接到系统并处理请求。</span><span class="sxs-lookup"><span data-stu-id="d24e7-112">BizTalk Adapter for JD Edwards OneWorld then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d24e7-113">SSO 配置是 BizTalk Server 安装程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="d24e7-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="d24e7-114">如果你收到 SSO 错误，请验证使用域帐户时配置 BizTalk Server 中，因为这会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="d24e7-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, because this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="d24e7-115">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="d24e7-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d24e7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d24e7-116">See Also</span></span>  
 <span data-ttu-id="d24e7-117">[创建关联应用程序](../core/creating-affiliate-applications3.md) </span><span class="sxs-lookup"><span data-stu-id="d24e7-117">[Creating Affiliate Applications](../core/creating-affiliate-applications3.md) </span></span>  
 [<span data-ttu-id="d24e7-118">使用单一登录</span><span class="sxs-lookup"><span data-stu-id="d24e7-118">Using Single Sign-On</span></span>](../core/using-single-sign-on3.md)