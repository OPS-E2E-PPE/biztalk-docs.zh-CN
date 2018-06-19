---
title: 交互适配器不可否认性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a13fb77c-b10c-4f8a-ba4b-efecc83e092c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d7eabd7eab04c0bd64af0164b73b38af197ac9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224917"
---
# <a name="interact-adapter-non-repudiation"></a>交互适配器不可否认性
不可否认性传出交互，消息支持是通过将 SwInt:NRIndicator 设置为 TRUE SwInt:ResponseControl，根据需要对 SwInt:RequestControl 中获取的。 如果这是必需仅服务不会在默认情况下，选择不可否认性支持根据服务的配置文件。  
  
 不可否认性取决于创建的 SNL，就在传输消息之前的有效签名。 因此，为了获取上传出请求消息的不可否认性支持，它是必需的 SwInt:RequestCrypto 元素，包含在 SwInt:RequestControl，要在 SwInt:RequestControl 设置 TRUE。  
  
 响应消息的要求是等效，只不过所涉及的元素包含在 SwInt:ResponseControl; 是 SwInt:ResponseCrypto，SwInt:ResponseCrypto 必须设置为 TRUE。  
  
 不可否认性请求获得支持，它是必需的消息签名，以涵盖 SwInt:RequestHeader、 SwInt:RequestPayload 和的 SwInt:RequestDescriptor SwInt:SwiftRequestRef 的。 通过 SWIFTNet 链接自动生成 SwInt:SwiftRequestRef。 与生成 SwInt:SwiftRequestRef，SNL 还自动调节中用来生成必需的消息签名 SwSec:CryptoControl SwSec:MemberRef 值。 同样，响应非 repudiatin 获得支持，就需要以涵盖 SwInt:ResponseHeader、 SwInt:ResponsePayload 和的 SwInt:ResponseDescriptor SwInt:SwiftResponseRef 的消息签名。 通过 SWIFTNet 链接自动生成 SwInt:SwiftResponseRef。 与生成 SwInt:SwiftResponseRef，SNL 还自动调节中用来生成必需的消息签名 SwSec:CryptoControl SwSec:MemberRef 值。  
  
 如果业务服务配置文件选择不可否认性，默认情况下，必需的消息签名仍需要选择 （正如刚才中所述，SwInt:RequestControl 或 SwInt:ResponseControl），并在消息离开之前，必须选中SNL。  
  
 如果根据业务服务配置文件的功能选择时，将调用不可否认性支持上一条消息，并且与消息找不到必要的签名，然后将由交换机拒绝消息。 状态异常消息将返回到消息的发件人。  
  
 负载加密与不一致时不可否认性支持。 如果负载进行加密的全部或部分不可否认性支持选择的消息，消息将被拒绝由 SWIFTNet 链接。  
  
 请注意，如果服务不具有不可否认性功能，任何请求或响应，该值指示在控件中，不可否认性将被拒绝。  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)