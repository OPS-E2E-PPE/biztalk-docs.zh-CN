---
title: POP3 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, about POP3 adapters
- authenticating, POP3 adapters
- POP3 adapters
- POP3 adapters, receive adapters
- POP3 adapters, authenticating
- receive adapters, POP3 adapters
ms.assetid: 008f7fa7-60c3-4ea3-b90d-821e4029a04c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34a5f6a73f30ba831256ce1699b9a6a77b75c102
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982790"
---
# <a name="pop3-adapter"></a><span data-ttu-id="23a84-102">POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="23a84-102">POP3 Adapter</span></span>
<span data-ttu-id="23a84-103">使用邮局协议 3 (POP3) 适配器从 POP3 邮箱所在到通过 POP3 协议运行 Microsoft BizTalk Server 的服务器的服务器检索数据。</span><span class="sxs-lookup"><span data-stu-id="23a84-103">You use the Post Office Protocol 3 (POP3) adapter to retrieve data from a server that houses POP3 mailboxes into a server running Microsoft BizTalk Server by means of the POP3 protocol.</span></span>  
  
 <span data-ttu-id="23a84-104">POP3 适配器由只有一个适配器，接收适配器组成。</span><span class="sxs-lookup"><span data-stu-id="23a84-104">The POP3 adapter consists of only one adapter, a receive adapter.</span></span> <span data-ttu-id="23a84-105">接收适配器控制使用 POP3 适配器的接收位置。</span><span class="sxs-lookup"><span data-stu-id="23a84-105">The receive adapter controls the receive locations that use the POP3 adapter.</span></span>  
  
 <span data-ttu-id="23a84-106">本主题讨论的工作流的 POP3 接收适配器。</span><span class="sxs-lookup"><span data-stu-id="23a84-106">This topic discusses the workflow of the POP3 receive adapter.</span></span>  
  
 <span data-ttu-id="23a84-107">**POP3 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="23a84-107">**POP3 Receive Adapter**</span></span>  
  
 <span data-ttu-id="23a84-108">从指定的 POP3 服务器上指定的邮箱，POP3 接收适配器检索电子邮件。</span><span class="sxs-lookup"><span data-stu-id="23a84-108">The POP3 receive adapter retrieves e-mail from a specified mailbox on a specified POP3 server.</span></span> <span data-ttu-id="23a84-109">默认情况下，POP3 接收适配器适用 MIME 处理到其下载和这些将消息提交给 BizTalk Server 作为多部分 BizTalk 消息的电子邮件消息。</span><span class="sxs-lookup"><span data-stu-id="23a84-109">By default, the POP3 receive adapter applies MIME processing to the e-mail messages that it downloads and submits these messages to BizTalk Server as multipart BizTalk messages.</span></span> <span data-ttu-id="23a84-110">POP3 接收适配器可以接收和处理采用以下格式的电子邮件：</span><span class="sxs-lookup"><span data-stu-id="23a84-110">The POP3 receive adapter can receive and process e-mail in the following formats:</span></span>  
  
- <span data-ttu-id="23a84-111">纯文本</span><span class="sxs-lookup"><span data-stu-id="23a84-111">Plain text</span></span>  
  
- <span data-ttu-id="23a84-112">MIME 编码</span><span class="sxs-lookup"><span data-stu-id="23a84-112">MIME encoded</span></span>  
  
- <span data-ttu-id="23a84-113">MIME 加密</span><span class="sxs-lookup"><span data-stu-id="23a84-113">MIME encrypted</span></span>  
  
- <span data-ttu-id="23a84-114">MIME 编码和签名</span><span class="sxs-lookup"><span data-stu-id="23a84-114">MIME encoded and signed</span></span>  
  
- <span data-ttu-id="23a84-115">MIME 加密和签名</span><span class="sxs-lookup"><span data-stu-id="23a84-115">MIME encrypted and signed</span></span>  
  
  <span data-ttu-id="23a84-116">**POP3 接收适配器的批处理支持**</span><span class="sxs-lookup"><span data-stu-id="23a84-116">**Batching Support for the POP3 Receive Adapter**</span></span>  
  
  <span data-ttu-id="23a84-117">POP3 接收适配器不支持批处理。</span><span class="sxs-lookup"><span data-stu-id="23a84-117">The POP3 receive adapter does not support batching.</span></span>  
  
  <span data-ttu-id="23a84-118">**POP3 服务器的身份验证**</span><span class="sxs-lookup"><span data-stu-id="23a84-118">**Authentication with POP3 Server**</span></span>  
  
  <span data-ttu-id="23a84-119">用于 POP3 适配器支持以下身份验证方法：</span><span class="sxs-lookup"><span data-stu-id="23a84-119">The following authentication methods are supported for use with the POP3 adapter:</span></span>  
  
- <span data-ttu-id="23a84-120">**基本。**</span><span class="sxs-lookup"><span data-stu-id="23a84-120">**Basic.**</span></span> <span data-ttu-id="23a84-121">POP3 服务器使用用户提供的凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="23a84-121">The POP3 server uses user provided credentials for authentication.</span></span>  <span data-ttu-id="23a84-122">这些凭据以明文形式发送。</span><span class="sxs-lookup"><span data-stu-id="23a84-122">These credentials are sent in clear text.</span></span>  
  
- <span data-ttu-id="23a84-123">**摘要 (APOP)。**</span><span class="sxs-lookup"><span data-stu-id="23a84-123">**Digest (APOP).**</span></span> <span data-ttu-id="23a84-124">POP3 服务器进行身份验证使用摘要字符串。</span><span class="sxs-lookup"><span data-stu-id="23a84-124">The POP3 server uses a digest string for authentication.</span></span>  
  
- <span data-ttu-id="23a84-125">**安全密码身份验证 (SPA)。**</span><span class="sxs-lookup"><span data-stu-id="23a84-125">**Secure Password Authentication (SPA).**</span></span> <span data-ttu-id="23a84-126">POP3 服务器使用当前进程凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="23a84-126">The POP3 server uses current process credentials for authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23a84-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="23a84-127">In This Section</span></span>  
  
-   [<span data-ttu-id="23a84-128">POP3 适配器概述</span><span class="sxs-lookup"><span data-stu-id="23a84-128">What Is the POP3 Adapter?</span></span>](../core/what-is-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="23a84-129">配置 POP3 适配器</span><span class="sxs-lookup"><span data-stu-id="23a84-129">Configuring the POP3 Adapter</span></span>](../core/configuring-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="23a84-130">演练：创建使用 POP3 适配器的 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="23a84-130">Walkthrough: Creating a BizTalk Application That Uses the POP3 Adapter</span></span>](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [<span data-ttu-id="23a84-131">使用 POP3 适配器处理多部分消息</span><span class="sxs-lookup"><span data-stu-id="23a84-131">Processing Multi Part Messages with the POP3 Adapter</span></span>](../core/processing-multi-part-messages-with-the-pop3-adapter.md)