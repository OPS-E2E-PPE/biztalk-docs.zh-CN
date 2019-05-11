---
title: 用于 PeopleSoft Enterprise 的单一登录和 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing HTTP requests
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: d8ad75f1-a83f-4722-a43f-50dc95df2f9d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6819b89f7c09fdf347f362f89038e732f6f24396
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393016"
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="cc683-102">用于 PeopleSoft Enterprise 的单一登录和 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="cc683-102">Single Sign-On and BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="cc683-103">当用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用单一登录 (SSO) 时，适配器将从 SSO 凭据数据库中; 获取凭据因此，您无需输入服务器系统的登录凭据**传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="cc683-103">When you use Single Sign-On (SSO) with Microsoft BizTalk Adapter for PeopleSoft Enterprise, the adapter obtains the credentials from the SSO Credentials database; therefore, you do not have to enter the logon credentials for the server system in the **Transport Properties** dialog box.</span></span>  
  
 <span data-ttu-id="cc683-104">在设计时用于 PeopleSoft Enterprise 的 BizTalk 适配器获取用于启动 BizTalk Server 项目的用户的上下文 （适用于指定的关联应用程序） 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="cc683-104">At design-time, BizTalk Adapter for PeopleSoft Enterprise obtains the credentials for the system (for the specified affiliate application) under the context of the user who started the BizTalk Server project.</span></span> <span data-ttu-id="cc683-105">该用户应为应用程序用户。</span><span class="sxs-lookup"><span data-stu-id="cc683-105">That user should be an Application User.</span></span>  
  
## <a name="processing-requests"></a><span data-ttu-id="cc683-106">处理请求</span><span class="sxs-lookup"><span data-stu-id="cc683-106">Processing Requests</span></span>  
 <span data-ttu-id="cc683-107">当 Internet 信息服务 (IIS) 从 Web 客户端收到 HTTP 请求时，IIS 会进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="cc683-107">When Internet Information Services (IIS) receives an HTTP request from a Web client, IIS authenticates the user.</span></span> <span data-ttu-id="cc683-108">ISAPI 扩展模拟 Windows 用户，然后调用 SSO 凭据存储区获取加密的票证。</span><span class="sxs-lookup"><span data-stu-id="cc683-108">The ISAPI extension impersonates the Windows user and then calls the SSO credential store to obtain an encrypted ticket.</span></span> <span data-ttu-id="cc683-109">此票证在消息的上下文中以 SSOTicket 属性形式存储。</span><span class="sxs-lookup"><span data-stu-id="cc683-109">This ticket is stored as the SSOTicket property in the context of the message.</span></span>  
  
 <span data-ttu-id="cc683-110">消息然后定向到 Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="cc683-110">The message is then directed to the Message Box database.</span></span> <span data-ttu-id="cc683-111">当 PeopleSoft 企业的 BizTalk 适配器从 Messagebox 数据库接收消息时，它调用 validateandredeemticket，以使用加密票证和关联应用程序名来从 SSO 存储中检索登录凭据。</span><span class="sxs-lookup"><span data-stu-id="cc683-111">When BizTalk Adapter for PeopleSoft Enterprises receives the message from the Message Box database, it calls ValidateAndRedeemTicket with the encrypted ticket together with the affiliate application name to retrieve the logon credentials from the SSO store.</span></span> <span data-ttu-id="cc683-112">然后，适配器使用的外部凭据连接到系统并处理该请求。</span><span class="sxs-lookup"><span data-stu-id="cc683-112">The adapter then uses the external credentials to connect to the system and process the request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc683-113">SSO 配置是 BizTalk Server 安装程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc683-113">SSO configuration is part of the BizTalk Server setup.</span></span> <span data-ttu-id="cc683-114">如果收到 SSO 错误，请确认使用的域帐户配置 BizTalk Server 中，因为它会影响企业 SSO 服务的功能。</span><span class="sxs-lookup"><span data-stu-id="cc683-114">If you receive SSO errors, verify that you used a domain account when you configured BizTalk Server, as this affects the function of the Enterprise SSO service.</span></span> <span data-ttu-id="cc683-115">SSO 仅在域帐户下起作用。</span><span class="sxs-lookup"><span data-stu-id="cc683-115">SSO only functions under a domain account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc683-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc683-116">See Also</span></span>  
 <span data-ttu-id="cc683-117">[创建关联应用程序](../core/creating-affiliate-applications2.md) </span><span class="sxs-lookup"><span data-stu-id="cc683-117">[Creating Affiliate Applications](../core/creating-affiliate-applications2.md) </span></span>  
 [<span data-ttu-id="cc683-118">保护适配器</span><span class="sxs-lookup"><span data-stu-id="cc683-118">Secure the adapter</span></span>](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)