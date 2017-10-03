---
title: "如何配置一个 SMTP 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], send ports
- send ports, SMTP adapters
- SMTP adapters, send ports
ms.assetid: b2291378-718d-4d1a-9d54-cd34c1b2e000
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69f61af2803272c34e3f4e8a0ac4dccfb151561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-smtp-send-port"></a>如何配置一个 SMTP 发送端口
可以通过编程方式或使用 BizTalk Server 管理控制台来配置 SMTP 发送端口。  
  
 **如何以编程方式配置 SMTP 发送端口**  
  
 SMTP 适配器将其配置信息存储在 BizTalk 管理数据库（也称为配置数据库）中。 配置信息存储在自定义的 XML 属性包中。 在 SMTP 适配器的初始化过程中及其运行时期间，服务器将按如下所述将配置传递到适配器：  
  
-   为 SMTP 发送处理程序中，配置信息将传递给适配器通过调用**负载**方法**IPersistPropertyBag**接口。  
  
-   对于 SMTP 发送适配器，将配置信息作为消息上下文上的一组属性传递到适配器。 SMTP 命名空间将这些属性组合在一起。  
  
 BizTalk 浏览器对象模型可公开发送端口的 ITransportInfo 适配器配置接口，该接口包含 TransportTypeData 读/写属性。 此属性以名称-值对 XML 字符串的形式接受 SMTP 发送端口配置属性包。 请注意，若要在 BizTalk 资源管理器对象模型中设置此属性，它必须首先设置上的地址属性**ITransportInfo**接口。  
  
 设置**TransportTypeData**属性**ITransportInfo**界面不是必需。 如果未设置此属性，SMTP 发送端口将使用 SMTP 发送处理程序的默认值。 特定于 SMTP 发送端口的属性在 SMTP 发送适配器属性架构 bts_smtp_properties.xsd 中进行定义。  
  
 如果未定义的属性与发送处理程序配置属性重复，则使用该处理程序的配置属性。 如果未定义必需的属性，则使用默认值。 如果未定义默认值，则 SMTP 发送处理程序将在事件日志中记录错误，然后将消息移到备份适配器。  
  
 可以通过编程方式在消息上下文中设置这些属性。 可以在 BizTalk 业务流程调度或自定义管道组件中设置这些属性。 使用这些属性时，以下规则适用：  
  
-   如果在业务流程或接收管道的自定义管道组件中设置属性，则：  
  
    -   如果将消息发送到静态发送端口，则将使用为该发送端口配置的值覆盖属性值。  
  
    -   如果将消息发送到动态发送端口，则不会覆盖属性值。  
  
-   如果在发送管道的自定义管道组件中设置属性，则：  
  
    -   无论将消息发送到静态发送端口还是动态发送端口，都不会覆盖属性值。  
  
 下表列出了可在 SMTP 发送位置的 BizTalk 浏览器对象模型中设置的配置属性：  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|**SMTPHost**|xs:string|用于发送消息的 SMTP 服务器。|最大长度：256|默认值： 空。<br /><br /> 默认值表示 SMTP 发送端口将使用处理程序的配置值。|  
