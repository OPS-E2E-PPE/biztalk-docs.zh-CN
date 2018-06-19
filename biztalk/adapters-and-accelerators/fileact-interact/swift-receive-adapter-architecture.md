---
title: SWIFT 接收适配器体系结构 |Microsoft 文档
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
ms.openlocfilehash: 3aca9b5ef1fd1130feeebad3ec6fdf072d3bf88d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224981"
---
# <a name="swift-receive-adapter-architecture"></a>SWIFT 接收适配器体系结构
在 BizTalk Server 中，在其自己的内存空间中，这意味着创建一个单独的进程运行主机承载了接收适配器。 此主机被生成通过 SWIFTNet 链接 (SNL) 配置中定义的子系统。  
  
 服务器可执行文件已配置为在 SNL 配置 (paramfile) 子系统，通过执行 SWIFTNet 启动命令生成。 通过执行 SWIFTNet 停止命令终止 SNL 服务器应用程序。 SNL 管理服务器可执行文件的生存期。  
  
> [!NOTE]
>  服务调查局开发方案要求服务在其自己的安全上下文下运行的多个 SWIFT 成员的适配器。 这可以通过配置个人支持接收每个成员和生成多个实例的服务器可执行文件的位置 — 每个专用于一个接收位置。  
  
 在 BizTalk Server 中的接收适配器支持以下的通信模式，与 BizTalk 消息传送引擎进行交互：  
  
-   一种方法-在延迟的模式下操作接收适配器 （服务器） 时需要此模式。 在延迟模式下，该适配器将默认确认对于传入消息发送。 可以在适配器属性中配置该确认的默认值。 可以通过发送适配器 LOB 应用程序更高版本发送业务级别响应。  
  
    > [!NOTE]
    >  发生延迟模式下，所有值必须都填充在适配器配置中，因为该适配器构造响应。  
  
-   请求响应-在此模式下适配器提交到 BizTalk 从 SWIFT 请求并等待响应。 如果从 LOB 应用程序没有响应，该适配器将超时。 超时值为适配器配置中配置。 默认值为 60 秒。  
  
     接收适配器可以仅在一个线程上，从 SNL 接收回调。 这意味着，接收适配器可以进一步从接收消息 SNL 仅在提交第一条消息后。 因此，默认批次大小设置为 1。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [SWIFT 接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [SWIFT 接收适配器存储和转发](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)