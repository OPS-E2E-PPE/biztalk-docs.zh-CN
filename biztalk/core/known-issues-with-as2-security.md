---
title: AS2 安全的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b291e000-630d-49a1-8e19-f76c4dfee294
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e57a9ecd84f3087dc860a13c9e9f06d7e0859947
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380791"
---
# <a name="known-issues-with-as2-security"></a>AS2 安全的已知的问题
本主题介绍了在安全方面的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]AS2 解决方案。  
  
## <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>AS2 解码器将不验证在该主机或目标参与方配置了证书  
 只要在证书存储区配置该消息的私有证书，AS2 解码器将解密消息。 但是，AS2 解码器将不验证解密证书是在主机上配置的证书相同。 收到的消息可以使用多个证书进行加密。  
  
## <a name="storing-as2-messages-in-wire-format-can-lead-to-a-security-issue"></a>以传输格式存储 AS2 消息可能会导致安全问题  
 如果不使用证书，不建议在不可否认接收 (NRR) 数据库中以传输格式存储 AS2 消息。 执行此操作可能会导致安全问题。  
  
## <a name="messages-or-mdns-to-be-stored-in-the-nrr-database-should-be-signed"></a>应签名消息或 Mdn 存储在 NRR 数据库中  
 若要确保不可否认性的回执，必须建立身份验证和确保适用消息的完整性。 推荐的方法来这样做因此是对消息使用数字签名。 因此，如果配置 AS2 参与方属性来将消息或 Mdn 存储在不可否认数据库中，则应配置进行签名的消息或要存储的 Mdn 的 AS2 属性。  
  
## <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>BizTalk Server 将无法解密以传输格式保存，如果证书不是有效的消息  
 **症状**  
  
 BizTalk Server 不能解密入站的 AS2 消息的不可否认数据库中以传输格式保存。  
  
 **可能的原因**  
  
 所需对消息进行解密的证书已过期或被吊销。 这是更有可能发生如果自 AS2 消息保存在不可否认数据库后已经过去一段时间。 如果发生这种情况，您可能没有立即访问的有效证书的消息。  
  
 **解决方法**  
  
 获取有效的证书对消息解密。  
  
## <a name="the-inner-envelope-of-a-signed-as2-message-must-not-be-changed-after-the-signature-has-been-calculated"></a>在计算签名后不得更改签名的 AS2 消息的内层信封  
 当 AS2 消息进行签名时，签名是基于计算内层信封标头和负载。 如果在计算签名后更改了内层信封，签名将受损。 可以更改边界标头或边界标头以外的任何内容，但不得更改边界标头中的任何内容。  
  
## <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>使用相同的进程内主机实例和独立主机实例的登录名以确保可识别个人存储区  
 个人证书存储区都可用于消息处理仅在用户配置文件加载为用户的登录凭据与主机实例相关联。 个人存储区用于签名和解密证书 （用户自己的私有密钥）。 对于进程内主机实例中; 默认情况下加载用户配置文件但是，默认情况下为独立的主机实例未加载用户配置文件。 为独立的主机，可以有一个应用程序加载用户配置文件。 或者，您可以解决此问题的进程内主机实例和独立主机实例使用相同的登录名。  
  
 而不是让一个应用程序加载用户配置文件，可以创建一个空的服务来加载配置文件。 有关创建空的服务的信息，请参阅[如何：创建 Windows 服务](http://go.microsoft.com/fwlink/?LinkId=196492)。 创建服务后，打开计算机管理对话框中，打开服务的属性对话框中，单击**Log On**选项卡上，选择**此帐户**，输入用于登录名独立的主机实例，并单击**确定**。 您可以手动启动服务，从而加载登录用户的用户配置文件。  
  
## <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>证书的密钥用法属性必须匹配证书的使用  
 用于 AS2 传输的证书必须具有实现其用途所需的属性。 对于签名和签名验证证书的密钥用法属性必须为数字签名。 加密和解密，证书的密钥用法属性必须为数据加密或密钥加密。 可以通过双击证书、 单击证书对话框中，在详细信息选项卡并检查密钥用法字段来验证密钥用法属性。  
  
## <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>将传出的 MDN 验证证书解析列表，如果将 AS2-的参与方未设置属性  
 传出的 MDN 的默认协议，在执行证书解析列表验证。 如果不希望执行此验证，确认正确的 AS2-To 参与方属性设置，以便能够解析接收方并且可以确定参与方属性。 如果是这样，将不使用提示验证证书解析列表的默认协议。 您还需要禁用 AS2 参与方属性的常规页上的检查证书吊销列表属性。