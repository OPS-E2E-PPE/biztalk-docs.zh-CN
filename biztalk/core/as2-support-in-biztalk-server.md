---
title: "AS2 BizTalk Server 中支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ee230e-8f5f-4b51-99e2-0b38acaf5707
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5e40d7c45ffc8622a420d87bd60e3b74659db93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-support-in-biztalk-server"></a>BizTalk Server 中的 AS2 支持
本主题简要地从整体上介绍了 AS2 处理以及 [!INCLUDE[prague](../includes/prague-md.md)] 实现 AS2 处理的方式。  
  
## <a name="introduction-to-as2"></a>AS2 介绍  
 增值网络 (VAN) 是 EDI 的一种常见传输方式。 增值网络是提供增值服务（例如，精确且合法的绑定审计跟踪）的专有网络。 但是，各个公司正在转为通过 Internet 交换 EDI 文档。 这样不仅可以降低成本、提高灵活性和效率，而且在冗余性和伸缩性方面具有明显优势。  
  
 通过 Internet 实现 EDI (EDIINT) 的最常见方法是使用 AS2 (Applicability Statement 2)。 AS2 规范定义了基于 MIME 的安全对等业务数据交换。 包含带有 MIME 数据的信封的消息使用 TCP/IP 上的 HTTP 进行传输。  
  
 AS2 使用 HTTP POST 操作发送 EDI、XML 或其他业务数据。 AS2 并非只能发送 EDI 数据。 请求-URI 可标识要用来解压缩并处理消息数据的过程。 消息处置通知 (MDN) 作为 HTTP 响应消息正文中的确认返回，或者通过发送到原始发送方的 URL 的新的 HTTP POST 操作作为确认返回。  
  
 有关 EDI 消息传送的详细信息，请参阅[AS2 消息传送](../core/as2-messaging.md)。  
  
## <a name="how-as2-is-implemented-in-biztalk-server"></a>BizTalk Server 中 AS2 的实现方式  
 [!INCLUDE[prague](../includes/prague-md.md)] 包括了可提供 AS2 支持的固有功能。 它不是产品的外接程序，例如适配器或加速器。 它内置于产品之中，可提供以下功能：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 AS2 定义方法来发送、 接收和验证消息。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]有助于确保通过加密、 签名和压缩的数据传输的安全性。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用加密密钥、数字签名和证书来实现这一目的。  
  
-   通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以将传入和传出的 AS2 消息保存在不可否认的存储位置。 包括在保存编码或解码的 AS2 消息和保存 MDN 时，都需这么做。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了将附件文件名保留为 AS2 消息的一部分的能力。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使你能够检查重复的传入消息。  
  
-   既可以通过与确认消息时使用连接相同的连接同步返回 MDN，也可以通过不同的连接异步返回 MDN。  
  
-   如果在指定时间段内未接收到 MDN，你可以重新发送 AS2 消息。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可提供特定于 AS2 的状态报告。 这些报告提供了 AS2 传输的全面状态，其中也包括与交换有关的确认状态。  
  
-   AS2 要求在接收端和发送端均使用 HTTP 适配器。  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使你能够通过定义每个协议的证书来覆盖 AS2 消息的默认签名证书。 有关如何为方指定不同的证书的说明，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
## <a name="as2-components-in-biztalk-server"></a>BizTalk Server 中的 AS2 组件  
 用于 AS2 传输的 [!INCLUDE[prague](../includes/prague-md.md)] 组件包括以下内容：  
  
-   BizTalk EDI 应用程序，包含处理 AS2 文档所需的项目（包括管道和架构）。  
  
    > [!NOTE]
    >  当你配置 [!INCLUDE[prague](../includes/prague-md.md)] 中的 AS2 功能时，配置程序会创建此应用程序。 无论何时，只要你创建了一个处理 AS2 消息的应用程序，就必须从你的应用程序中添加对 BizTalk EDI 应用程序的引用。 有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
-   AS2EdiReceive 管道，对通过 AS2 接收的 EDI 消息执行 AS2 处理和随后的 EDI 处理。 有关详细信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。  
  
-   AS2Receive 管道，对通过 AS2 接收的非 EDI 消息执行 AS2 处理。 有关详细信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。  
  
-   AS2EdiSend 管道，对通过 AS2 发送的 EDI 消息执行 EDI 处理和随后的 AS2 处理。 有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。  
  
-   AS2Send 管道，对通过 AS2 发送的非 EDI 消息执行 AS2 处理。 有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。  
  
-   贸易合作伙伴管理 (TPM) 用户界面，可用来设置参与 AS2 文档传输的贸易合作伙伴的处理属性。 有关详细信息，请参阅[AS2 处理的协议角色](../core/the-role-of-agreements-in-as2-processing.md)和**EDI 和 AS2 UI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
-   状态报告用户界面，提供了 AS2 交换和相关确认的全面状态信息。 有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
-   通过迁移工具（参与方迁移工具），可以将包含 AS2 属性的参与方数据从 BizTalk Server 2006 R2 或 BizTalk Server 2009 迁移到 [!INCLUDE[prague](../includes/prague-md.md)]。 有关详细信息，请参阅[迁移 BizTalk Server 以前版本中的 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
## <a name="see-also"></a>另请参阅  
 [AS2 解决方案体系结构](../core/as2-solution-architecture.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)