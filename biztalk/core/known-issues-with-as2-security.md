---
title: "AS2 安全的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b291e000-630d-49a1-8e19-f76c4dfee294
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb633e092ed568bb3817df7be788364934be446
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-as2-security"></a>AS2 安全的已知问题
本主题介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 解决方案在安全方面的已知问题。  
  
## <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>AS2 解码器将不验证在主机上是否已配置证书或是否为目标参与方已配置证书  
 只要在证书存储区中配置了消息的私用证书，AS2 解码器就会解密该消息。 但是，AS2 解码器将不验证解密证书是否与在主机上配置的证书相同。 接收到的消息可使用多个证书进行加密。  
  
## <a name="storing-as2-messages-in-wire-format-can-lead-to-a-security-issue"></a>以传输格式存储 AS2 消息可能会导致安全问题  
 不使用证书时，不推荐在不可否认接收 (NRR) 数据库中以传输格式存储 AS2 消息。 这样做可能导致安全问题。  
  
## <a name="messages-or-mdns-to-be-stored-in-the-nrr-database-should-be-signed"></a>应对要存储在 NRR 数据库中的消息或 MDN 签名  
 为保证接收的不可否认性，必须对适用消息进行验证并确保适用消息的完整性。 实现此目的的推荐方法是对消息使用数字签名。 因此，如果将 AS2 参与方属性配置为在不可否认数据库中存储消息或 MDN，则应将 AS2 属性配置为对将存储的消息或 MDN 签名。  
  
## <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>如果证书无效，则 BizTalk Server 将无法对以传输格式保存的消息解密  
 **症状**  
  
 BizTalk Server 无法对不可否认数据库中以传输格式保存的入站 AS2 消息解密。  
  
 **可能的原因**  
  
 解密消息所需的证书已过期或已被吊销。 如果自 AS2 消息保存在不可否认数据库以来已过去一定时间，则更有可能发生上述情况。 如果发生这种情况，则您可能不能立即访问该消息的有效证书。  
  
 **解决方法**  
  
 获取有效证书，以对消息进行解密。  
  
## <a name="the-inner-envelope-of-a-signed-as2-message-must-not-be-changed-after-the-signature-has-been-calculated"></a>在计算签名后不得更改已签名的 AS2 消息的内层信封  
 对 AS2 消息签名时，将根据内层信封标头和负载计算该签名。 如果在计算签名后更改了内层信封，则该签名将受损。 可以更改边界标头或边界标头以外的任何对象，但不得更改边界标头以内的任何对象。  
  
## <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>对进程内主机实例和独立主机实例使用相同的登录名，以确保可识别个人存储区  
 只有在为登录凭据与主机实例关联的用户加载了用户配置文件时，个人证书存储区才可用于消息处理。 个人存储区用于签名证书和解密证书（用户自己的私钥）。 默认情况下，将为进程内主机实例加载用户配置文件；但默认情况下不会为独立主机实例加载用户配置文件。 您可以通过应用程序为独立主机加载用户配置文件。 另外，也可以通过对进程内主机实例和独立主机实例使用相同的登录名来解决此问题。  
  
 您可以创建空服务来加载用户配置文件，而无需让应用程序来加载此文件。 有关创建空的服务的信息，请参阅[如何： 创建 Windows 服务](http://go.microsoft.com/fwlink/?LinkId=196492)。 创建服务后，打开计算机管理对话框中，打开服务的属性对话框，单击**Log On**选项卡上，选择**此帐户**，输入用于登录名隔离主机实例，然后单击**确定**。 然后您可以手动启动该服务，以加载该登录用户的用户配置文件。  
  
## <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>证书的“密钥用法”属性必须与证书的用途匹配  
 用于 AS2 传输的证书必须具有实现其用途所需的属性。 对于签名和签名验证，证书的“密钥用法”属性必须为“数字签名”。 对于加密和解密，证书的“密钥用法”属性必须为“数据加密”或“密钥加密”。 可通过双击证书、单击“证书”对话框中的“详细信息”选项卡并检查“密钥用法”字段来验证“密钥用法”属性。  
  
## <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>如果没有对参与方设置 AS2-To 属性，则将为传出的 MDN 验证证书解析列表。  
 在传出的 MDN 的默认协议中，会执行证书解析列表验证。 如果您不希望执行此验证，请确保设置了正确的 AS2-To 参与方属性，以便能够解析接收方并且能够确定参与方属性。 这样的话，将不使用提示验证证书解析列表的默认协议。 您还将需要在 AS2 参与方属性的“常规”页上禁用“检查证书吊销列表”属性。