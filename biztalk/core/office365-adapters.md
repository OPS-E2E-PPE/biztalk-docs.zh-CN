---
title: 使用 Office 365 Outlook 电子邮件适配器 |Microsoft Docs
description: 发送和接收消息在 BizTalk Server，包括电子邮件、 日历和联系人中使用 Office 365 Outlook 适配器概述
ms.custom: ''
ms.date: 06/19/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: MandiOhlinger
ms.author: ribarua
manager: dougeby
ms.openlocfilehash: 2002ab6859a71a930ef9166f9b3a5a072ba77948
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36946160"
---
# <a name="office-365-outlook-adapters-in-biztalk"></a><span data-ttu-id="fb938-103">在 BizTalk 中的 office 365 Outlook 适配器</span><span class="sxs-lookup"><span data-stu-id="fb938-103">Office 365 Outlook adapters in BizTalk</span></span>

## <a name="overview"></a><span data-ttu-id="fb938-104">概述</span><span class="sxs-lookup"><span data-stu-id="fb938-104">Overview</span></span>
<span data-ttu-id="fb938-105">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]功能包 3**，可以发送和接收 BizTalk Server 和 Office 365 Outlook 功能之间的消息。</span><span class="sxs-lookup"><span data-stu-id="fb938-105">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 3**, you can send and receive messages between BizTalk Server and Office 365 Outlook features.</span></span> <span data-ttu-id="fb938-106">功能包 3 中包括以下适配器：</span><span class="sxs-lookup"><span data-stu-id="fb938-106">The following adapters are included in Feature Pack 3:</span></span>

- [<span data-ttu-id="fb938-107">Office 365 Outlook 电子邮件适配器</span><span class="sxs-lookup"><span data-stu-id="fb938-107">Office 365 Outlook Email adapter</span></span>](office365-mail-adapter.md)
- [<span data-ttu-id="fb938-108">Office 365 Outlook 日历适配器</span><span class="sxs-lookup"><span data-stu-id="fb938-108">Office 365 Outlook Calendar adapter</span></span>](office365-calendar-adapter.md)
- [<span data-ttu-id="fb938-109">Office 365 Outlook 联系人适配器</span><span class="sxs-lookup"><span data-stu-id="fb938-109">Office 365 Outlook Contact adapter</span></span>](office365-contact-adapter.md)

## <a name="prerequisites"></a><span data-ttu-id="fb938-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="fb938-110">Prerequisites</span></span>

