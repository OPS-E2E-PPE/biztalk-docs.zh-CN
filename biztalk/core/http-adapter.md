---
title: "HTTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, receive adapters
- HTTP adapters, send adapters
- HTTP adapters
- receive adapters, HTTP adapters
- send adapters, HTTP adapters
- HTTP adapters, about HTTP adapters
ms.assetid: a9423052-8392-4006-ab46-79834169c796
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d9be9fac6fdb65c4516c671b6c0e30096e83a27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter"></a>HTTP 适配器
使用 HTTP 适配器可以通过 HTTP 协议在 Microsoft BizTalk Server 和应用程序之间交换信息。 HTTP 是企业间进行消息交换的主要协议。 通过向指定的 HTTP URL 发送 HTTP POST 或 HTTP GET 请求，应用程序可以向服务器发送消息。 HTTP 适配器接收 HTTP 请求，并将其提交到 BizTalk Server 进行处理。 同样，通过向指定的 HTTP URL 发送 HTTP POST 请求，BizTalk Server 可以将消息传输给远程应用程序。  
  
 HTTP 适配器由两个适配器组成：一个接收适配器和一个发送适配器。 HTTP 接收适配器是 Microsoft Internet 信息服务 (IIS) Internet 服务器应用程序编程接口 (ISAPI) 扩展，IIS 进程将作为该适配器的接收位置的宿主并控制这些接收位置。 HTTP 发送适配器控制使用 HTTP 适配器的发送端口。  
  
 本部分将介绍 HTTP 接收适配器和 HTTP 发送适配器的工作流和批处理支持。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [HTTP 接收适配器](../core/http-receive-adapter.md)  
  
-   [HTTP 发送适配器](../core/http-send-adapter.md)  
  
-   [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)  
  
-   [HTTP 适配器安全建议](../core/http-adapter-security-recommendations.md)