---
title: AS2 在 BizTalk Server 中支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8ee230e-8f5f-4b51-99e2-0b38acaf5707
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8916f5c33d1d96cf9a1ce579a15e1894e651f89e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358835"
---
# <a name="as2-support-in-biztalk-server"></a>BizTalk Server 中的 AS2 支持
本主题提供了 AS2 处理和 BizTalk Server 如何实现它的一般概述。  
  
## <a name="introduction-to-as2"></a>AS2 介绍  
 用于 EDI 的常见传输是增值网络 (Van)。 这些是提供增值服务，例如精确和具有法律约束力的审核线索的专用网络。 但是，各个公司正在转为通过 Internet 交换 EDI 文档。 这降低了成本、 提高灵活性和效率，并在冗余性和可伸缩性方面具有优势。  
  
 实现 Internet (EDIINT) 的 EDI 的最常见方法是使用 AS2 (Applicability Statement 2)。 AS2 规范定义了基于 MIME 的安全对等业务数据交换。 通过 TCP/IP 使用 HTTP 传输包含带有 MIME 数据信封的消息。  
  
 AS2 使用 HTTP POST 操作发送 EDI、 XML 或其他业务数据。 AS2 并不局限于发送 EDI 数据。 请求 URI 可标识要用来解压缩并处理消息数据的进程。 消息处置通知 (MDN) 作为返回 HTTP 响应消息正文中或通过新的 HTTP POST 操作的确认到 URL 的原始发件人。  
  
 有关 EDI 消息传送的详细信息，请参阅[AS2 消息传送](../core/as2-messaging.md)。  
  
## <a name="how-as2-is-implemented-in-biztalk-server"></a>在 BizTalk Server 中 AS2 的实现方式  
 BizTalk Server 包括提供 AS2 支持的固有功能。 它不是外接程序对产品，例如适配器或加速器。 它内置于产品，并提供了以下功能：  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用 AS2 定义的方法发送、 接收和验证消息。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可帮助确保通过加密、 签名和压缩的数据传输的安全性。 为此，请[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用加密密钥、 数字签名和证书。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以将传入和传出 AS2 消息保存在不可否认存储中。 这包括在保存编码或解码 AS2 消息和保存 Mdn。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供的功能以保留附件文件名作为 AS2 消息的一部分。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使你能够检查重复的传入消息。  
  
- 您可以通过确认消息时，同一连接以同步方式或以异步方式通过不同的连接返回 Mdn。  
  
- 在指定的时间段内未收到 MDN 时，你可以重新发送 AS2 消息。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可提供特定于 AS2 的状态报告。 这些报告提供了 AS2 传输，包括与交换的确认的全面状态。  
  
- AS2 要求在接收端和发送端上使用 HTTP 适配器。  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以重写的默认签名证书为 AS2 消息通过定义每个协议的证书。 有关如何为参与方指定不同的证书的说明，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。  
  
## <a name="as2-components-in-biztalk-server"></a>在 BizTalk Server 中的 AS2 组件  
 用于 AS2 传输的 BizTalk Server 组件包括：  
  
- BizTalk EDI 应用程序，其中包含处理 AS2 文档所需的项目 （包括管道和架构）。  
  
  > [!NOTE]
  >  在 BizTalk Server 中配置的 AS2 功能时，配置程序会创建此应用程序。 每当创建将用于处理 AS2 消息的应用程序时，必须添加对 BizTalk EDI 应用程序从你的应用程序的引用。 有关详细信息，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
- AS2EdiReceive 管道执行 AS2 处理和随后的 EDI 处理通过 AS2 接收 EDI 消息。 有关详细信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。  
  
- AS2Receive 管道执行 AS2 处理通过 AS2 接收非 EDI 消息。 有关详细信息，请参阅[AS2 接收组件](../core/as2-receive-components.md)。  
  
- AS2EdiSend 管道执行 EDI 处理和随后的 AS2 处理通过 AS2 发送 EDI 消息。 有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。  
  
- AS2Send 管道执行 AS2 处理通过 AS2 发送非 EDI 消息。 有关详细信息，请参阅[AS2 发送组件](../core/as2-send-components.md)。  
  
- 贸易合作伙伴管理 (TPM) 用户界面，可用于设置处理属性为贸易合作伙伴参与 AS2 文档传输。 有关详细信息，请参阅[协议的角色中的 AS2 处理](../core/the-role-of-agreements-in-as2-processing.md)并**EDI 和 AS2 用户界面** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
- 状态报告提供了 AS2 的全面状态的用户界面交换和相关确认。 有关详细信息，请参阅[EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)。  
  
- 迁移工具 （参与方迁移工具），可将包含 AS2 属性从 BizTalk Server 2006 R2 或 BizTalk Server 2009 到 BizTalk Server 参与方数据迁移。 有关详细信息，请参阅[从以前版本的 BizTalk Server 迁移 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
## <a name="see-also"></a>请参阅  
 [AS2 解决方案体系结构](../core/as2-solution-architecture.md)   
 [EDI 和 AS2 状态报告](../core/edi-and-as2-status-reporting.md)   
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)