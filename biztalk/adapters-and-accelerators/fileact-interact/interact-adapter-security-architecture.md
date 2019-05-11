---
title: InterAct 适配器安全体系结构 |Microsoft Docs
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
ms.openlocfilehash: 445f62df17c45b80d7be83b9e9283f091e797fb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366656"
---
# <a name="interact-adapter-security-architecture"></a>InterAct 适配器安全体系结构
使用 SWIFTNet 链接 (SNL) 和 SWIFTAlliance 网关 （压降） 中固有的证书和加密功能来实现消息传输和接收的安全性。 SWIFT 建议服务设计为将"端到端"签名应用的交互 — 即，登录请求和响应消息。  
  
 SWIFTNet 链接安全模块通过实现加密操作。 此模块将允许签名和 PKI 密钥的加密。 性质和程度的加密操作被指定为传递给 Api 请求和响应控件的数据结构的一部分。  
  
 SWIFTNet 支持签名/加密 RequestPayload 或 ResponsePayload。 此外可以签名 RequestHeader 或 ResponseHeader。  
  
## <a name="signingencrypting-requests-and-responses"></a>签名/加密请求和响应  
 应用请求 SWIFTNet 交互元素上的加密操作的规则如下所示：  
  
- RequestControl： 这是发往 SWIFTNet 仅。 SWIFTNet 将 RequestDescriptor 传递到响应方 （和一些元素还向请求者）。 因此，可以对它执行向服务器处理加密操作没有客户端进程。  
  
- RequestE2EControl： 此元素包含信息，以确保可靠的端到端消息传送。 可以对它不执行任何加密操作。  
  
- RequestHeader： 它是由 SWIFTNet 并传递到响应方保持不变。 因此，这可以仅进行签名。  
  
- RequestPayload： 可以对此执行任何加密操作。  
  
- 加密的元素： 这些与此请求之前激活的加密操作。 可以对它们不执行任何加密操作。  
  
  将加密函数应用于 SWIFTNet 交互响应的规则包括：  
  
- ResponseControl： 这是发往 SWIFTNet 仅。 SWIFTNet 将 ResponseDescriptor 传递给请求者。 因此，可以对它执行向客户端处理加密操作，无服务器进程。  
  
- ResponseE2EControl： 此元素包含信息，以确保可靠的端到端消息传送。 可以对它不执行任何加密操作。  
  
- ResponseHeader： 此元素可进行签名 （将传输未更改到请求者）。  
  
- ResponsePayload： 可以是加密和/或签名。  
  
- 加密的元素： 这些与此请求之前激活的加密操作。 可以对它们不执行任何加密操作。  
  
## <a name="receiving-requests-with-cryptography"></a>接收请求的加密  
 服务器进程可能会收到已受到由请求者的加密操作的请求。 传入请求包含所有相关信息以启用反向加密操作。 CryptoInternal 信息是，这样解密和验证函数现在将更有效地操作。  
  
 服务器进程将需要激活的 DN 解密需要进行的安全上下文  
  
 反向加密操作将然后修改请求验证 (解密） 的方式，将发出原始请求可用原封不动地向服务器进程，因为它最初发送到加密的客户端进程操作。 对于响应，类似的处理将会发生。 务必要验证签名不只验证的签署未被更改，但其将进行身份验证是否签名者为正版。 这要求 SignDN 使用有效的证书。 有效的证书是证书尚未吊销 （在证书吊销列表中，保留集中在 SWIFTNet 内查找）。  
  
## <a name="activation"></a>激活  
 SWIFTNet 链接可以运行验证和解密在自动模式下的所有传入的请求和传入的响应。 这意味着，将自动处理 SWIFTNet 链接 （验证和解密） 最后一个加密阻止所有传入的请求 （服务器端） 或传入的响应 （客户端）。 先决条件是解密 （如果请求解密） 所需的安全上下文将打开，并且，已在自动模式下 （此设置为自动模式 Sw:InitRequest 或 Sw:HandleInitResponse，通过完成初始化 SWIFTNet 链接设置为"自动"CryptoMode 或更好的仍"高级"的交互。 (我们将始终使用"高级"对于交互适配器，因为这会使客户端或服务器应用程序窗体中恢复意外的加密通过远程位置，或从过期的证书。  
  
 SWIFTNet 链接操作签名和加密的自动在一个传出的请求 （或一个传出的响应），如果 RequestCrypto (ResponseCrypto) 的字段初始化为"TRUE"的请求 （响应） RequestControl (ResponseControl) 中。  
  
 在这种情况下 SWIFTNet 链接处理的最后一个加密块。 先决条件是，打开所需的签名 （如果请求签名） 的安全上下文，加密块在上的签名和加密要求，指示的请求，并显示 RequestCrypto (ResponseCrypto)标志设置为"TRUE"RequestControl (ResponseControl) 中。 此操作始终后，而不考虑在初始化的客户端或服务器时使用 CryptoMode。  
  
## <a name="see-also"></a>请参阅  
 [InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct 适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)