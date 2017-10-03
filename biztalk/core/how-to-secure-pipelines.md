---
title: "如何保护管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3a717f-acf8-4f08-a6fb-6d1d48b5b80a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 903e9faec81ce58aac243fb7a22bac6678a81a42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-secure-pipelines"></a><span data-ttu-id="2faa7-102">如何确保管道安全</span><span class="sxs-lookup"><span data-stu-id="2faa7-102">How to Secure Pipelines</span></span>

## <a name="authentication-trusted"></a><span data-ttu-id="2faa7-103">受信任的身份验证</span><span class="sxs-lookup"><span data-stu-id="2faa7-103">Authentication trusted</span></span>
<span data-ttu-id="2faa7-104">主机可以在管理控制台中为标记**受信任的身份验证**。</span><span class="sxs-lookup"><span data-stu-id="2faa7-104">Hosts can be marked in the administration console as **Authentication Trusted**.</span></span> <span data-ttu-id="2faa7-105">将主机表示为“受信任验证”意味着 Microsoft BizTalk Server 将信任该主机所发送消息的上下文中的安全相关属性。</span><span class="sxs-lookup"><span data-stu-id="2faa7-105">Denoting a host as Authentication Trusted means that the Microsoft BizTalk Server will trust the security-related properties sent on the message context of a message from that host.</span></span> <span data-ttu-id="2faa7-106">在消息上下文的安全相关的属性是**OriginatorPID**，对应于消息上下文属性 BTS。SourcePartyID，和**OriginatorSID**，对应于消息上下文属性**BTS。WindowsUser**。</span><span class="sxs-lookup"><span data-stu-id="2faa7-106">The security-related properties on the message context are the **OriginatorPID**, which corresponds to the message context property BTS.SourcePartyID, and the **OriginatorSID**, which corresponds to the message context property **BTS.WindowsUser**.</span></span> <span data-ttu-id="2faa7-107">有关详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="2faa7-107">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="2faa7-108">标记为主机**身份验证受信任**允许以指示，受信任的主机是一条消息队列将从添加到自身以外的其他人为消息的发送程序。</span><span class="sxs-lookup"><span data-stu-id="2faa7-108">A host that is marked as **Authentication Trusted** is allowed to indicate that the trusted host is adding a message to the queue from someone other than itself as the sender of the message.</span></span> <span data-ttu-id="2faa7-109">换而言之，未标记为的主机**受信任的身份验证**不允许从其他消息发送方将消息添加到队列。</span><span class="sxs-lookup"><span data-stu-id="2faa7-109">In other words, hosts that are not marked as **Authentication Trusted** are not allowed to add a message to the queue from a message sender other than themselves.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2faa7-110">MIME/SMIME 解码器管道组件不会检查解密证书的到期日期。</span><span class="sxs-lookup"><span data-stu-id="2faa7-110">The MIME/SMIME Decoder pipeline component does not check the expiration date of decryption certificates.</span></span> <span data-ttu-id="2faa7-111">但是，它会检查签名证书的到期日期。</span><span class="sxs-lookup"><span data-stu-id="2faa7-111">However, it does check the expiration date of signing certificates.</span></span>  
  
 <span data-ttu-id="2faa7-112">有关编码和解码通过 SMTP 或 HTTP 发送的消息的信息，请参阅[MIME SMIME 编码器管道组件](../core/mime-smime-encoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="2faa7-112">For information about encoding and decoding messages sent over SMTP or HTTP, see [MIME-SMIME Encoder Pipeline Component](../core/mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="2faa7-113">另请参阅[MIME SMIME 解码器管道组件](../core/mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="2faa7-113">Also see [MIME-SMIME Decoder Pipeline Component](../core/mime-smime-decoder-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="2faa7-114">有关第三方在处理时的签名验证的信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="2faa7-114">For information about signature verification when dealing with third parties, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span> <span data-ttu-id="2faa7-115">另请参阅[如何创建协议](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)。</span><span class="sxs-lookup"><span data-stu-id="2faa7-115">Also see [How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2faa7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2faa7-116">See Also</span></span>  
 <span data-ttu-id="2faa7-117">[创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="2faa7-117">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="2faa7-118">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="2faa7-118">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)