---
title: 交互适配器安全体系结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a4924b8c-1fda-4a0c-b9be-8f2ccba38013
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de0eee57daec102507a9e502e3146e1cfcdec723
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225357"
---
# <a name="interact-adapter-security-architecture"></a>交互适配器安全体系结构
使用 SWIFTNet 链接 (SNL) 和 SWIFTAlliance 网关 （压降） 中的固有的证书和加密功能实现的消息发送和接收的安全性。 SWIFT 建议服务设计为将"端到端"签名应用的交互 — 也就是说，来签署请求和响应消息。  
  
 SWIFTNet 链接安全模块通过实现加密操作。 此模块将允许签名和加密使用 PKI 密钥。 性质和加密操作的范围被指定为传递给 Api 的请求和响应控件数据结构的一部分。  
  
 SWIFTNet 支持签名/加密 RequestPayload 或 ResponsePayload。 此外可以签名 RequestHeader 或 ResponseHeader。  
  
## <a name="signingencrypting-requests-and-responses"></a>签名/加密请求和响应  
 应用 SWIFTNet 交互请求的元素上的加密操作的规则如下所示：  
  
-   RequestControl： 这是要发送到 SWIFTNet 仅。 SWIFTNet 将 RequestDescriptor 传递到响应方 （和某些元素还与请求者）。 因此，可以对其不执行任何客户端进程向服务器处理加密操作。  
  
-   RequestE2EControl： 此元素包含的信息，以确保可靠的端到端消息传送。 可以在其上不执行任何加密操作。  
  
-   RequestHeader： 它是由 SWIFTNet 和传达到响应方保持不变。 因此，这可以仅进行签名。  
  
-   RequestPayload： 可以对这执行任何加密操作。  
  
-   加密的元素： 这些与此请求以前激活加密操作。 可以对这些不执行任何加密操作。  
  
 将加密函数应用于 SWIFTNet 交互响应的规则包括：  
  
-   ResponseControl： 这是要发送到 SWIFTNet 仅。 SWIFTNet 将 ResponseDescriptor 提供给请求者。 因此，向客户端处理加密操作，没有服务器进程可以对它执行。  
  
-   ResponseE2EControl： 此元素包含的信息，以确保可靠的端到端消息传送。 可以在其上不执行任何加密操作。  
  
-   ResponseHeader： 此元素可以进行签名 （它传输不变到请求者）。  
  
-   ResponsePayload： 可以进行加密和/或签名。  
  
-   加密的元素： 这些与此请求以前激活加密操作。 可以对这些不执行任何加密操作。  
  
## <a name="receiving-requests-with-cryptography"></a>接收请求加密  
 服务器进程可能会收到已受到请求者的加密操作的请求。 传入的请求包含启用反向加密操作的所有相关信息。 会因此现在将有效地执行运算的解密和验证函数的 CryptoInternal 信息。  
  
 服务器进程将需要激活的解密需要发生 DN 的安全上下文  
  
 然后将反向加密操作由修改请求验证 (解密） 的方式，将发出原始请求可用原封不动地到服务器过程中，因为最初将它传送到加密客户端进程操作。 响应，类似的处理会发生。 务必要实现的签名验证不仅验证的签署未被更改，但其将进行身份验证是否签名者为正版。 这要求 SignDN 使用有效的证书。 有效的证书是证书尚未吊销 （在证书吊销列表中，保留集中在 SWIFTNet 内查找）。  
  
## <a name="activation"></a>激活  
 SWIFTNet 链接可以运行验证和解密在自动模式下的所有传入的请求和传入响应。 这意味着 SWIFTNet 链接将自动处理 （验证和解密） 最后一个加密阻止所有传入的请求 （服务器端） 或传入响应 （客户端）。 先决条件都已打开解密 （如果请求解密） 所需的安全上下文并且都具有已 SWIFTNet 链接在自动模式下 （此设置为自动模式下由 Sw:InitRequest 或 Sw:HandleInitResponse，未初始化设置为"自动"CryptoMode 或更好地仍"高级"交互。 (我们将始终使用"高级"对于交互适配器，因为这会使客户端或服务器应用程序窗体中恢复意外的加密通过远程位置，或从过期的证书。  
  
 如果字段 RequestCrypto (ResponseCrypto) 初始化为"TRUE"的请求 （响应） RequestControl (ResponseControl) 中，SWIFTNet 链接进行操作签名和加密的自动在一个传出的请求 （或一个传出的响应）。  
  
 在这种情况下 SWIFTNet 链接处理的最后一个加密块。 先决条件是，打开所需的签名 （如果请求签名） 的安全上下文，加密的块是在使用上的签名和加密所需，指示请求，并存在 RequestCrypto (ResponseCrypto)标志中 RequestControl (ResponseControl) 设置为"TRUE"。 此操作始终后，而不考虑使用在客户端或服务器初始化 CryptoMode。  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [交互适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)