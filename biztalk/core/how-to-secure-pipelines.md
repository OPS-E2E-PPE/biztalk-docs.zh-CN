---
title: 如何确保管道安全 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3a717f-acf8-4f08-a6fb-6d1d48b5b80a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e27ba4d24dd8109366af95b0a477fc8fb049ce5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334828"
---
# <a name="how-to-secure-pipelines"></a><span data-ttu-id="f16ce-102">如何确保管道安全</span><span class="sxs-lookup"><span data-stu-id="f16ce-102">How to Secure Pipelines</span></span>

## <a name="authentication-trusted"></a><span data-ttu-id="f16ce-103">受信任的身份验证</span><span class="sxs-lookup"><span data-stu-id="f16ce-103">Authentication trusted</span></span>
<span data-ttu-id="f16ce-104">主机可以在管理控制台中为标记**受信任验证**。</span><span class="sxs-lookup"><span data-stu-id="f16ce-104">Hosts can be marked in the administration console as **Authentication Trusted**.</span></span> <span data-ttu-id="f16ce-105">表示为受信任验证主机意味着 Microsoft BizTalk Server 将信任发送一条消息的消息上下文上的与安全相关的属性。</span><span class="sxs-lookup"><span data-stu-id="f16ce-105">Denoting a host as Authentication Trusted means that the Microsoft BizTalk Server will trust the security-related properties sent on the message context of a message from that host.</span></span> <span data-ttu-id="f16ce-106">在消息上下文的安全相关的属性是**OriginatorPID**，对应于 BTS 消息上下文属性。SourcePartyID，并**OriginatorSID**，这对应于消息上下文属性**BTS。WindowsUser**。</span><span class="sxs-lookup"><span data-stu-id="f16ce-106">The security-related properties on the message context are the **OriginatorPID**, which corresponds to the message context property BTS.SourcePartyID, and the **OriginatorSID**, which corresponds to the message context property **BTS.WindowsUser**.</span></span> <span data-ttu-id="f16ce-107">有关详细信息，请参阅**消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="f16ce-107">For more information, see **Message Context Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
 <span data-ttu-id="f16ce-108">标记为主机**身份验证受信任**允许以指示，受信任的主机一条消息向队列添加从本身以外的其他人为消息的发件人。</span><span class="sxs-lookup"><span data-stu-id="f16ce-108">A host that is marked as **Authentication Trusted** is allowed to indicate that the trusted host is adding a message to the queue from someone other than itself as the sender of the message.</span></span> <span data-ttu-id="f16ce-109">换而言之，未标记为的主机才**受信任验证**不允许来自非其本身的消息发件人添加到队列的消息。</span><span class="sxs-lookup"><span data-stu-id="f16ce-109">In other words, hosts that are not marked as **Authentication Trusted** are not allowed to add a message to the queue from a message sender other than themselves.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f16ce-110">MIME/SMIME 解码器管道组件不会检查解密证书的到期日期。</span><span class="sxs-lookup"><span data-stu-id="f16ce-110">The MIME/SMIME Decoder pipeline component does not check the expiration date of decryption certificates.</span></span> <span data-ttu-id="f16ce-111">但是，它会检查签名证书的到期日期。</span><span class="sxs-lookup"><span data-stu-id="f16ce-111">However, it does check the expiration date of signing certificates.</span></span>  
  
 <span data-ttu-id="f16ce-112">有关编码和解码通过 SMTP 或 HTTP 发送的消息的信息，请参阅[MIME-SMIME 编码器管道组件](../core/mime-smime-encoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="f16ce-112">For information about encoding and decoding messages sent over SMTP or HTTP, see [MIME-SMIME Encoder Pipeline Component](../core/mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="f16ce-113">另请参阅[MIME-SMIME 解码器管道组件](../core/mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="f16ce-113">Also see [MIME-SMIME Decoder Pipeline Component](../core/mime-smime-decoder-pipeline-component.md).</span></span>  
  
 <span data-ttu-id="f16ce-114">处理第三方时签名验证的信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="f16ce-114">For information about signature verification when dealing with third parties, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span> <span data-ttu-id="f16ce-115">另请参阅[如何创建协议](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c)。</span><span class="sxs-lookup"><span data-stu-id="f16ce-115">Also see [How to Create an Agreement](http://msdn.microsoft.com/library/f8608cf7-8ac5-4f02-805e-5a0bdf19ca8c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f16ce-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f16ce-116">See Also</span></span>  
 <span data-ttu-id="f16ce-117">[使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="f16ce-117">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="f16ce-118">开发自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="f16ce-118">Developing Custom Pipeline Components</span></span>](../core/developing-custom-pipeline-components.md)