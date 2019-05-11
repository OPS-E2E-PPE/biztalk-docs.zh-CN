---
title: HTTP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, receive adapters
- HTTP adapters, send adapters
- HTTP adapters
- receive adapters, HTTP adapters
- send adapters, HTTP adapters
- HTTP adapters, about HTTP adapters
ms.assetid: a9423052-8392-4006-ab46-79834169c796
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d9bfc533222dad9411c6c56e67c37b5c9a37212
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382872"
---
# <a name="http-adapter"></a>HTTP 适配器
使用 HTTP 适配器通过 HTTP 协议交换 Microsoft BizTalk Server 和应用程序之间的信息。 HTTP 是企业间进行消息交换的主要协议。 应用程序可以通过将 HTTP POST 或 HTTP GET 请求发送到指定的 HTTP URL 向服务器发送消息。 HTTP 适配器接收 HTTP 请求，并将其提交给 BizTalk Server 进行处理。 同样，BizTalk Server 可以将 HTTP POST 请求发送到指定的 HTTP URL 传输给远程应用程序的消息。  
  
 HTTP 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。 HTTP 接收适配器是 Microsoft Internet 信息服务 (IIS) Internet 服务器应用程序编程接口 (ISAPI) 扩展的 IIS 进程的宿主并控制使用 HTTP 适配器的接收位置。 HTTP 发送适配器控制使用 HTTP 适配器的发送端口。  
  
 本部分讨论了工作流和批处理支持 HTTP 接收适配器和 HTTP 发送适配器。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [HTTP 接收适配器](../core/http-receive-adapter.md)  
  
-   [HTTP 发送适配器](../core/http-send-adapter.md)  
  
-   [配置 HTTP 适配器](../core/configuring-the-http-adapter.md)  
  
-   [HTTP 适配器的安全建议](../core/http-adapter-security-recommendations.md)