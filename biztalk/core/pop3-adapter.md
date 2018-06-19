---
title: POP3 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, about POP3 adapters
- authenticating, POP3 adapters
- POP3 adapters
- POP3 adapters, receive adapters
- POP3 adapters, authenticating
- receive adapters, POP3 adapters
ms.assetid: 008f7fa7-60c3-4ea3-b90d-821e4029a04c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbe21a3cf0e611a690cf22c88b1344926fa72744
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264549"
---
# <a name="pop3-adapter"></a>POP3 适配器
邮局协议 3 (POP3) 适配器用于从运行 Microsoft BizTalk Server POP3 协议通过另一服务器中保存 POP3 邮箱的服务器中检索数据。  
  
 POP3 适配器包含只有一个适配器，接收适配器。 接收适配器控制使用 POP3 适配器接收位置。  
  
 本主题讨论的工作流的 POP3 接收适配器。  
  
 **POP3 接收适配器**  
  
 POP3 从指定的 POP3 服务器上指定的邮箱接收适配器检索电子邮件。 默认情况下，接收 POP3 适配器适用 MIME 处理的电子邮件，它将下载和提交给 BizTalk Server 作为多部分 BizTalk 消息的这些消息。 POP3 接收适配器可以接收和处理采用以下格式的电子邮件：  
  
-   纯文本  
  
-   编码的 MIME  
  
-   MIME 加密  
  
-   MIME 编码和签名  
  
-   MIME 加密和签名  
  
 **POP3 接收适配器的批处理支持**  
  
 POP3 接收适配器不支持批处理。  
  
 **POP3 服务器的身份验证**  
  
 使用与 POP3 适配器支持以下身份验证方法：  
  
-   **基本。** POP3 服务器使用提供的凭据进行身份验证的用户。  这些凭据以明文形式发送。  
  
-   **Digest (APOP)。** POP3 服务器使用摘要式字符串进行身份验证。  
  
-   **安全密码身份验证 (SPA)。** POP3 服务器使用当前进程凭据进行身份验证。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [POP3 适配器是什么？](../core/what-is-the-pop3-adapter.md)  
  
-   [配置 POP3 适配器](../core/configuring-the-pop3-adapter.md)  
  
-   [演练： 创建使用 POP3 适配器 BizTalk 应用程序](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [处理与 POP3 适配器的多部分消息](../core/processing-multi-part-messages-with-the-pop3-adapter.md)