|**From**|xs:string|SMTP 发送端口的电子邮件地址将置于 SMTP**从**标头。|最大长度：256|默认值： 空。<br /><br /> 默认值表示 SMTP 发送端口将使用处理程序的配置值。|  
|**抄送**|xs:string|将向其发送邮件副本的电子邮件地址。|最大长度： 1024年|默认值： 空<br /><br /> 可以列出多个电子邮件地址。|  
|**主题**|xs:string|邮件的主题。|最小长度：0<br /><br /> 最大长度：256|默认值: %messageid%。|  
|**SMTPAuthenticate**|xs:int|要使用的验证类型。|无|有效值：<br /><br /> -0-无身份验证<br />-1-基本身份验证<br />-2-进程帐户 (NTLM)<br /><br /> 默认值表示 SMTP 发送端口将使用处理程序的配置值。 若要应用默认值，请在设置 TransportTypeData 属性时忽略属性包中的此属性。|  
|**UserName**|xs:string|用于对 SMTP 服务器进行验证的用户名。|最小长度：0<br /><br /> 最大长度：256|默认值： 空<br /><br /> 需要一个值，如果**SMTPAuthenticate**等于 1 （基本身份验证）。|  
|**密码**|xs:string|用于对 SMTP 服务器进行验证的用户密码。|最小长度：0<br /><br /> 最大长度：256|默认值： 空<br /><br /> 需要一个值，如果**SMTPAuthenticate**等于 1 （基本身份验证）。|  
|**ReadReceipt**|xs:boolean|为通过此发送端口发送的消息请求阅读回执。|无|默认值：False|  
|**DeliveryReceipt**|xs:boolean|为通过此发送端口发送的消息请求送达回执。|无|默认值：False|  
|**EmailBodyText**|xs:string|指定将用于要发送的电子邮件正文的文本。|最大长度： 64 kb|默认值： 空|  
|**EmailBodyTextCharset**|xs:string|指定要用于编码时要发送电子邮件的正文的字符集**EmailBodyText**使用选项。 SMTP 适配器会将转换**EmailBodyText**为设置指定的字符**EmailBodyTextCharset**。|无|默认值： 无。 必须明确设置该值，如设为 UTF-8。<br /><br /> 如果不设置值，可能会出现本主题结尾处列出的错误。|  
|**EmailBodyFile**|xs:string|指定将使用一个文件的内容作为要发送的电子邮件的正文，并指定该文件的完整路径。 在运行时，SMTP 适配器所在的主机必须能够访问此路径。|最大路径长度：256 个字符|默认值： 空|  
|**EmailBodyFileCharset**|xs:string|指定要用于编码如果正在发送的电子邮件正文的字符集**EmailBodyFile**属性设置。 SMTP 适配器将不对该文件执行任何转换；该文件必须已用此字符集进行编码。 如果该文件具有字节顺序标记 (BOM)，则 SMTP 适配器将删除该标记。|无|默认值：UTF-8 (65001)|  
|**Attachments**|xs:string|指定将向电子邮件附加一个或多个文件，并指定所附加的文件的完整路径。 在运行时，SMTP 适配器所在的主机必须能够访问所指定的路径。|最大路径长度：256 个字符|默认值： 空|  
|**MessagePartsAttachments**|xs:int|指定 BizTalk 消息部分如何附加到电子邮件|无|有效值：<br /><br /> -0-否 BizTalk 消息部分将用作附件。<br />-1-BizTalk 消息正文部分作为电子邮件附件发送。 在这种情况下， **EmailBodyFile**或**EmailBodyText**应指定属性。 如果未指定这两个属性，则将 BizTalk 消息正文部分作为电子邮件正文发送，而不是作为附件发送。<br />-2-所有部分将作为附件都发送。 但是，如果**EmailBodyText**或**EmailBodyFile**未指定，则作为电子邮件正文发送的 BizTalk 消息正文部分和其他部分将作为附件发送。<br /><br /> 默认值： 0|  
|**ReplyBy**|xs:dateTime|填充**答复通过**中指定的值的传出消息的标头字段。|不能在发送端口属性页上设置此属性。 可以在管道或业务流程中设置此属性。|默认值： 空|  
  
 以下代码显示了用于设置这些属性的 XML 字符串的格式：  
  
```  
<CustomProps>  
   <DeliveryReceipt vt="11">-1</DeliveryReceipt  
   <SMTPHost vt="8">sfdsadf</SMTPHost>  
   <Subject vt="8">Some subject</Subject>  
   <From vt="8">username@domain.com</From>  
   <SMTPAuthenticate vt="19">2</SMTPAuthenticate>  
   <ReadReceipt vt="11">-1</ReadReceipt>  
</CustomProps>  
```  
  
 **如何使用 BizTalk Server 管理控制台中配置 SMTP 发送端口**  
  
 可以在 BizTalk Server 管理控制台中设置 SMTP 发送端口适配器变量。 如果未设置发送端口的属性，则使用在 BizTalk Server 管理控制台中设置的默认发送处理程序值。  
  
 若要使用 BizTalk Server 管理控制台配置 SMTP 发送端口，请使用以下过程：  
  
### <a name="to-configure-variables-for-an-smtp-send-port"></a>配置 SMTP 发送端口的变量  
  
1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击现有发送端口以对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**SMTP**为**类型**选项**传输**部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分，旁边**类型**，单击**配置**。  
  
