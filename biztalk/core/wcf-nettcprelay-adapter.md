---
title: WCF NetTcpRelay 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f6c6afc-6aa9-4962-91e6-1fcd92744534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8ca33c5568d7a36777e8ed08adea70f476a80f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975851"
---
# <a name="wcf-nettcprelay-adapter"></a>WCF-NetTcpRelay 适配器
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用**WCF NetTcpRelay**适配器接收和发送通过 WCF 服务请求[NetTcpRelayBinding 类](https://msdn.microsoft.com/library/azure/microsoft.servicebus.nettcprelaybinding.aspx)。  

本主题列出了配置的步骤**WCF NetTcpRelay**接收位置和发送端口使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

## <a name="before-you-begin"></a>开始之前

从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，此适配器可以用于服务总线使用访问控制服务 (ACS) 或共享访问签名 (SAS) 到 athenticate。 我们建议使用服务总线进行身份验证时使用共享访问签名 (SAS)。 

当你创建了服务总线命名空间时，不自动创建 Access Control (ACS) 命名空间。 如果使用 ACS 进行身份验证，你可能需要创建一个新的 ACS 命名空间。 请参阅[SB 消息适配器](../core/sb-messaging-adapter.md)更多详细信息，包括检索 ACS 密钥值的步骤。
  
## <a name="create-the-receive-location"></a>创建接收位置
 
> [!NOTE]
>  之前完成以下过程，你必须已添加单向接收端口。 请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
1.  在 BizTalk 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开应用程序你想要创建中的接收位置。  
  
2.  在 BizTalk 管理控制台的左窗格中，单击“接收端口”  节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在“接收端口属性”  对话框的左窗格中，选择“接收位置” ，然后在右窗格中双击现有的接收位置或单击“新建”  以创建新的接收位置。  
  
4.  在“接收位置属性”  对话框的“传输”  部分中，从“类型”  下拉列表中选择“WCF-NetTcpRelay”  ，然后单击“配置”  以配置接收位置的传输属性。  
  
5.  在“WCF-NetTcpRelay 传输属性”  对话框中的“常规”  选项卡上，为 WCF-NetTcpRelay 接收位置配置终结点地址和终结点标识。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**地址 (URI)**|必需的。 指定此接收位置的完全限定 URI。 此 URI 通常采用以下格式：<br /><br /> `sb://<Namespace>.servicebus.windows.net/`|  
    |**终结点标识**|可选。 指定终结点标识。 通过这些设置，终结点可对此接收位置进行验证。 在终结点与接收位置进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保终结点的标识与此元素的值保持一致。<br /><br /> 最小长度：0<br /><br /> 最大长度：32767<br /><br /> 默认值为空字符串。|  
  
6.  在“WCF-NetTcpRelay 传输属性”  对话框中的“绑定”  选项卡上，配置超时和事务属性。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**打开超时 (hh:mmss)**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。 此值应大于或等于 **System.TimeSpan.Zero**。<br /><br /> 默认值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**发送超时时 (hh:mmss)**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 此值应大于或等于 **System.TimeSpan.Zero**。 如果使用请求-响应接收端口，则此值指定完成整个交互的时间跨度（即使客户端返回一条大消息）。<br /><br /> 默认值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**关闭超时 (hh:mmss)**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。 此值应大于或等于 **System.TimeSpan.Zero**。<br /><br /> 默认值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**收到的最大消息大小 （字节）**|指定网络上可接收的消息的最大大小（包括标头），以字节表示。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> WCF NetTcpRelay 适配器利用[NetTcpRelayBinding](https://msdn.microsoft.com/library/azure/microsoft.servicebus.nettcprelaybinding.aspx)在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [NetTcpRelayBindingBase.MaxBufferSize](https://msdn.microsoft.com/library/azure/microsoft.servicebus.nettcprelaybindingbase.maxbuffersize.aspx)属性也始终等于此属性的值。<br /><br /> 默认值：65536<br /><br /> 最大值：2147483647|  
    |**最大并发调用**|指定针对单个服务实例的并发调用的数目。 超出此限制的调用将在队列中排队。 将该值设置为 0 等效于将它设置为 **Int32.MaxValue**。<br /><br /> 默认值：200|  
  
7.  在“WCF-NetTcpRelay 传输属性”  对话框中的“安全性”  选项卡上，定义 WCF-NetTcpRelay 接收位置的安全功能。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**安全模式**|指定使用的安全类型。 有效值包括：<br /><br /> -                          **无**： 在传输过程不保护消息。<br /><br /> - **传输**： 使用传输安全提供**TLS over TCP**或**SPNego**。 可以使用此模式控制保护级别。 如果在此安全模式中为“传输客户端凭据类型”  属性选择“无”  或“证书”  ，则需要通过“服务证书 - 指纹”  属性提供此接收位置的服务证书。<br /><br /> - **消息**： 使用 SOAP 消息安全提供安全性。 默认情况下，SOAP“正文”  已加密和签名。 这种模式提供了多种功能，例如，服务凭据是否可用于带外客户端以及要使用的算法套件。 如果在此安全模式中为“消息客户端凭据类型” 属性选择“无” 、“用户名”  或“证书”  ，则必须通过“服务证书 - 指纹”  属性提供此接收位置的服务证书。<br /><br /> -                          **TransportWithMessageCredential**： 与消息安全性结合使用传输安全。 传输安全性是通过使用 **TLS over TCP** 或 **SPNego** 来提供的，可确保完整性、机密性以及服务器验证。 如果在此安全模式中为“消息客户端凭据类型” 属性选择“Windows” 、“用户名”  或“证书”  ，则需要通过“服务证书 - 指纹”  属性提供此接收位置的服务证书。<br /><br /> **注意：** 此安全模式不能与使用**传输客户端凭据类型**属性，**无**。<br /><br /> 默认值为“传输” 。|  
    |**传输保护级别**|定义 TCP 传输一级的安全性。 消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。 加密为传输过程提供了数据级保密功能。 有效值包括：<br /><br /> -                          **无**： 无保护。<br /><br /> - **登录**： 对消息进行签名。<br /><br /> - **EncryptAndSign**： 消息进行加密和签名。<br /><br /> 默认值为“EncryptAndSign” 。|  
    |**消息客户端凭据类型**|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。 仅当“安全模式”  设置为 **消息** 或 **TransportWithMessageCredential**时，才需执行此步骤。 有效值包括：<br /><br /> -                          **无**： 这允许服务与匿名客户端交互。 这表示此客户端不提供任何客户端凭据。<br /><br /> - **Windows**： 允许 SOAP 交换在已通过身份验证的 Windows 凭据上下文。 客户端凭据是使用 **WSS SOAP Message Security Kerberos Token Profile 1.0** 协议通过 SOAP“标头”  元素传递的。 你必须创建与客户端凭据对应的域或本地用户帐户。 此外，必须使用运行此接收处理程序的用户帐户名配置客户端的 **userPrincipalName** 元素。<br /><br /> - **用户名**： 客户端进行身份验证到此接收位置使用**用户名**凭据。 此凭据是使用 **WSS SOAP Message Security UsernameToken Profile 1.0** 协议通过 SOAP **Header** 元素传递的。 你必须创建与客户端凭据对应的域或本地用户帐户。<br /><br /> -**证书**： 客户端进行身份验证到此接收位置使用通过指定的客户端证书**服务证书的指纹**属性。 此凭据是使用 **WSS SOAP Message Security X509 Token Profile 1.0** 协议通过 SOAP **Header** 元素传递的。 若要验证客户端证书，必须将客户端证书的 CA 证书链安装到此计算机的“受信任根证书颁发机构”证书存储区中。 此外，你必须通过“服务证书 - 指纹”  属性为此位置提供服务证书。<br /><br /> 默认值为“Windows” 。|  
    |**算法套件**|指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。 可能的值有：<br /><br /> -                          **Basic128**： 使用 Aes128 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **Basic128Rsa15**： 对消息加密使用 Aes128，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> -                          **Basic128Sha256**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **Basic128Sha256Rsa15**： 对消息加密使用 Aes128，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> - **Basic192**： 使用 Aes192 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> - **Basic192Rsa15**： 对消息加密使用 Aes192，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> -                          **Basic192Sha256**： 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **Basic192Sha256Rsa15**： 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> - **Basic256**： 使用 Aes256 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **Basic256Rsa15**： 对消息加密使用 Aes256，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> - **Basic256Sha256**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> - **Basic256Sha256Rsa15**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> - **TripleDes**： 使用 TripleDes 加密，对消息摘要，Rsa oaep-mgf1p 对密钥包装 Sha1。<br /><br /> -                          **TripleDesRsa15**： 使用 TripleDes 加密，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> - **TripleDesSha256**： 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **TripleDesSha256Rsa15**： 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> 默认值为“Basic256” 。|  
    |**服务证书的指纹**|为此接收位置指定 X.509 证书的指纹，客户端利用该指纹验证服务。 使用“浏览”  按钮，导航到“当前用户”  位置中“我的”  存储，然后即可选择指纹。<br /><br /> **注意：** 必须安装到的服务证书**当前用户**承载此接收位置接收处理程序的用户帐户的位置。<br /><br /> 最小长度：0<br /><br /> 最大长度：40<br /><br /> 默认值为空字符串。|  
    |**中继客户端身份验证类型**|指定对 Service Bus 中继终结点（可通过其接收消息）进行身份验证的选项。 有效值包括：<br /><br /> -                          **无**： 无身份验证是必需的。<br /><br /> -                          **RelayAccessToken**： 指定此选项可使用的安全令牌以授权与 Service Bus 中继终结点。<br /><br /> 默认值为“RelayAccessToken” 。|  
    |**启用服务发现**|选中此复选框可指定是否在服务注册表中发布服务的行为。<br /><br /> -                          **显示名称**– 指定与该服务发布到服务注册表的名称。<br /><br /> - **发现模式**– 设置在服务注册表中发布的服务的发现模式。 有关发现模式的详细信息，请参阅[https://msdn.microsoft.com/library/microsoft.servicebus.discoverytype.aspx](https://msdn.microsoft.com/library/microsoft.servicebus.discoverytype.aspx)。|  
    |**访问控制服务**|适用于[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]2013年。<br/><br/>如果将“中继客户端身份验证类型”  设置为“RelayAccessToken” ，请单击“编辑”  按钮，然后指定以下详细信息：<br /><br /> - **访问控制服务 STS Uri** – 设置为`https://<Namespace>-sb.accesscontrol.windows.net/`，其中\<命名空间\>是服务总线命名空间。<br /><br /> - **颁发者名称**– 指定的颁发者名称。 通常将此值设置为 owner。<br /><br /> - **颁发者密钥**– 指定的颁发者密钥。<br /><br /> |  
        |**服务总线连接信息** | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。<br/><br/>选择使用共享访问签名 (SAS) 或 Service Bus 命名空间的访问控制服务 (ACS)。 <br/><br/>选择一个选项，然后选择**编辑**输入的密钥信息：<br/><br/> - **共享访问签名**： 输入访问密钥名称和访问密钥。 这两个值中列出[Azure 门户](https://portal.azure.com)。<br/> - **访问控制服务**： 输入 STS URI (`https://<yourNamespace>-sb.accesscontrol.windows.net/`)，颁发者名称和颁发者密钥。 使用 Windows PowerShell 检索这些值中所述[SB 消息适配器](../core/sb-messaging-adapter.md)。 |
  
8.  在“WCF-NetTcpRelay 传输属性”  对话框中的“消息”  选项卡上，为 SOAP **Body** 元素指定数据选择。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**信封--完整\<soap 信封：\>**|从传入消息的整个 SOAP **Envelope** 创建 BizTalk 消息正文部分。<br /><br /> 默认值为清除此复选框。|  
    |**正文--内容\<soap： 正文\>元素**|使用传入消息的 SOAP **Body** 元素的内容创建 BizTalk 消息正文部分。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。<br /><br /> 这是默认设置。|  
    |**路径--由正文路径定位的内容**|使用“正文路径表达式”  文本框中的正文路径表达式创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。<br /><br /> 默认值为清除此复选框。|  
    |**正文路径表达式**|键入正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算此正文路径表达式。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 如果选择了“路径 -- 按正文路径定位内容”  选项，则此属性是必需的。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：32767<br /><br /> 默认值为空字符串。|  
    |**节点编码**|指定 WCF-NetTcpRelay 接收适配器为“正文路径表达式”  文本框中正文路径表达式标识的节点进行解码所采用的编码类型。 如果选择了“路径 -- 按正文路径定位内容”  选项，则此属性是必需的。 有效值包括：<br /><br /> - **Base64**: Base64 编码。<br /><br /> - **十六进制**： 十六进制编码。<br /><br /> -                          **字符串**： 文本编码的 utf-8<br /><br /> -                          **XML**: WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**正文路径表达式**文本框。<br /><br /> 默认值为“XML” 。|  
    |**正文--BizTalk 响应消息正文**|使用 BizTalk 消息正文部分创建传出响应消息的 SOAP **Body** 元素的内容。 此属性仅对请求响应接收位置有效。<br /><br /> 这是默认设置。|  
    |**指定模板的模板--内容**|使用在“XML”  文本框中提供的模板创建传出消息的 SOAP **Body** 元素的内容。 此属性仅对请求响应接收位置有效。<br /><br /> 默认值为清除此复选框。|  
    |**XML**|为传出消息的 SOAP **Body** 元素的内容键入 XML 格式的模板。 如果选择了“模板 -- BizTalk 响应消息正文”  选项，则此属性是必需的。 此属性仅对请求响应接收位置有效。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：32767<br /><br /> 默认值是 **\<bts 消息正文 xmlns ="http://www.microsoft.com/schemas/bts2007"编码 ="xml"\>**。|
    |**挂起失败的请求消息**|指定是否将由于接收管道故障或路由故障而导致入站处理失败的请求消息挂起。<br /><br /> 默认值为清除此复选框。|  
    |**错误中包括异常详细信息**|指定发生错误时是否返回 SOAP 错误以方便进行调试。<br /><br /> 默认值为清除此复选框。|  
  
9. 单击 **“确定”**。  
  
10. 在“接收位置属性”  对话框中输入相应的值，完成对接收位置的配置，然后单击“确定”  保存设置。 璝惠**接收位置属性**对话框中，请参阅[如何创建接收位置](../core/how-to-create-a-receive-location.md)。 
  
## <a name="create-the-send-port"></a>创建发送端口
  
1.  在 BizTalk 管理控制台中，创建一个新的发送端口或双击某个现有发送端口以对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**WCF NetTcpRelay**为**类型**选项**传输**部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分中，单击**配置**按钮。  
  
3.  在**WCF NetTcpRelay 传输属性**对话框中，在**常规**选项卡上，指定下列各项：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**地址 (URI)**|必需的。 指定发送端口的完全限定 URI。 此 URI 通常采用以下格式：<br /><br /> `sb://<Namespace>.servicebus.windows.net/`<br /><br /> 最大长度： 255<br /><br /> 默认值： net.tcp://localhost/|  
    |**终结点标识**|可选。 指定此发送端口将消息发送到的终结点的标识。 这些设置，此发送端口进行身份验证终结点。 在终结点和发送端口之间握手过程中，Windows Communication Foundation (WCF) 基础结构将确保终结点的标识与此元素的值匹配。 可以为指定的值**终结点标识**属性而异的安全配置。<br /><br /> 默认值为清除此复选框。|  
    |**操作**|指定**SOAP 操作**传出消息的标头字段。 此外可以通过消息上下文属性设置此属性**WCF。操作**在管道或业务流程。 你可以通过两种方式指定此值： 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如，http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。<br /><br /> 如果在操作映射格式，传出中设置此属性**SOAPAction**标头由**BTS。操作**上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，WCF 发送适配器`uses http://contoso.com/Svc/Op1`为传出**SOAPAction**标头。<br /><br /> `<BtsActionMapping> <Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /> <Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /> </BtsActionMapping>`<br /><br /> 如果传出消息来自的业务流程端口时，动态设置业务流程实例**BTS。操作**与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置**BTS。操作**管道组件中的属性。<br /><br /> 最小长度：0<br /><br /> 最大长度：32767<br /><br /> 默认值为空字符串。|  
  
4.  在“WCF-NetTcpRelay 传输属性”  对话框中的“绑定”  选项卡上，配置超时和事务属性。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**打开超时 (hh:mmss)**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。 此值应大于或等于 **System.TimeSpan.Zero**。<br /><br /> 默认值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**发送超时时 (hh:mmss)**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 此值应大于或等于 **System.TimeSpan.Zero**。 如果使用要求-响应发送端口，则此值指定完成整个交互的时间跨度（即使服务返回一条大消息）。<br /><br /> 默认值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**关闭超时 (hh:mmss)**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。 此值应大于或等于 **System.TimeSpan.Zero**。<br /><br /> 默认值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**收到的最大消息大小 （字节）**|指定网络上可接收的消息的最大大小（包括标头），以字节表示。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> WCF NetTcpRelay 适配器利用[NetTcpRelayBinding](https://msdn.microsoft.com/library/azure/microsoft.servicebus.nettcprelaybinding.aspx)在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [NetTcpRelayBindingBase.MaxBufferSize](https://msdn.microsoft.com/library/azure/microsoft.servicebus.nettcprelaybindingbase.maxbuffersize.aspx)属性也始终等于此属性的值。<br /><br /> 默认值：65536<br /><br /> 最大值：2147483647|  
  
5.  在**WCF NetTcpRelay 传输属性**对话框中，在**安全**选项卡上，定义 WCF NetTcpRelay 发送端口的安全功能。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**安全模式**|指定使用的安全类型。 有效值包括：<br /><br /> - **无**： 在传输过程不保护消息。<br /><br /> - **传输**： 使用传输安全提供**TLS over TCP**或**SPNego**。 可以使用此模式控制保护级别。<br /><br /> -                          **消息**： 使用 SOAP 消息安全提供安全性。 默认情况下，SOAP“正文”  已加密和签名。 这种模式提供了多种功能，例如，服务凭据是否可用于带外客户端以及要使用的算法套件。<br /><br /> - **TransportWithMessageCredential**： 与消息安全性结合使用传输安全。 通过提供传输安全**TLS over TCP**，或**SPNego**，并确保完整性、 保密性和服务器身份验证。 SOAP 消息安全性提供客户端验证。 若要使用此模式，必须将服务的 X.509 证书的 CA 证书链安装到此计算机的“受信任根证书颁发机构”证书存储区中，以便向发送端口验证该服务。<br /><br /> **注意：** 此安全模式不能与使用**传输客户端凭据类型**属性，**无**。<br /><br /> 默认值为“传输” 。|  
    |**传输保护级别**|定义 TCP 传输一级的安全性。 消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。 加密为传输过程提供了数据级保密功能。 有效值包括：<br /><br /> -                          **无**： 无保护。<br /><br /> - **登录**： 对消息进行签名。<br /><br /> -                          **EncryptAndSign**： 消息进行加密和签名。<br /><br /> 默认值为“EncryptAndSign” 。|  
    |**消息客户端凭据类型**|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。 仅当“安全模式”  设置为 **消息** 或 **TransportWithMessageCredential**时，才需执行此步骤。 有效值包括：<br /><br /> - **无**： 这允许服务与匿名客户端交互。 这表示此发送端口不提供任何客户端凭据。 必须将服务 X.509 证书的 CA 证书链安装到此计算机的“受信任根证书颁发机构”证书存储区中，以便向发送端口验证该服务。<br /><br /> -                          **Windows**： 允许 SOAP 交换在已通过身份验证的 Windows 凭据上下文。 服务使用运行此发送端口的用户帐户来验证此发送端口。 客户端凭据是使用 **WSS SOAP Message Security Kerberos Token Profile 1.0** 协议通过 SOAP“标头”  元素传递的。 你必须配置**用户主体名称**属性设置为使用运行目标服务的用户帐户名称**标识编辑器**对话框。<br /><br /> - **用户名**： 此发送端口与服务进行身份验证**用户名**凭据。 此凭据是使用 **WSS SOAP Message Security UsernameToken Profile 1.0** 协议通过 SOAP **Header** 元素传递的。 此选项需要配置**客户端凭据**属性。 必须将服务 X.509 证书的 CA 证书链安装到此计算机的“受信任根证书颁发机构”证书存储区中，以便向发送端口验证该服务。<br /><br /> - **证书**： 此发送端口使用通过指定的客户端证书对服务进行身份验证**客户端证书的指纹**属性。 此凭据是使用 **WSS SOAP Message Security X509 Token Profile 1.0** 协议通过 SOAP **Header** 元素传递的。 必须将服务 X.509 证书的 CA 证书链安装到此计算机的“受信任根证书颁发机构”证书存储区中，以便向发送端口验证该服务。<br /><br /> 默认值为“Windows” 。|  
    |**算法套件**|指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。 可能的值有：<br /><br /> - **Basic128**： 使用 Aes128 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> - **Basic128Rsa15**： 对消息加密使用 Aes128，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> -                          **Basic128Sha256**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **Basic128Sha256Rsa15**： 对消息加密使用 Aes128，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> - **Basic192**： 使用 Aes192 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **Basic192Rsa15**： 对消息加密使用 Aes192，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> - **Basic192Sha256**： 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **Basic192Sha256Rsa15**： 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> -                          **Basic256**： 使用 Aes256 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> - **Basic256Rsa15**： 对消息加密使用 Aes256，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> - **Basic256Sha256**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> - **Basic256Sha256Rsa15**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> -                          **TripleDes**： 使用 TripleDes 加密，对消息摘要，Rsa oaep-mgf1p 对密钥包装 Sha1。<br /><br /> - **TripleDesRsa15**： 使用 TripleDes 加密，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> - **TripleDesSha256**： 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                          **TripleDesSha256Rsa15**： 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> 默认值为“Basic256” 。|  
    |**客户端证书的指纹**|指定向服务验证此发送端口时使用的 X.509 证书的指纹。 使用“浏览”  按钮，导航到“当前用户”  位置中“我的”  存储，然后即可选择指纹。<br /><br /> **注意：** 必须安装到客户端证书**当前用户**承载该发送处理程序的用户帐户的位置发送端口。<br /><br /> 最小长度：0<br /><br /> 最大长度：40<br /><br /> 默认值为空字符串。|  
    |**用户名凭据**|指定用于发送消息时使用的凭据**用户名**为**消息客户端凭据类型**属性。 你可以通过单击指定属性**编辑凭据**按钮。<br /><br /> 默认值是**不使用单一登录**。|  
    |**使用 ACS 服务标识**|适用于[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]2013年。<br/><br/>选择此复选框，然后单击**编辑**并提供以下值，以使用 Service Bus 进行身份验证。<br /><br /> - **访问控制服务 STS Uri** – 设置为`https://<Namespace>-sb.accesscontrol.windows.net/`，其中\<命名空间\>是服务总线命名空间。<br /><br /> - **颁发者名称**– 指定的颁发者名称。 通常将此值设置为 owner。<br /><br /> - **颁发者密钥**– 指定的颁发者密钥。|  
    |**服务总线连接信息** | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。<br/><br/>选择使用共享访问签名 (SAS) 或 Service Bus 命名空间的访问控制服务 (ACS)。 <br/><br/>选择一个选项，然后选择**编辑**输入的密钥信息：<br/><br/> - **共享访问签名**： 输入访问密钥名称和访问密钥。 这两个值中列出[Azure 门户](https://portal.azure.com)。<br/> - **访问控制服务**： 输入 STS URI (`https://<yourNamespace>-sb.accesscontrol.windows.net/`)，颁发者名称和颁发者密钥。 使用 Windows PowerShell 检索这些值中所述[SB 消息适配器](../core/sb-messaging-adapter.md)。 |
  
6.  在“WCF-NetTcpRelay 传输属性”  对话框中的“消息”  选项卡上，为 SOAP **Body** 元素指定数据选择。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**正文--BizTalk 请求消息正文**|使用 BizTalk 消息正文部分创建的 SOAP 内容**正文**传出消息的元素。<br /><br /> 这是默认设置。|  
    |**指定模板的模板--内容**|使用在“XML”  文本框中提供的模板创建传出消息的 SOAP **Body** 元素的内容。<br /><br /> 默认值为清除此复选框。|  
    |**XML**|为传出消息的 SOAP **Body** 元素的内容键入 XML 格式的模板。 如果选择了“模板 -- BizTalk 响应消息正文”  选项，则此属性是必需的。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：32767<br /><br /> 默认值是 < bts 消息正文<br /><br /> xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/>|  
    |**信封--完整\<soap 信封：\>**|从整个 SOAP 创建 BizTalk 消息正文部分**信封**的传入。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为清除此复选框。|  
    |**正文--内容\<soap： 正文\>元素**|使用传入消息的 SOAP **Body** 元素的内容创建 BizTalk 消息正文部分。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。 此属性仅对要求-响应端口有效。<br /><br /> 这是默认设置。|  
    |**路径--由正文路径定位的内容**|使用“正文路径表达式”  文本框中的正文路径表达式创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为清除此复选框。|  
    |**正文路径表达式**|键入正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 如果选择了“路径 -- 按正文路径定位内容”  选项，则此属性是必需的。 此属性仅对要求-响应端口有效。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：32767<br /><br /> 默认值为空字符串。|  
    |**节点编码**|指定 WCF NetTcpRelay 发送适配器用于解码识别由正文路径表达式中的节点的编码类型**正文路径表达式**文本框。 如果选择了“路径 -- 按正文路径定位内容”  选项，则此属性是必需的。 此属性仅对要求-响应端口有效。 有效值包括：<br /><br /> -                          **Base64**: Base64 编码。<br /><br /> - **十六进制**： 十六进制编码。<br /><br /> - **字符串**： 文本编码的 utf-8<br /><br /> -                          **XML**: WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**正文路径表达式**文本框。<br /><br /> 默认值为“XML” 。|  
    |**传播故障消息**|选中此复选框可将无法执行出站处理的消息路由至某个订阅应用程序（例如其他接收端口或业务流程计划）。 清除此复选框可挂起失败的消息，并生成一个否定确认 (NACK)。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为选中此复选框。|  
  
7.  单击**确定**和**确定**再次以保存设置。  
  
## <a name="set-maxconnections-in-the-handler"></a>处理程序中的组 MaxConnections

1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**.  
  
2.  在适配器列表中，选择**WCF NetTcpRelay**，然后选择发送或接收处理程序。  
  
3.  在**适配器处理程序属性**上**常规**选项卡上，选择**属性**。  
  
4.  在**处理程序**选项卡：   
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**最大连接数**|指定最大数量 （接收处理程序） 的入站的连接的连接池中缓存的每个终结点的出站连接 （发送处理程序）。 这将限制为每个唯一的远程终结点缓存的连接数。 对于每个唯一的远程终结点，你应该将此值设置为一个大于最大期望缓存连接数的值。 如果活动连接数超出此最大值，则服务可能表现为在此发送处理程序下运行的 WCF NetTcpRelay 发送端口。<br /><br /> 默认值为 10。|  
  
5.  单击“确定”保存更改。  

## <a name="see-also"></a>另请参阅
[SB 消息适配器](../core/sb-messaging-adapter.md)

[使用适配器](../core/using-adapters.md)