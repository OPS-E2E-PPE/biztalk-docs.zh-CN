---
title: SWIFT 接收适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23deda6ba243e3b6823f5b8b80e560260c45fc7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364618"
---
# <a name="swift-receive-adapter-architecture"></a>SWIFT 接收适配器体系结构
在 BizTalk Server 中，接收适配器都托管在自己的内存空间，这意味着创建单独的进程运行主机。 此主机生成的在 SWIFTNet 链接 (SNL) 配置中定义的子系统。  
  
 服务器可执行文件配置为在 SNL 配置 (paramfile) 子系统和生成的执行 SWIFTNet 开始命令。 通过执行 SWIFTNet Stop 命令终止 SNL 服务器应用程序。 SNL 管理服务器可执行文件的生存期。  
  
> [!NOTE]
>  服务局方案需要适配器服务在其自己的安全上下文下运行的多个 SWIFT 成员。 可以通过配置单个支持此接收位置，每个成员和生成服务器可执行文件的多个实例，每个专用于一个接收位置。  
  
 在 BizTalk Server 中，接收适配器支持以下的通信模式，以与 BizTalk 消息引擎交互：  
  
-   一种方法，此模式下是必需的当在延迟模式下运行时接收适配器 （服务器）。 在延迟模式下，适配器发送的传入消息的默认确认。 可以在适配器属性中配置确认的默认值。 可以通过发送适配器的 LOB 应用程序的更高版本发送业务级别响应。  
  
    > [!NOTE]
    >  发生延迟模式下时的所有值必须被都填满在适配器配置中，因为该适配器构造响应。  
  
-   请求响应 — 在此模式下，适配器提交到 BizTalk 从 SWIFT 请求并等待响应。 如果从 LOB 应用程序没有响应，该适配器将会超时。 可在适配器配置中配置的超时值。 默认值为 60 秒。  
  
     接收适配器可以仅在一个线程上，从 SNL 接收回调。 这意味着，接收适配器可以进一步从接收消息 SNL 仅提交的第一个消息后。 因此，默认批大小设置为 1。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [SWIFT 接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [SWIFT 接收适配器存储和转发](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)