3.  在**SMTP 传输属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**若要**|必需的。 指定邮件要发送到的电子邮件地址。<br /><br /> 您可以指定多个地址。<br /><br /> 最大长度：256<br /><br /> 有关此属性的详细信息，请参阅[SMTP To 属性限制](../core/restrictions-on-the-smtp-to-property.md)。|  
    |**抄送**|指定邮件的抄送副本要发送到的电子邮件地址。<br /><br /> 您可以指定多个地址。<br /><br /> 最大长度： 1024年|  
    |**主题**|指定邮件的主题。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**通知**|指定通知回执的类型。 您既可以选择下列一种类型的回执，也可以同时选择两种类型的回执。 它们分别是：<br /><br /> -   **阅读回执**。 在阅读邮件后发送确认电子邮件。<br />-   **送达回执**。 在送达邮件后发送确认电子邮件。|  
  
4.  在**SMTP 传输属性**对话框中，在**Compose**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**BizTalk 消息正文部分**|指定将使用 BizTalk 消息正文部分作为要发送的电子邮件的正文。|  
    |**Text**|指定将用于要发送的电子邮件正文的文本。 后**文本**选项可以在文本框中的电子邮件正文输入的文本。<br /><br /> **最大长度：** 64 Kb|  
    |**文本的字符集**|-指定要用于编码正在发送的电子邮件正文的字符集。 此选项才可用如果**文本**选项。<br />-   **默认值：** utf-8 (65001)|  
    |**文件**|指定将使用一个文件的内容作为要发送的电子邮件的正文，并指定该文件的路径。 后**文件**选项可以单击省略号 (**...**) 按钮以浏览到该文件。<br /><br /> 最大路径长度： 256 个字符**注意：**它是建议的最佳做法来从要在生产中使用的 BizTalk Server 组中的所有 BizTalk 服务器可访问的文件共享上指定的路径。|  
    |**文件的字符集**|指定要发送的文件的字符集编码。 **注意：** SMTP 适配器不适用于指定编码的文件。 此选项只用于指定要发送的文件现有的编码方式。 <br /><br /> 此选项才可用如果**文件**选项。<br /><br /> 默认值：UTF-8 (65001)|  
  
5.  在**SMTP 传输属性**对话框中，在**附件**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**剩余 BizTalk 消息部分**|指定 BizTalk 消息部分如何附加到电子邮件。<br /><br /> 选项：<br /><br /> -   **不附加任何部分**<br />-   **仅附加正文部分**<br />-   **将附加所有部分**<br /><br /> 默认值： 不附加任何部分。|  
    |**添加**|指定要附加到电子邮件的一个或多个文件。 单击后**添加**你可以浏览以选择文件并将其添加到要附加的文件列表。<br /><br /> 最大路径长度： 256 个字符**注意：**它是建议的最佳做法来从要在生产中使用的 BizTalk Server 组中的所有 BizTalk 服务器可访问的文件共享上指定的路径。|  
    |**删除**|从要附加到电子邮件的文件列表中删除所选文件。|  
  
6.  在**SMTP 传输属性**对话框中，在**处理程序重写**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**SMTP 服务器名称**|指定发送邮件时要使用的 SMTP 服务器的名称。<br /><br /> 最大长度： 256**注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**发件人 （电子邮件地址）**|指定要放入 SMTP 的电子邮件地址**从**标头。<br /><br /> 最大长度：256|  
    |**身份验证类型**|指定对 SMTP 服务器使用的验证类型。<br /><br /> 选项：<br /><br /> -   **（默认值）**<br />-   **无身份验证**<br />-   **基本身份验证**<br />-   **进程帐户 (NTLM)**<br /><br /> 默认值指示 SMTP 发送端口将使用发送处理程序中指定的配置值。|  
    |**用户名**|指定对 SMTP 服务器进行验证所使用的用户名。<br /><br /> 此属性需要一个值，如果**身份验证类型**是**基本身份验证**。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**密码**|指定对 SMTP 服务器进行验证所使用的密码。<br /><br /> 此属性需要一个值，如果**身份验证类型**是**基本身份验证**。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
  
7.  单击**确定**和**确定**再次以保存设置。  
  
## <a name="see-also"></a>另请参阅  
 [配置 SMTP 适配器](../core/configuring-the-smtp-adapter.md)