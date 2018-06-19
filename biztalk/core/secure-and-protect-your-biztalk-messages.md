---
title: 保护 BizTalk 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security
ms.assetid: f2419d2a-57cf-435e-b0d0-0b0e1433d585
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e73c635ce423ad77c2986bb12ebda9bfa285e68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268853"
---
# <a name="secure-and-protect-your-biztalk-messages"></a><span data-ttu-id="9a51a-102">保护 BizTalk 消息</span><span class="sxs-lookup"><span data-stu-id="9a51a-102">Secure and protect your BizTalk messages</span></span>
<span data-ttu-id="9a51a-103">Microsoft® BizTalk® Server 提供了一个标准网关以便在 Intranet 中或通过 Internet 发送和接收文档。</span><span class="sxs-lookup"><span data-stu-id="9a51a-103">Microsoft® BizTalk® Server provides a standard gateway for sending and receiving documents both within an intranet and through the Internet.</span></span> <span data-ttu-id="9a51a-104">由于通过 BizTalk Server 发送和接收的消息有可能包含重要的业务信息，因此很有必要采取一些措施，保证这些消息及其包含的信息在传输过程中以及 BizTalk Server 对这些消息的处理和存储过程中的安全性。</span><span class="sxs-lookup"><span data-stu-id="9a51a-104">Due to the possible business-critical nature of the messages sent to and from BizTalk Server, it is important to consider measures for securing these messages and the information they contain both as they are in transit and while BizTalk Server processes and stores them.</span></span> <span data-ttu-id="9a51a-105">本部分提供有关 BizTalk Server 安全功能以及如何使用这些功能来确保数据和环境安全的信息。</span><span class="sxs-lookup"><span data-stu-id="9a51a-105">This section provides information about the BizTalk Server security features, and how you can use them to secure your data and environment.</span></span>  
  
 <span data-ttu-id="9a51a-106">有关保护 BizTalk Server 部署的详细信息，请参阅[的 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9a51a-106">For more information about securing a BizTalk Server deployment, see [Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a51a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="9a51a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="9a51a-108">BizTalk Server 中的安全功能</span><span class="sxs-lookup"><span data-stu-id="9a51a-108">Security Features in BizTalk Server</span></span>](../core/security-features-in-biztalk-server.md)  
  
-   [<span data-ttu-id="9a51a-109">规划消息安全</span><span class="sxs-lookup"><span data-stu-id="9a51a-109">Planning Message Security</span></span>](../core/planning-message-security.md)  
  
-   [<span data-ttu-id="9a51a-110">访问控制和数据安全</span><span class="sxs-lookup"><span data-stu-id="9a51a-110">Access Control and Data Security</span></span>](../core/access-control-and-data-security.md)