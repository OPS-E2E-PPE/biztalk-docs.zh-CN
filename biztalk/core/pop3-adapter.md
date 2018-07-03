---
title: POP3 适配器 |Microsoft Docs
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
ms.openlocfilehash: 34a5f6a73f30ba831256ce1699b9a6a77b75c102
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982790"
---
# <a name="pop3-adapter"></a>POP3 适配器
使用邮局协议 3 (POP3) 适配器从 POP3 邮箱所在到通过 POP3 协议运行 Microsoft BizTalk Server 的服务器的服务器检索数据。  
  
 POP3 适配器由只有一个适配器，接收适配器组成。 接收适配器控制使用 POP3 适配器的接收位置。  
  
 本主题讨论的工作流的 POP3 接收适配器。  
  
 **POP3 接收适配器**  
  
 从指定的 POP3 服务器上指定的邮箱，POP3 接收适配器检索电子邮件。 默认情况下，POP3 接收适配器适用 MIME 处理到其下载和这些将消息提交给 BizTalk Server 作为多部分 BizTalk 消息的电子邮件消息。 POP3 接收适配器可以接收和处理采用以下格式的电子邮件：  
  
- 纯文本  
  
- MIME 编码  
  
- MIME 加密  
  
- MIME 编码和签名  
  
- MIME 加密和签名  
  
  **POP3 接收适配器的批处理支持**  
  
  POP3 接收适配器不支持批处理。  
  
  **POP3 服务器的身份验证**  
  
  用于 POP3 适配器支持以下身份验证方法：  
  
- **基本。** POP3 服务器使用用户提供的凭据进行身份验证。  这些凭据以明文形式发送。  
  
- **摘要 (APOP)。** POP3 服务器进行身份验证使用摘要字符串。  
  
- **安全密码身份验证 (SPA)。** POP3 服务器使用当前进程凭据进行身份验证。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [POP3 适配器概述](../core/what-is-the-pop3-adapter.md)  
  
-   [配置 POP3 适配器](../core/configuring-the-pop3-adapter.md)  
  
-   [演练：创建使用 POP3 适配器的 BizTalk 应用程序](../core/walkthrough-creating-a-biztalk-application-that-uses-the-pop3-adapter.md)  
  
-   [使用 POP3 适配器处理多部分消息](../core/processing-multi-part-messages-with-the-pop3-adapter.md)