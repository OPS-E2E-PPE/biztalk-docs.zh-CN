---
title: MIME SMIME 编码器管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, MIME/SMIME Encoder
- MIME/SMIME Encoder [pipeline component]
- BTS.EncryptionCert property
ms.assetid: 397505e6-47d0-4b63-9197-814ee4388369
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c6a79052d3294420c46bff2a1ce3c0ed869e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263061"
---
# <a name="mime-smime-encoder-pipeline-component"></a><span data-ttu-id="169a3-102">MIME SMIME 编码器管道组件</span><span class="sxs-lookup"><span data-stu-id="169a3-102">MIME-SMIME Encoder Pipeline Component</span></span>
<span data-ttu-id="169a3-103">MIME/SMIME 编码器管道组件可放置在发送管道的编码阶段。</span><span class="sxs-lookup"><span data-stu-id="169a3-103">The MIME/SMIME Encoder component can be placed into the Encode stage of a send pipeline.</span></span> <span data-ttu-id="169a3-104">它支持 7 位、8 位、二进制、quoted-printable、base64 和 UUencode 编码。</span><span class="sxs-lookup"><span data-stu-id="169a3-104">It supports 7bit, 8bit, binary, quoted-printable, base64, and UUencode encoding.</span></span> <span data-ttu-id="169a3-105">更改本地化数据字符集不会影响编码。</span><span class="sxs-lookup"><span data-stu-id="169a3-105">Localized data character set changes do not affect the encoding.</span></span>  
  
 <span data-ttu-id="169a3-106">此组件可用于对使用加密和签名证书的传出消息进行 MIME 编码、签名或加密。</span><span class="sxs-lookup"><span data-stu-id="169a3-106">This component can be used to either MIME encode, sign or encrypt an outgoing message with encryption and signing certificates.</span></span>  
  
 <span data-ttu-id="169a3-107">如果发送管道中包含已配置用来对消息进行签名的编码组件，但没有为包含运行该管道的主机的 BizTalk 组配置签名证书，则传出消息将挂起到运行该管道的主机的挂起队列中（并显示相应的错误）。</span><span class="sxs-lookup"><span data-stu-id="169a3-107">If there is an encoding component in the send pipeline that is configured to sign messages, and the BizTalk group that includes the host running the pipeline is not configured with a signing certificate, the outgoing message will be suspended (with the appropriate error) to the suspended queue of the host that is running the pipeline.</span></span> <span data-ttu-id="169a3-108">如果在运行服务的当前用户的个人证书存储中找不到签名证书，则消息将挂起到运行该管道的主机的挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="169a3-108">If the signing certificate cannot be found in the personal certificate store of the current user under which the service is running, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="169a3-109">如果出站管道中存在已配置用来对出站消息进行加密的编码组件，但在证书存储中找不到证书，则消息将挂起到运行该管道的主机的挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="169a3-109">If there is an encoding component in the outbound pipeline configured to encrypt outbound messages, and the certificate cannot be found in the certificate store, the message will be suspended to the suspended queue of the host that is running the pipeline.</span></span>  
  
 <span data-ttu-id="169a3-110">若要对接收已签名和加密的消息的请求-响应端口执行响应加密，必须在管道中的 MIME/SMIME 编码器管道组件之前添加自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="169a3-110">To perform response encryption on a request-response port that is receiving signed and encrypted messages, a custom pipeline component must be added to the pipeline before the MIME/SMIME Encoder pipeline component.</span></span> <span data-ttu-id="169a3-111">此自定义管道组件必须标识对应于加密证书的指纹，并将其设置为**BTS。EncryptionCert**消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="169a3-111">This custom pipeline component must identify the thumbprint corresponding to the encryption certificate and set it to the **BTS.EncryptionCert** property on the message context.</span></span> <span data-ttu-id="169a3-112">有关消息上下文属性的详细信息，请参阅[如何修改组属性](../core/how-to-modify-group-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="169a3-112">For more information about message context properties, see [How to Modify Group Properties](../core/how-to-modify-group-properties.md).</span></span>  
  
 <span data-ttu-id="169a3-113">有关配置 MIME/SMIME 编码器管道组件的信息，请参阅[如何配置 MIME SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="169a3-113">For information about configuring the MIME/SMIME Encoder pipeline component, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span> <span data-ttu-id="169a3-114">有关加密、 签名和证书的使用情况的 BizTalk Server 支持的详细信息，请参阅[发送和接收消息的安全性](../core/security-for-sending-and-receiving-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="169a3-114">For more information about BizTalk Server support for encryption, signing, and usage of certificates, see [Security for Sending and Receiving Messages](../core/security-for-sending-and-receiving-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="169a3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="169a3-115">See Also</span></span>  
 <span data-ttu-id="169a3-116">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="169a3-116">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 <span data-ttu-id="169a3-117">[MIME SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="169a3-117">[MIME-SMIME Property Schema and Properties](../core/mime-smime-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="169a3-118">MIME （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="169a3-118">MIME (BizTalk Server Sample)</span></span>](../core/mime-biztalk-server-sample.md)