* <span data-ttu-id="fb938-111">具有[Office 365 帐户](https://outlook.office365.com)</span><span class="sxs-lookup"><span data-stu-id="fb938-111">Have an [Office 365 account](https://outlook.office365.com)</span></span>
* <span data-ttu-id="fb938-112">安装[功能包 3](https://aka.ms/bts2016fp3) BizTalk 服务器上</span><span class="sxs-lookup"><span data-stu-id="fb938-112">Install [Feature Pack 3](https://aka.ms/bts2016fp3) on your BizTalk Server</span></span>
* <span data-ttu-id="fb938-113">使用该帐户是 SSO Administrators 组的成员</span><span class="sxs-lookup"><span data-stu-id="fb938-113">Use an account that is a member of the SSO Administrators group</span></span>

## <a name="tms-overview"></a><span data-ttu-id="fb938-114">TMS 概述</span><span class="sxs-lookup"><span data-stu-id="fb938-114">TMS overview</span></span>

<span data-ttu-id="fb938-115">BizTalk Server TMS 是刷新 BizTalk 使用 Office 365 OAuth 令牌的服务。</span><span class="sxs-lookup"><span data-stu-id="fb938-115">BizTalk Server TMS is a service that refreshes the Office 365 OAuth tokens used by BizTalk.</span></span> <span data-ttu-id="fb938-116">它将刷新这些令牌定期，确保令牌始终保持有效。</span><span class="sxs-lookup"><span data-stu-id="fb938-116">It refreshes these tokens periodically, ensuring that the tokens always remain valid.</span></span> <span data-ttu-id="fb938-117">它在企业单一登录服务 (ENT SSO) 上具有依赖关系，并必须承载在主密钥服务器的计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="fb938-117">It has a dependency on Enterprise Single Sign On service (ENT SSO), and must be installed on a computer that hosts the master secret server.</span></span> 

## <a name="install-biztalk-server-tms"></a><span data-ttu-id="fb938-118">安装 BizTalk Server TMS</span><span class="sxs-lookup"><span data-stu-id="fb938-118">Install BizTalk Server TMS</span></span>

1. <span data-ttu-id="fb938-119">安装[功能包 3](https://aka.ms/bts2016fp3)。</span><span class="sxs-lookup"><span data-stu-id="fb938-119">Install [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>
2. <span data-ttu-id="fb938-120">在`\Program Files (x86)\Microsoft BizTalk Server <your version>`，运行 BizTalkTMS.msi。</span><span class="sxs-lookup"><span data-stu-id="fb938-120">In `\Program Files (x86)\Microsoft BizTalk Server <your version>`, run BizTalkTMS.msi.</span></span>
3. <span data-ttu-id="fb938-121">输入用户名和密码是 SSO Administrators 组的成员的用户。</span><span class="sxs-lookup"><span data-stu-id="fb938-121">Enter the username and password of a user that's a member of the SSO Administrators group.</span></span> 

![BizTalk Server TMS 安装程序](../core/media/BizTalk-TMS.png)

## <a name="sign-in-to-office-365"></a><span data-ttu-id="fb938-123">登录到 Office 365</span><span class="sxs-lookup"><span data-stu-id="fb938-123">Sign-in to Office 365</span></span>

<span data-ttu-id="fb938-124">如果您要创建[发送端口](how-to-create-a-send-port2.md)或[接收位置](how-to-create-a-receive-location.md)在 BizTalk 管理，你可以**登录...** 到 Office 365 帐户：</span><span class="sxs-lookup"><span data-stu-id="fb938-124">When you're creating a [send port](how-to-create-a-send-port2.md) or [receive location](how-to-create-a-receive-location.md) in BizTalk Administration, you can **Sign-in...** to your Office 365 account:</span></span>

  ![Office 365 登录](../core/media/office365-signin.png)

<span data-ttu-id="fb938-126">输入 Office 365 凭据，并确认权限。</span><span class="sxs-lookup"><span data-stu-id="fb938-126">You enter the Office 365 credentials, and confirm permissions.</span></span> <span data-ttu-id="fb938-127">这些凭据授权 BizTalk 要连接到并访问 Office 365 帐户。</span><span class="sxs-lookup"><span data-stu-id="fb938-127">These credentials authorize BizTalk to connect to, and access the Office 365 account.</span></span> <span data-ttu-id="fb938-128">在以下示例中，可以看到 Office 365 Outlook 日历的权限：</span><span class="sxs-lookup"><span data-stu-id="fb938-128">In the following example, you see the permissions for Office 365 Outlook Calendar:</span></span>

  ![Office 365 日历权限](../core/media/office365-calendar-permissions.png)

## <a name="get-started"></a><span data-ttu-id="fb938-130">入门</span><span class="sxs-lookup"><span data-stu-id="fb938-130">Get started</span></span>
<span data-ttu-id="fb938-131">安装 BizTalk Server TMS 后，你准备好创建这些项目中，并开始使用适配器：</span><span class="sxs-lookup"><span data-stu-id="fb938-131">After BizTalk Server TMS is installed, you're ready to create the artifacts, and start using the adapters:</span></span>

- [<span data-ttu-id="fb938-132">Office 365 Outlook 电子邮件适配器</span><span class="sxs-lookup"><span data-stu-id="fb938-132">Office 365 Outlook Email adapter</span></span>](./office365-mail-adapter.md)
- [<span data-ttu-id="fb938-133">Office 365 Outlook 日历适配器</span><span class="sxs-lookup"><span data-stu-id="fb938-133">Office 365 Outlook Calendar adapter</span></span>](./office365-calendar-adapter.md)
- [<span data-ttu-id="fb938-134">Office 365 Outlook 联系人适配器</span><span class="sxs-lookup"><span data-stu-id="fb938-134">Office 365 Outlook Contact adapter</span></span>](./office365-contact-adapter.md)
