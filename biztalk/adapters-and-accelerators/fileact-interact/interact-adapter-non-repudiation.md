---
title: 交互适配器不可否认 |Microsoft Docs
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
ms.openlocfilehash: 8d9006ef82a9133884b8e1fbd1cf9caa981cf779
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366673"
---
# <a name="interact-adapter-non-repudiation"></a>交互适配器不可否认性
为传出的 InterAct 消息不可否认性的支持被通过将 SwInt:NRIndicator 设置为在 SwInt:RequestControl 或 SwInt:ResponseControl，根据需要，则返回 TRUE。 这才需要该服务不会默认情况下，选择不可否认支持根据服务配置文件。  
  
 不可否认性-基于传送该消息之前由 SNL，创建有效的签名。 因此，为了获取上传出请求消息的不可否认性支持，是必需的 SwInt:RequestCrypto 元素，包含在 SwInt:RequestControl SwInt:RequestControl 中设置 TRUE。  
  
 为响应消息的要求是等效的不过，所涉及的元素是 SwInt:ResponseCrypto，包含在 SwInt:ResponseControl;SwInt:ResponseCrypto 必须设置为 TRUE。  
  
 有关对请求不可否认性支持，有必要，涵盖 SwInt:RequestHeader、 SwInt:RequestPayload 和的 SwInt:RequestDescriptor SwInt:SwiftRequestRef 的消息签名。 SWIFTNet 链接自动生成 SwInt:SwiftRequestRef。 与生成 SwInt:SwiftRequestRef，SNL 还自动调节中用于生成必需的消息签名 SwSec:CryptoControl SwSec:MemberRef 值。 同样，有关非 repudiatin 支持的响应，有必要，涵盖 SwInt:ResponseHeader、 SwInt:ResponsePayload 和的 SwInt:ResponseDescriptor SwInt:SwiftResponseRef 的消息签名。 SWIFTNet 链接自动生成 SwInt:SwiftResponseRef。 与生成 SwInt:SwiftResponseRef，SNL 还自动调节中用于生成必需的消息签名 SwSec:CryptoControl SwSec:MemberRef 值。  
  
 如果业务服务配置文件默认情况下选择不可否认，必需的消息签名是仍需要选择 （如前面所述，SwInt:RequestControl 或 SwInt:ResponseControl），并在消息离开之前，必须选中SNL。  
  
 如果根据业务服务配置文件的功能选择调用上一条消息的不可否认性支持和消息找不到必要的签名，则消息将拒绝由该交换机。 将向消息的发件人返回状态异常消息。  
  
 有效负载加密不一致的不可否认性的支持。 如果为消息选择不可否认性支持和整体或部分负载进行加密，消息将被拒绝通过 SWIFTNet 链接。  
  
 请注意，如果服务不具有不可否认性功能，任何请求或响应指示在控件中，不可否认将被拒绝。  
  
## <a name="see-also"></a>请参阅  
 [InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)