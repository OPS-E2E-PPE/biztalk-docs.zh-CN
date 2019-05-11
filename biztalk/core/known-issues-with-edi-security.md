---
title: EDI 安全的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d7f68bc-8460-4656-b9f2-955337458d78
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d4afab871dc34e3249d2ea3ed7d531b18472a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380676"
---
# <a name="known-issues-with-edi-security"></a>EDI 安全的已知的问题
本主题介绍了在安全方面的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2 解决方案。  
  
## <a name="biztalk-will-not-suspend-a-signed-message-from-a-party-for-which-no-certificate-is-set"></a>BizTalk 不会挂起来自未设置任何证书的参与方的签名消息  
 如果在参与方 （在参与方的参与方属性页的证书节点中），未设置签名证书，但来自该参与方的传入消息进行签名，BizTalk Server 将不会挂起消息，并引发异常的证书缺失问题.  
  
 如果您替代入站的消息属性 （在上的参与方作为 AS2 消息发送方页），并清除"应对消息进行签名"属性，BizTalk Server 将挂起已签名的传入消息。  
  
## <a name="access-to-program-files-folder-can-be-limited-to-prevent-file-tampering"></a>程序文件文件夹的访问权限可以进行限制以防文件被篡改。  
 如果未经过身份验证的用户提供包含 BizTalk Server 可执行文件和 EDI 架构的 Program Files 文件夹，这些用户可能会修改这些文件。 为避免出现该威胁，您可以使用访问控制列表 (Acl) 上的 Program Files 文件夹来限制对受信任的用户访问。  
  
## <a name="a-schema-with-a-long-field-can-be-susceptible-to-a-denial-of-service-attack"></a>具有长字段的架构可以很容易受到拒绝服务攻击  
 自定义的架构具有很长的字段可能会遭到拒绝服务攻击。 架构的附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有很长的字段，因此通常不是易受攻击。  
  
## <a name="message-processing-will-be-aborted-if-a-control-number-exceeds-its-maximum-length"></a>如果控制编号超过了其最大长度，将中止消息处理  
 交换、 组或事务集控制编号具有最大长度限制。 如果其中一个控制数字的长度超过最大长度，将中止某一参与方的所有消息的该编码类型的处理。 另一种编码类型 (而不是 X12，例如 EDIFACT) 的消息不会受到影响。 这可能表示存在安全漏洞。  
  
 如果序列号的长度超过最大长度，用户必须重置受影响的参与方的 EDI 属性中的序列号。 重置数目后，可以再次处理该编码类型的所有消息。  
  
 对于 X12 消息，一个控件的最大长度数字为九位。 对于 EDIFACT 消息，控制编号的最大长度是三个字段 14 位数字。  
  
## <a name="using-the-edi-receive-pipeline-with-an-http-adapter-will-leave-the-connection-open-if-no-ack-is-sent"></a>如果没有发送任何确认使用 EDI 接收管道，其中包含 HTTP 适配器将保留连接打开  
 如果您创建的接收位置使用 EDIReceive 管道，并且具有 HTTP 传输类型，则可能出现安全问题。 EdiReceive 管道将不会生成 HTTP"200 确定"确认。 如果不返回任何 EDI 确认，则连接将不正常终止，但将保持打开状态。 超时期限已过期时，该连接将超时时间。  
  
 这不是使用 AS2EdiREceive 管道的问题。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>如果启用了基于端口的身份验证，并且 BizTalk Server 不具有访问授权和安全信息的 X12 编码消息被挂起  
 **症状**  
  
 通过用于已启用的身份验证，并发送不能确定该消息的参与方的接收端口收到一条消息时，BizTalk Server 将挂起该消息。  
  
 **可能的原因**  
  
 BizTalk Server 的接收端口 （接收端口的"无身份验证"属性被清除） 启用身份验证，如果需要设置为"ISA1-2 （授权限定符和信息）"和"ISA3-4 （安全限定符和信息）"若要处理的交换的属性。 这些属性设置为 X12 中的参与方作为交换发送方的参与方的交换处理属性页。 如果 BizTalk Server 无法确定这些属性的值，它将挂起该消息。  
  
 这可能通过两种方式。 在第一种情况下，如果 BizTalk Server 无法确定参与方发送消息，它将使用 EDI 全局属性并不会访问授权和安全设置。 因此，它将挂起该消息。 在第二种情况下，如果 BizTalk Server 确定参与方，但未配置的参与方 ISA1-2 和 ISA3-4 属性，BizTalk Server 也无权访问授权和安全信息并将挂起该消息。  
  
 **解决方法**  
  
 请确保可以识别的消息发送方和 ISA1-2 和 ISA3-4 属性参与方协议中定义。  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)