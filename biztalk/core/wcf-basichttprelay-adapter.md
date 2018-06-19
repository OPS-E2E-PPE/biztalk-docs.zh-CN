---
title: WCF BasicHttpRelay 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22eefde6-80f5-4d45-80cf-55f743ff9d45
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72a72129a9b0ee48969d528374c2a06497aa3311
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "25975852"
---
# <a name="wcf-basichttprelay-adapter"></a>WCF-BasicHttpRelay 适配器
[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用**WCF BasicHttpRelay**适配器接收和发送通过 WCF 服务请求[BasicHttpRelayBinding 类](https://msdn.microsoft.com/library/azure/microsoft.servicebus.basichttprelaybinding.aspx)。 **Wcf-basichttprelay** 配接器會使用服務匯流排轉送端點使用 **BasicHttpRelayBinding**。  

## <a name="before-you-begin"></a>開始之前

从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，此适配器可以用于服务总线使用访问控制服务 (ACS) 或共享访问签名 (SAS) 到 athenticate。 我们建议使用服务总线进行身份验证时使用共享访问签名 (SAS)。 

当你创建了服务总线命名空间时，不自动创建 Access Control (ACS) 命名空间。 如果使用 ACS 进行身份验证，你可能需要创建一个新的 ACS 命名空间。 请参阅[SB 消息适配器](../core/sb-messaging-adapter.md)更多详细信息，包括检索 ACS 密钥值的步骤。
  
## <a name="create-the-receive-location"></a>建立接收位置
  
> [!NOTE]
>  之前完成以下过程，你必须已添加单向接收端口。 请参阅 [如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
1.  在 BizTalk Server 管理控制台中，依次展开“ [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组” 、“应用程序” ，然后展开要在其下创建接收位置的应用程序。  
  
2.  在左窗格中按一下 **[接收埠]** 節點，在右窗格中以滑鼠右鍵按一下您想與新接收位置建立關聯的接收埠，然後按一下 **[屬性]**。  
  
3.  在“接收端口属性”  对话框的左窗格中，选择“接收位置” ，然后在右窗格中单击“新建”  以创建新的接收位置。  
  
4.  在 **接收位置属性** 对话框中，在 **传输** 部分中，选择 **WCF BasicHttpRelay** 从 **类型** 下拉列表，然后单击 **配置** 若要配置接收位置的传输属性。  
  
5.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **常规** 选项卡上，配置其中托管的服务总线中继终结点，WCF BasicHttpRelay 的服务标识接收位置的终结点地址。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**地址 (URI)**|必要。 指定已部署服務匯流排轉接端點的 URI。|  
    |**终结点标识**|選擇性。 指定端點識別。 這些設定可讓端點驗證此接收位置。 在端點與接收位置之間的交握程序中，Windows Communication Foundation (WCF) 基礎結構可確保預期之服務的識別與此元素的值相符。<br /><br /> 預設為空字串。|  
  
6.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **绑定** 选项卡上配置的超时和编码相关的属性。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**打开超时 (hh:mmss)**|指定時間值，表示可供完成通道開啟作業的時間間隔。 這個值應大於或等於 **System.TimeSpan.Zero**。<br /><br /> 預設值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**发送超时时 (hh:mmss)**|指定時間值，表示可供完成傳送作業的時間間隔。 這個值應大於或等於 **System.TimeSpan.Zero**。 如果您使用要求-回應接收埠，這個值會指定完成整個互動的時間長度，即使服務傳回很大的訊息也是如此。<br /><br /> 預設值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**关闭超时 (hh:mmss)**|指定時間值，表示可供完成通道關閉作業的時間間隔。 這個值應大於或等於 **System.TimeSpan.Zero**。<br /><br /> 預設值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**收到的最大消息大小 （字节）**|以位元組為單位，指定可在網路上接收的訊息大小上限 (含標頭)。 訊息的大小受限於配置給每個訊息的記憶體數量。 您可以使用這個屬性來限制遭受拒絕服務 (DoS) 攻擊的風險程度。<br /><br /> WCF BasicHttpRelay 适配器利用 [BasicHttpRelayBinding](http://msdn.microsoft.com/library/windowsazure/microsoft.servicebus.basichttprelaybinding.aspx) 在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [BasicHttpRelayBinding.MaxBufferSize](http://msdn.microsoft.com/library/windowsazure/microsoft.servicebus.basichttprelaybinding.maxbuffersize.aspx) 属性也始终等于此属性的值。<br /><br /> 預設值：65536<br /><br /> 最大值：2147483647|  
    |**消息编码**|指定用來為 SOAP 訊息編碼的編碼器。 有效值包括下列各項：<br /><br /> -   **文本**： 使用文本消息编码器。<br />-   **Mtom**︰ 使用消息传输组织机制 1.0 (MTOM) 编码器。<br /><br /> 默认值是 **文本**。|  
    |**文本编码**|指定的字符集编码要用于在绑定上发出消息时 **消息编码** 属性设置为 **文本**。 有效值包括下列各項：<br /><br /> -   **utf 16BE (unicodeFFFE)**: Unicode BigEndian 编码。<br />-   **utf-16**: 16 位编码。<br />-   **utf-8**: 8 位编码<br /><br /> 默认值是 **utf-8**。|  
    |**最大并发调用**|指定對單一服務執行個體的並行呼叫數目。 超出上限的呼叫將排入佇列。 將這個值設定為 0 的效果與設定為 **Int32.MaxValue**相同。<br /><br /> 預設值是 200。|  
  
7.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **安全** 选项卡上，定义安全性功能 WCF BasicHttpRelay 接收位置。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**安全模式**|指定使用的安全性類型。 有效值包括下列各項：<br /><br /> -   **无**： 在传输过程不保护消息。<br />-   **传输**︰ 使用 HTTPS 传输提供安全性。 使用 HTTPS 來維護 SOAP 訊息的安全。 若要使用這個模式，您必須在 Microsoft Internet Information Services (IIS) 中設定「安全通訊端層」(SSL)。<br />-   **消息**︰ 使用 HTTP 传输的 SOAP 消息安全提供安全性。 根據預設，SOAP **Body** 會進行加密及簽署。 仅有的有效 **消息客户端凭据类型** 对于 WCF Basic 适配器是 **证书**。 這種模式需要使用 HTTP 傳輸。 使用此安全模式时，此服务证书接收位置需要通过提供 **服务证书的指纹** 属性。<br />-   **TransportWithMessageCredential**︰ 由 HTTPS 传输提供完整性、 保密性和服务身份验证。 若要使用這個模式，您必須在 Microsoft Internet Information Services (IIS) 中設定「安全通訊端層」(SSL)。<br /><br /> 預設值為 **[傳輸]**。|  
    |**消息客户端凭据类型**|指定的消息级安全选项，仅当你设置 **安全模式** 上面到 **消息** 或 **TransportWithMessageCredential**。 有效值包括下列各項：<br /><br /> -   **用户名**： 启用此接收位置需要客户端进行身份验证使用**用户名**凭据。 您必須建立對應到用戶端認證的網域或本機使用者帳戶。<br />-   **证书**︰ 客户端进行身份验证到此接收位置使用客户端证书。 用戶端 X.509 憑證的 CA 憑證鏈結必須安裝在這部電腦的「信任的根憑證授權單位」憑證存放區中，才可以向這個接收位置驗證用戶端。<br /><br /> 默认值是 **用户名**。|  
    |**算法套件**|指定的消息加密和密钥换行算法，仅当你设置 **安全模式** 到上面的模式 **消息** 或 **TransportWithMessageCredential**。 这不是适用于你设置的情况 **安全模式** 到 **无** 或 **传输**。<br /><br /> 這些演算法會對應到安全性原則語言 (WS-SecurityPolicy) 規格中所指定的演算法。 可能的值為：<br /><br /> -   **Basic128**： 使用 Aes128 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br />-   **Basic128Rsa15**︰ 对消息加密使用 Aes128，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br />-   **Basic128Sha256**︰ 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br />-   **Basic128Sha256Rsa15**︰ 对消息加密使用 Aes128，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br />-   **Basic192**︰ 使用 Aes192 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br />-   **Basic192Rsa15**︰ 对消息加密使用 Aes192，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br />-   **Basic192Sha256**︰ 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br />-   **Basic192Sha256Rsa15**︰ 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br />-   **Basic256**︰ 使用 Aes256 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br />-   **Basic256Rsa15**︰ 对消息加密使用 Aes256，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br />-   **Basic256Sha256**︰ 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br />-   **Basic256Sha256Rsa15**︰ 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br />-   **TripleDes**︰ 使用 TripleDes 加密，对消息摘要，Rsa oaep-mgf1p 对密钥包装 Sha1。<br />-   **TripleDesRsa15**︰ 使用 TripleDes 加密，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br />-   **TripleDesSha256**︰ 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br />-   **TripleDesSha256Rsa15**︰ 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> 預設值為 **[Basic256]**。|  
    |**服务证书的指纹**|針對此接收位置指定用戶端用來驗證服務之 X.509 憑證的憑證指紋。 您可以使用 **[瀏覽]** 按鈕瀏覽至 **「目前使用者」** 位置的 **My** 存放區，以選取憑證指紋。 **注意︰**  必须设置此属性，仅当你设置 **安全模式** 到上面的模式 **消息** 或 **TransportWithMessageCredential**。 这不是适用于你设置的情况 **安全模式** 到 **无** 或 **传输**。 **注意︰**  必须安装到的服务证书 **当前用户** 承载此接收位置接收处理程序的用户帐户的位置。 <br /><br /> 最小長度：00<br /><br /> 最大長度：40<br /><br /> 預設為空字串。|  
    |**中继客户端身份验证类型**|指定用於驗證接收訊息之服務匯流排轉接端點的選項。 有效值包括下列各項：<br /><br /> -   **无**： 无身份验证是必需的。<br />-   **RelayAccessToken**︰ 指定此选项可使用的安全令牌以授权与 Service Bus 中继终结点。<br /><br /> 預設值為 **RelayAccessToken**。|  
    |**启用服务发现**|選取此核取方塊，指定是否在服務登錄中發佈此服務的行為。<br /><br /> -   **显示名称**– 指定与该服务发布到服务注册表的名称。<br />-   **发现模式** – 设置在服务注册表中发布的服务的发现模式。 有关发现模式的详细信息，请参阅[ http://msdn.microsoft.com/library/microsoft.servicebus.discoverytype.aspx ](http://msdn.microsoft.com/library/microsoft.servicebus.discoverytype.aspx)。|  
    |**访问控制服务**|适用于[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]2013年。<br/><br/>如果將 **[轉接用戶端驗證類型]** 設定為 **[RelayAccessToke]**，請按一下 **[編輯]** 按鈕並指定下列詳細資料：<br /><br /> -   **访问控制服务 STS Uri** – 设置为`https://<Namespace>-sb.accesscontrol.windows.net/`，其中\<命名空间\>是服务总线命名空间。<br />-   **颁发者名称** – 指定的颁发者名称。 此值通常設定為擁有者。<br />-   **颁发者密钥** – 指定的颁发者密钥。|  
    |**服务总线连接信息** | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。<br/><br/>选择使用共享访问签名 (SAS) 或 Service Bus 命名空间的访问控制服务 (ACS)。 <br/><br/>选择一个选项，然后选择 **编辑** 输入的密钥信息︰<br/><br/> - **共享访问签名**： 输入访问密钥名称和访问密钥。 这两个值中列出 [Azure 门户](https://portal.azure.com)。<br/> - **访问控制服务**： 输入 STS URI (`https://<yourNamespace>-sb.accesscontrol.windows.net/`)，颁发者名称和颁发者密钥。 使用 Windows PowerShell 检索这些值中所述[SB 消息适配器](../core/sb-messaging-adapter.md)。 |
  
8.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **消息** 选项卡上，指定 SOAP 数据选择 **正文** 元素。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**信封--完整\<soap 信封：\>**|從內送訊息的整個 SOAP **信封** 建立 BizTalk 訊息內文部分。<br /><br /> 預設值為清除核取方塊。|  
    |**正文--内容\<soap： 正文\>元素**|使用內送訊息的 SOAP **Body** 元素內容來建立 BizTalk 訊息內文部分。 如果 **Body** 元素有一個以上的子元素，則只有第一個元素會成為 BizTalk 訊息內文部分。<br /><br /> 這是預設值。|  
    |**路径--由正文路径定位的内容**|使用 **[內文路徑運算式]** 文字方塊中的內文路徑運算式，建立 BizTalk 訊息內文部分。 內文路徑運算式會依照內送訊息 SOAP **Body** 元素的直系子元素來進行評估。<br /><br /> 預設值為清除核取方塊。|  
    |**正文路径表达式**|輸入內文路徑運算式，以識別用來建立 BizTalk 訊息內文部分的內送訊息特定部分。 這個內文路徑運算式會依照內送訊息 SOAP **Body** 元素的直系子項目來進行評估。 如果此內文路徑運算式傳回一個以上的節點，則只會為 BizTalk 訊息內文部分選擇第一個節點。 如果選取了 **[路徑 -- 內容由內文路徑定位]** 選項，就需要此屬性。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：32767<br /><br /> 預設為空字串。|  
    |**节点编码**|指定的编码，WCF BasicHttpRelay 接收适配器使用要解码识别由正文路径表达式中的节点类型 **正文路径表达式** 文本框。<br /><br /> 如果選取了 **[路徑 -- 內容由內文路徑定位]** 選項，就需要此屬性。 有效值包括下列各項：<br /><br /> -   **Base64**: Base64 编码。<br />-   **十六进制**︰ 十六进制编码。<br />-   **字符串**︰ 文本编码的 utf-8<br />-   **XML**: WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文 **正文路径表达式** 文本框。<br /><br /> 預設值是 **[XML]**。|  
    |**正文--BizTalk 响应消息正文**|使用 BizTalk 訊息內文部分建立外寄回應訊息的 SOAP **內文** 元素內容。 此屬性只適用於要求-回應接收位置。<br /><br /> 這是預設值。|  
    |**指定模板的模板--内容**|使用 [XML]  文字方塊中提供的範本來建立外寄訊息的 SOAP **內文** 元素內容。 此屬性只適用於要求-回應接收位置。<br /><br /> 預設值為清除核取方塊。|  
    |**XML**|針對外寄訊息的 SOAP **內文** 元素內容，輸入 XML 格式的範本。 如果選取了 **[範本 -- BizTalk 回應訊息本文]** 選項，就需要此屬性。 此屬性只適用於要求-回應接收位置。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：32767<br /><br /> 默认值是 **\<bts 消息正文 xmlns ="http://www.microsoft.com/schemas/bts2007"编码 ="xml"\>**。|  
    |**挂起失败的请求消息**|指定是否擱置因接收管線失敗或路由失敗而造成輸入處理失敗的要求訊息。<br /><br /> 預設值為清除核取方塊。|  
    |**错误中包括异常详细信息**|指定是否要將在錯誤發生時傳回 SOAP 錯誤以方便偵錯。<br /><br /> 預設值為清除核取方塊。|  
  
9. 按一下 **[確定]**。  
  
10. 在 **[接收位置屬性]** 對話方塊中輸入適當的值，以完成接收位置的組態，然後按一下 **[確定]** 儲存設定值。 璝惠 **接收位置属性** 对话框中，请参阅 [如何创建接收位置](../core/how-to-create-a-receive-location.md)。  

## <a name="create-the-send-port"></a>建立傳送埠

1.  在 [BizTalk 管理主控台] 中建立新的傳送埠，或按兩下現有的傳送埠進行修改。 请参阅 [如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定 **WCF BasicHttpRelay** 为 **类型** 选项 **传输** 部分 **常规** 选项卡。  
  
2.  上 **常规** 选项卡上，在 **传输** 部分中，单击 **配置** 按钮。  
  
3.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **常规** 选项卡上，指定下列各项︰  
  
    |使用|動作|  
    |--------------|----------------|  
    |**地址 (URI)**|必要。 指定在 Service Bus 上部署中继终结点的 URL。 URL 通常會使用下列格式：<br /><br /> `https://<namespace>.servicebus.windows.net/`|  
    |**终结点标识**|選擇性。 指定端點識別。 这些设置支持此发送端口对终结点进行验证。 在终结点与发送端口进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保终结点的标识与此元素的值匹配。<br /><br /> 預設值為清除核取方塊。|  
    |**動作**|指定 **SOAPAction** 传出消息的 HTTP 标头字段。 此外可以通过消息上下文属性设置此属性 **WCF。操作** 在管道或业务流程。 你可以通过两种方式指定此值︰ 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如， `http://contoso.com/Svc/Op1`- **SOAPAction** 标头为传出消息始终设置为此属性中指定的值。<br /><br /> 如果在操作映射格式，传出中设置此属性 **SOAPAction** 标头由 **BTS。操作** 上下文属性。 例如，如果此属性设置为以下 XML 格式和 **BTS。操作** 属性设置为 Op1，WCF 发送适配器使用 `http://contoso.com/Svc/Op1` 为传出 **SOAPAction** 标头。<br /><br /> `<BtsActionMapping> <Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /> <Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /> </BtsActionMapping>`<br /><br /> 如果传出消息来自于业务流程端口，动态设置业务流程实例 **BTS。操作** 与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置 **BTS。操作** 管道组件中的属性。<br /><br /> 重要事項：<br /><br /> [!INCLUDE[sb](../includes/sb-md.md)] 要求在向中继终结点发送消息时设置 SOAP 操作。<br /><br /> 最小長度：00<br /><br /> 最大長度：32767<br /><br /> 預設為空字串。|  
  
4.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **绑定** 选项卡上，配置的超时和编码属性。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**打开超时 (hh:mmss)**|指定時間值，表示可供完成通道開啟作業的時間間隔。 這個值應大於或等於 **System.TimeSpan.Zero**。<br /><br /> 預設值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**发送超时时 (hh:mmss)**|指定時間值，表示可供完成傳送作業的時間間隔。 這個值應大於或等於 **System.TimeSpan.Zero**。 如果您使用請求-回應傳送埠，這個值會指定完成整個互動的時間長度，即使服務傳回很大的訊息也是如此。<br /><br /> 預設值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**关闭超时 (hh:mmss)**|指定時間值，表示可供完成通道關閉作業的時間間隔。 此值应大于或等于 **System.TimeSpan.Zero**。<br /><br /> 預設值：00:01:00<br /><br /> 最大值：23:59:59|  
    |**收到的最大消息大小 （字节）**|以位元組為單位，指定可在網路上接收的訊息大小上限 (含標頭)。 訊息的大小受限於配置給每個訊息的記憶體數量。 您可以使用這個屬性來限制遭受拒絕服務 (DoS) 攻擊的風險程度。<br /><br /> WCF BasicHttpRelay 适配器利用 [BasicHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81086) 在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [BasicHttpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=80659) 属性也始终等于此属性的值。<br /><br /> 預設值：65536<br /><br /> 最大值：2147483647|  
    |**消息编码**|指定用來為 SOAP 訊息編碼的編碼器。 有效值包括下列各項：<br /><br /> -                         **文本**： 使用文本消息编码器。<br /><br /> -                         **Mtom**： 使用消息传输组织机制 1.0 (MTOM) 编码器。<br /><br /> 默认值︰ **文本**|  
    |**文本编码**|指定的字符集编码要用于在绑定上发出消息时 **消息编码** 属性设置为 **文本**。 有效值包括下列各項：<br /><br /> -                         **utf 16BE (unicodeFFFE)**: Unicode BigEndian 编码。<br /><br /> -                         **utf-16**: 16 位编码。<br /><br /> -                         **utf-8**: 8 位编码<br /><br /> 默认值︰ **utf-8**|  
  
5.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **安全** 选项卡上，定义 WCF BasicHttpRelay 发送端口的安全功能。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**安全模式**|指定使用的安全性類型。 有效值包括下列各項：<br /><br /> -                         **无**： 在传输过程不保护消息。<br /><br /> -                         **传输**： 使用 HTTPS 传输提供安全性。 使用 HTTPS 來維護 SOAP 訊息的安全。 此服務之 X.509 憑證的 CA 憑證鏈結必須安裝在這部電腦的「信任的根憑證授權單位」憑證存放區中，才可以使用此服務的憑證向傳送埠驗證此服務。<br /><br /> -                         **消息**： 使用 SOAP 消息安全提供安全性。 默认情况下，SOAP **正文** 元素进行加密和签名。 仅有的有效 **消息客户端凭据类型** 对于 WCF BasicHttpRelay 发送适配器是 **证书**。 這種模式需要使用 HTTP 傳輸。<br /><br /> -                         **TransportWithMessageCredential**： 由 HTTPS 传输提供完整性、 保密性和服务身份验证。 此服務之 X.509 憑證的 CA 憑證鏈結必須安裝在這部電腦的「信任的根憑證授權單位」憑證存放區中，才可以使用此服務的憑證向傳送埠驗證此服務。 傳送埠驗證是由 SOAP 訊息安全性所提供。<br /><br /> 默认值是 **无**。|  
    |**消息客户端凭据类型**|指定的消息级安全选项，仅当你设置 **安全模式** 上面到 **消息** 或 **TransportWithMessageCredential**。 有效值包括下列各項：<br /><br /> -                         **用户名**： 此发送端口进行身份验证的端点到**用户名**凭据。 对于 WCF-BasicHttpRelay 发送适配器，不支持此功能。<br /><br /> -                         **证书**： 此发送端口到终结点使用通过指定的客户端证书进行身份验证**客户端证书的指纹**属性。 此外，当使用此凭据类型，则需要通过提供服务证书 **服务证书的指纹** 属性。<br /><br /> 默认值是 **用户名**。|  
    |**算法套件**|指定訊息加密和 Key Wrap 演算法。 這些演算法會對應到安全性原則語言 (WS-SecurityPolicy) 規格中所指定的演算法。 可能的值為：<br /><br /> -                         **Basic128**： 使用 Aes128 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                         **Basic128Rsa15**： 对消息加密使用 Aes128，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> -                         **Basic128Sha256**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                         **Basic128Sha256Rsa15**： 对消息加密使用 Aes128，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> -                         **Basic192**： 使用 Aes192 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                         **Basic192Rsa15**： 对消息加密使用 Aes192，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> -                         **Basic192Sha256**： 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                         **Basic192Sha256Rsa15**： 对消息加密使用 Aes192，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> -                         **Basic256**： 使用 Aes256 加密，对消息摘要的 Sha1，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                         **Basic256Rsa15**： 对消息加密使用 Aes256，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> -                         **Basic256Sha256**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                         **Basic256Sha256Rsa15**： 对消息加密使用 Aes256，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> -                         **TripleDes**： 使用 TripleDes 加密，对消息摘要，Rsa oaep-mgf1p 对密钥包装 Sha1。<br /><br /> -                         **TripleDesRsa15**： 使用 TripleDes 加密，对消息摘要的 Sha1，对密钥包装使用 Rsa15。<br /><br /> -                         **TripleDesSha256**： 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装的 Rsa-oaep-mgf1p。<br /><br /> -                         **TripleDesSha256Rsa15**： 对消息加密使用 TripleDes，对消息摘要的 Sha256，对密钥包装使用 Rsa15。<br /><br /> 預設值為 **[Basic256]**。|  
    |**客户端证书的指纹**|指定用于向终结点验证此发送端口的 X.509 证书的指纹。 你可以通过导航到选择指纹 **我** 将存储在 **当前用户** 位置与 **浏览** 按钮。<br /><br /> 注意：<br /><br /> 你必须安装到客户端证书 **当前用户** 承载该发送处理程序的用户帐户的位置发送端口。<br /><br /> 最小長度：00<br /><br /> 最大長度：40<br /><br /> 預設為空字串。|  
    |**服务证书的指纹**|指定 X.509 憑證的指紋，用於驗證此傳送埠傳送訊息至其中的端點。 你可以选择导航到的指纹 **其他人** 将存储在 **本地计算机** 位置与 **浏览** 按钮。<br /><br /> 最小長度：00<br /><br /> 最大長度：40<br /><br /> 預設為空字串。|  
    |**用户名凭据**|指定用來傳送訊息的認證。 你可以通过单击指定属性 **编辑** 按钮。 你必须设置凭据，如果你选择 **用户名** 选项 **消息客户端凭据类型**。<br /><br /> 默认值是 **不使用单一登录**。|  
    |**使用 ACS 服务标识**|适用于[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]2013年。<br/><br/>选择此复选框，然后单击 **编辑** 并提供以下值，以使用 Service Bus 进行身份验证。<br /><br /> -                         **访问控制服务 STS Uri** – 设置为`https://<Namespace>-sb.accesscontrol.windows.net/`，其中\<命名空间\>是服务总线命名空间。<br /><br /> -                         **颁发者名称**– 指定的颁发者名称。 此值通常設定為擁有者。<br /><br /> -                         **颁发者密钥**– 指定的颁发者密钥。|  
    |**服务总线连接信息** | 新开头[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]。<br/><br/>选择使用共享访问签名 (SAS) 或 Service Bus 命名空间的访问控制服务 (ACS)。 <br/><br/>选择一个选项，然后选择 **编辑** 输入的密钥信息︰<br/><br/> - **共享访问签名**： 输入访问密钥名称和访问密钥。 这两个值中列出 [Azure 门户](https://portal.azure.com)。<br/> - **访问控制服务**： 输入 STS URI (`https://<yourNamespace>-sb.accesscontrol.windows.net/`)，颁发者名称和颁发者密钥。 使用 Windows PowerShell 检索这些值中所述[SB 消息适配器](../core/sb-messaging-adapter.md)。 |
  
6.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **代理** 选项卡上配置的代理设置 WCF BasicHttpRelay 发送端口。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**使用发送处理程序代理设置**|指定此傳送埠是否要在裝載此傳送埠的傳送處理常式中，使用 Proxy 設定。<br /><br /> 這是預設值。|  
    |**不使用代理服务器**|指出這個傳送埠是否要使用 Proxy 伺服器。<br /><br /> 預設值為清除核取方塊。|  
    |**使用代理服务器**|指示此发送端口使用中指定的代理服务器 **地址** 属性。<br /><br /> 預設值為清除核取方塊。|  
    |**地址**|指定 Proxy 伺服器的位址。 使用 **https** 或 **http** 根据安全配置的方案。 這個位址後面可以加上冒號和連接埠編號， 例如， http://127.0.0.1:8080.<br /><br /> 此属性，则需要值才 **使用代理** 选择。<br /><br /> 類型：字串<br /><br /> 最大長度：256<br /><br /> 預設為空字串。|  
    |**用户名称**|指定要用於驗證的使用者名稱。 若使用整合式驗證，則使用者名稱會包括網域，即「網域\使用者名稱」。 如果使用基本或摘要式身份验证，则用户名不包括域\\。 此属性，则需要值才 **使用代理** 选择。<br /><br /> 注意：<br /><br /> WCF-BasicHttpRelay 发送适配器对代理使用基本身份验证。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：256<br /><br /> 預設為空字串。|  
    |**密码**|指定要用於驗證的密碼。<br /><br /> 此属性，则需要值才 **使用代理** 选择。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：256<br /><br /> 預設為空字串。|  
  
7.  在 **WCF BasicHttpRelay 传输属性** 对话框中，在 **消息** 选项卡上，指定 SOAP 数据选择 **正文** 元素。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**正文--BizTalk 请求消息正文**|使用 BizTalk 消息正文部分创建的 SOAP 内容 **正文** 传出消息的元素。<br /><br /> 這是預設值。|  
    |**指定模板的模板--内容**|使用 [XML]  文字方塊中提供的範本來建立外寄訊息的 SOAP **內文** 元素內容。<br /><br /> 預設值為清除核取方塊。|  
    |**XML**|键入 SOAP 的内容的 XML 格式模板  **正文** 的传出消息的元素。 如果選取了 **[範本 -- BizTalk 回應訊息本文]** 選項，就需要此屬性。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：32767<br /><br /> 默认值为 `<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/>`。|  
    |**信封--完整\<soap 信封：\>**|從內送訊息的整個 SOAP **信封** 建立 BizTalk 訊息內文部分。 此屬性只對請求-回應連接埠有效。<br /><br /> 預設值為清除核取方塊。|  
    |**正文--内容\<soap： 正文\>元素**|使用內送訊息的 SOAP **Body** 元素內容來建立 BizTalk 訊息內文部分。 如果 **Body** 元素有一個以上的子元素，則只有第一個元素會成為 BizTalk 訊息內文部分。 此屬性只對請求-回應連接埠有效。<br /><br /> 這是預設值。|  
    |**路径--由正文路径定位的内容**|使用 **[內文路徑運算式]** 文字方塊中的內文路徑運算式，建立 BizTalk 訊息內文部分。 內文路徑運算式會依照內送訊息 SOAP **Body** 元素的直系子元素來進行評估。 此屬性只對請求-回應連接埠有效。<br /><br /> 預設值為清除核取方塊。|  
    |**正文路径表达式**|輸入內文路徑運算式，以識別用來建立 BizTalk 訊息內文部分的內送訊息特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估 **正文** 传入消息的节点。 如果此內文路徑運算式傳回一個以上的節點，則只會為 BizTalk 訊息內文部分選擇第一個節點。 如果選取了 **[路徑 -- 內容由內文路徑定位]** 選項，就需要此屬性。 此屬性只對請求-回應連接埠有效。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：32767<br /><br /> 預設為空字串。|  
    |**节点编码**|指定 WCF BasicHttpRelay 发送适配器用于解码识别由正文路径表达式中的节点的编码类型 **正文路径表达式** 文本框。 如果選取了 **[路徑 -- 內容由內文路徑定位]** 選項，就需要此屬性。 此屬性只對請求-回應連接埠有效。 有效值包括下列各項：<br /><br /> - **Base64**: Base64 编码。<br /><br /> -                         **十六进制**： 十六进制编码。<br /><br /> -                         **字符串**： 文本编码的 utf-8<br /><br /> -                         **XML**: WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**正文路径表达式**文本框。<br /><br /> 預設值是 **[XML]**。|  
    |**传播故障消息**|選取此核取方塊可將輸出處理失敗的訊息路由至訂閱應用程式 (例如另一個接收埠或協調流程排程)。 清除核取方塊以擱置失敗的訊息，並產生負值通知 (NACK)。 此屬性只對請求-回應連接埠有效。<br /><br /> 預設值為選取核取方塊。|  
  
8.  单击 **确定** 和 **确定** 再次以保存设置。  
  
## <a name="add-a-proxy-to-the-send-handler"></a>将代理添加到发送处理程序

可以将代理添加到发送端口中或发送处理程序。 如果要在发送端口添加代理，则跳过此部分。

1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理，展开**BizTalk 组**，展开**平台设置**，然后展开**适配器**.  
  
2.  选择 **WCF BasicHttpRelay**, ，然后选择发送处理程序。  
  
3.  在 **适配器处理程序属性**, 上 **常规** 选项卡上，选择 **属性**。  
  
4.  在 **代理** 选项卡上，执行以下操作。  
  
    |使用|動作|  
    |--------------|----------------|  
    |**使用代理服务器**|指示此发送处理程序是否使用代理服务器。<br /><br /> 預設值為清除核取方塊。|  
    |**地址**|指定 Proxy 伺服器的位址。 使用 **https** 或 **http** 根据安全配置的方案。 這個位址後面可以加上冒號和連接埠編號， 例如， http://127.0.0.1:8080.<br /><br /> 此属性，则需要值才 **使用代理** 选择。<br /><br /> 類型：字串<br /><br /> 最大長度：256<br /><br /> 預設為空字串。|  
    |**用户名称**|指定要用於驗證的使用者名稱。 若使用整合式或基本驗證，則使用者名稱也包括網域，即「網域\使用者名稱」。 如果使用摘要式身份验证，则用户名不包括域\\。<br /><br /> 此属性，则需要值才 **使用代理** 选择。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：256<br /><br /> 預設為空字串。|  
    |**密码**|指定要用於驗證的密碼。<br /><br /> 此属性，则需要值才 **使用代理** 选择。<br /><br /> 類型：字串<br /><br /> 最小長度：00<br /><br /> 最大長度：256<br /><br /> 預設為空字串。|  
  
5.  单击 **确定** 直到退出所有对话框。  
  
## <a name="see-also"></a>另請參閱  
[SB 消息适配器](../core/sb-messaging-adapter.md)

[使用适配器](../core/using-adapters.md)