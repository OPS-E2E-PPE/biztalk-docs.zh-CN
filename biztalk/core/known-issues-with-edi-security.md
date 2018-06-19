---
title: EDI 安全的已知问题 |Microsoft 文档
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
ms.openlocfilehash: 9517f6c5b1aeae06b5989eef12fe269f81a27c74
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22262429"
---
# <a name="known-issues-with-edi-security"></a>EDI 安全的已知问题
本主题介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 解决方案在安全性方面存在的已知问题。  
  
## <a name="biztalk-will-not-suspend-a-signed-message-from-a-party-for-which-no-certificate-is-set"></a>BizTalk 不会挂起来自未设置任何证书的参与方的签名消息  
 如果您未对某一参与方设置签名证书（在该参与方的“参与方属性”页的“证书”节点），但是来自该参与方的传入消息已签名，BizTalk Server 不会挂起该消息，也不会就此证书缺失问题而引发异常。  
  
 如果您替代了入站消息属性（在“作为 AS2 消息发送方的参与方”页上），且清除了“应对消息进行签名”属性，则 BizTalk Server 将挂起已签名的传入消息。  
  
## <a name="access-to-program-files-folder-can-be-limited-to-prevent-file-tampering"></a>可以对 Program Files 文件夹的访问权限进行限制以防文件被篡改。  
 如果 Program Files 文件夹内包含未授权用户也可访问的 BizTalk Server 可执行文件和 EDI 架构，此类文件可能会被这些用户修改。 为了防范这种危险，可以使用 Program Files 文件夹上的访问控制列表 (ACL) 来仅对可信用户授予访问权限。  
  
## <a name="a-schema-with-a-long-field-can-be-susceptible-to-a-denial-of-service-attack"></a>字段很长的架构容易遭受拒绝服务攻击  
 具有很长字段的自定义架构可能会遭到拒绝服务的攻击。 与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起提供的架构没有很长的字段，因此一般不会遭受这种攻击。  
  
## <a name="message-processing-will-be-aborted-if-a-control-number-exceeds-its-maximum-length"></a>如果控制编号超过了最大长度的限制，消息处理将会中止  
 交换、组或者事务集控制编号都存在最大长度限制。 如果此类控制编号的其中一个编号的长度超出了最大长度限制，则对单个参与方的所有该编码类型消息的处理将中止。 其他编码类型（如，是 EDIFACT 而不是 X12）的消息将不会受到影响。 这样可能产生安全漏洞。  
  
 如果某序列号的长度超出了最大长度限制，用户必须在相应参与方的 EDI 属性中重新设置该序列号。 重新设置该序列号后，该编码类型的所有消息便立即可以重新进行处理。  
  
 对于 X12 消息，控制编号的最大长度为九位。 对于 EDIFACT 消息，控制编号的最大长度为三个字段 14 位。  
  
## <a name="using-the-edi-receive-pipeline-with-an-http-adapter-will-leave-the-connection-open-if-no-ack-is-sent"></a>使用带 HTTP 适配器的 EDI 接收管道时，如果没有发送任何确认，连接将处于打开状态  
 如果创建的接收位置使用 EDIReceive 管道，但采用 HTTP 传输类型，则可能会导致安全问题。 EdiReceive 管道将不生成 HTTP“200 OK”确认。 如果未返回 EDI 确认，连接将以非正常方式终止，但仍保持打开状态。 当超时期过后，该连接将超时。  
  
 而 AS2EdiREceive 管道不会出现这种问题。  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a>如果已启用基于端口的身份验证而 BizTalk Server 却无权访问授权和安全信息，X12 编码的消息将挂起  
 **症状**  
  
 如果某消息是通过已启用身份验证的接收端口接收的，而又无法确定发送该消息的参与方，BizTalk Server 将挂起该消息。  
  
 **可能的原因**  
  
 如果已为某接收端口启用了身份验证（清除了该接收端口的“无验证”属性），则 BizTalk Server 需要获得“ISA1-2 (授权限定符和信息)”和“ISA3-4 (安全限定符和信息)”属性的设置才能处理相应的交换。 这些属性是在作为交换发送方的参与方的“X12 交换处理属性”页为相应参与方设置的。 如果 BizTalk Server 不能确定这些属性的值，它将挂起相应消息。  
  
 这一问题分为两种情况： 第一种情况，如果 BizTalk Server 无法确定发送相应消息的参与方，它将使用 EDI 全局属性，并且将无权访问授权和安全设置。 因此，它将挂起该消息。 第二种情况，如果 BizTalk Server 已确定了相应的参与方，但是该参与方的 ISA1-2 和 ISA3-4 属性并没有进行配置，则 BizTalk Server 也无权访问授权和安全信息，因而将挂起相应消息。  
  
 **解决方法**  
  
 确保可以识别发送消息的参与方，且已在参与方协议中定义 ISA1-2 和 ISA3-4 属性。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)