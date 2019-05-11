---
title: 如何配置 SMTP 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [SMTP adapters], send ports
- send ports, SMTP adapters
- SMTP adapters, send ports
ms.assetid: b2291378-718d-4d1a-9d54-cd34c1b2e000
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bfbe86ac93e3fbba9a72c461b377b97d4f9d8e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341736"
---
# <a name="how-to-configure-an-smtp-send-port"></a>如何配置 SMTP 发送端口
可以以编程方式或使用 BizTalk Server 管理控制台配置 SMTP 发送端口。  
  
 **如何以编程方式配置 SMTP 发送端口**  
  
 SMTP 适配器将其配置信息存储在 BizTalk 管理数据库 （也称为配置数据库）。 配置信息存储在自定义的 XML 属性包中。 SMTP 适配器的初始化过程并在其运行时，服务器传递配置到适配器，如下所示：  
  
- 对于 SMTP 发送处理程序，配置信息传递到适配器通过调用**负载**方法**IPersistPropertyBag**接口。  
  
- 对于 SMTP 发送适配器，配置信息传递到适配器为一组属性的消息上下文。 SMTP 命名空间将这些属性组合在一起。  
  
  BizTalk 浏览器对象模型公开的 ITransportInfo 适配器配置发送端口，接口该接口包含 TransportTypeData 读/写属性。 此属性接受 SMTP 发送端口配置属性包以名称/值对 XML 字符串。 请注意，若要在 BizTalk 浏览器对象模型中设置此属性，则必须先设置上的地址属性**ITransportInfo**接口。  
  
  设置**TransportTypeData**的属性**ITransportInfo**接口不需要。 如果未设置，SMTP 发送端口将使用 SMTP 发送处理程序的默认值。 SMTP 发送适配器属性架构 bts_smtp_properties.xsd 中定义了 SMTP 发送特定于端口的属性。  
  
  如果未定义属性，它们重复发送处理程序配置属性，则使用处理程序的配置属性。 如果未定义必需的属性，将使用默认值。 如果未定义默认值，SMTP 发送处理程序事件日志中记录错误并将消息移到备份适配器。  
  
  消息上下文，可以以编程方式设置这些属性。 在 BizTalk 业务流程调度或自定义管道组件中，可以设置这些属性。 使用这些属性时，以下规则适用：  
  
- 如果该属性设置在业务流程或自定义管道组件在接收管道中，则：  
  
  -   如果将消息发送到静态发送端口，属性值将覆盖与该发送端口配置的值。  
  
  -   如果将消息发送到动态发送端口，则不会覆盖属性值。  
  
- 如果该属性设置的自定义管道组件中发送管道，则：  
  
  -   值不会被覆盖而不考虑是否将消息发送到静态或动态发送端口。  
  
  下表列出了可在 SMTP 在 BizTalk 浏览器对象模型中设置的配置属性发送位置。  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|**SMTPHost**|xs:string|用于发送消息的 SMTP 服务器。|最大长度：256|默认值：为空。<br /><br /> 默认值表示 SMTP 发送端口将使用的处理程序的配置值。|  
|**From**|xs:string|SMTP 发送端口的电子邮件地址将放置在 smtp**从**标头。|最大长度：256|默认值：为空。<br /><br /> 默认值表示 SMTP 发送端口将使用的处理程序的配置值。|  
|**CC**|xs:string|将消息的副本发送的电子邮件地址。|最大长度：1024|默认值：Empty<br /><br /> 可以列出多个电子邮件地址。|  
|**主题**|xs:string|使用者的消息的标头。|最小长度：0<br /><br /> 最大长度：256|默认值: %messageid%。|  
|**SMTPAuthenticate**|xs:int|要使用的身份验证类型。|None|有效的值：<br /><br /> -0-不进行身份验证<br />-1-基本身份验证<br />-2-进程帐户 (NTLM)<br /><br /> 默认值表示 SMTP 发送端口将使用的处理程序的配置值。 若要应用的默认值，请设置 TransportTypeData 属性时忽略属性包中的此属性。|  
|**UserName**|xs:string|若要使用的 SMTP 服务器的身份验证的用户名。|最小长度：0<br /><br /> 最大长度：256|默认值：Empty<br /><br /> 需要一个值，如果**SMTPAuthenticate**等于 1 （基本身份验证）。|  
|**密码**|xs:string|SMTP 服务器的身份验证的用户密码。|最小长度：0<br /><br /> 最大长度：256|默认值：Empty<br /><br /> 需要一个值，如果**SMTPAuthenticate**等于 1 （基本身份验证）。|  
|**ReadReceipt**|xs:boolean|通过此发送端口请求阅读的回执的消息。|None|默认值：False|  
|**DeliveryReceipt**|xs:boolean|通过此发送端口发送请求消息的送达回执。|None|默认值：False|  
|**EmailBodyText**|xs:string|指定要用于发送的电子邮件的正文文本。|最大长度：64 kb|默认值：Empty|  
|**EmailBodyTextCharset**|xs:string|指定要使用时要发送的电子邮件的正文进行编码的字符集**EmailBodyText**使用选项。 SMTP 适配器会将转换**EmailBodyText**到由指定的字符集**EmailBodyTextCharset**。|None|默认值：无。 您必须显式设置值，例如，为 utf-8。<br /><br /> 如果未设置一个值，可能会看到本主题末尾处列出的错误。|  
|**EmailBodyFile**|xs:string|指定文件的内容将用于要发送电子邮件和文件的完整路径的正文。 在运行时，此路径必须是 SMTP 适配器的主机可访问。|最大路径长度：256 个字符|默认值：Empty|  
|**EmailBodyFileCharset**|xs:string|指定要使用要发送的电子邮件的正文进行编码的字符集**EmailBodyFile**属性设置。 SMTP 适配器将该文件; 不执行任何转换该文件已必须用此字符集进行编码。 如果该文件具有字节顺序标记 (BOM)，SMTP 适配器将其删除。|None|默认值：UTF-8 (65001)|  
|**Attachments**|xs:string|指定的文件将附加到电子邮件和文件的文件的完整路径。 指定的路径必须是 SMTP 适配器的主机可以访问在运行时。|最大路径长度：256 个字符|默认值：Empty|  
|**MessagePartsAttachments**|xs:int|指定 BizTalk 消息部分如何附加到电子邮件|None|有效的值：<br /><br /> -0-无 BizTalk 消息部分用作附件。<br />-1 的 BizTalk 消息正文部分作为电子邮件附件发送。 在这种情况下， **EmailBodyFile**或**EmailBodyText**应指定属性。 如果指定了这些属性，BizTalk 消息正文部分作为电子邮件正文，而不是作为附件发送。<br />-2 的所有部分作为附件都发送。 但是，如果**EmailBodyText**或**EmailBodyFile**未指定，则 BizTalk 消息正文部分作为电子邮件正文发送和其他部分作为附件发送。<br /><br /> 默认值：0|  
|**ReplyBy**|xs:dateTime|填充**回复通过**的传出消息的指定值的标头字段。|不能在发送端口属性页上设置此属性。 可以从管道或业务流程中设置此属性。|默认值：Empty|  
  
 下面的代码显示了要用于设置这些属性的 XML 字符串的格式：  
  
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
  
 **如何使用 BizTalk Server 管理控制台配置 SMTP 发送端口**  
  
 您可以在 BizTalk Server 管理控制台中设置 SMTP 发送端口适配器变量。 如果没有为发送端口设置属性的默认发送处理程序将使用 BizTalk Server 管理控制台中设置的值。  
  
 若要在 BizTalk Server 管理控制台配置 SMTP 发送端口，请使用以下过程。  
  
### <a name="to-configure-variables-for-an-smtp-send-port"></a>若要配置 SMTP 发送端口的变量  
  
1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击某个现有发送端口以对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项，并指定**SMTP**有关**类型**选项**传输**一部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分中下, 一步**类型**，单击**配置**。  
  
3.  在中**SMTP 传输属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**若要**|必需的。 指定要将消息发送的电子邮件地址。<br /><br /> 可以指定多个地址。<br /><br /> 最大长度：256<br /><br /> 有关此属性的详细信息，请参阅[对 SMTP 到属性的限制](../core/restrictions-on-the-smtp-to-property.md)。|  
    |**CC**|指定要发送邮件的抄送电子邮件地址。<br /><br /> 可以指定多个地址。<br /><br /> 最大长度：1024|  
    |**主题**|指定消息的使用者标头。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**通知**|指定通知回执的类型。 可以选择一个或两个类型的回执。 分别是：<br /><br /> -   **阅读回执**。 在读取消息时，发送确认电子邮件。<br />-   **送达回执**。 当传递消息时，发送确认电子邮件。|  
  
4.  在中**SMTP 传输属性**对话框中，在**Compose**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**BizTalk 消息正文部分**|指定要使用 BizTalk 消息正文部分正在发送的电子邮件的正文。|  
    |**文本**|指定要用于发送的电子邮件的正文文本。 之后**文本**选择选项可以在文本框中的电子邮件正文输入文本。<br /><br /> **最大长度：** 64Kb|  
    |**文本的字符集**|-指定要使用正在发送的电子邮件正文进行编码的字符集。 此选项才可用如果**文本**选择选项。<br />-   **默认值：** UTF-8 (65001)|  
    |**File**|指定文件的内容将用于发送的电子邮件的正文，并指定文件的路径。 之后**文件**选择了您可以单击省略号 (**...**) 按钮以浏览到该文件。<br /><br /> 最大路径长度：256 个字符**注意：** 它是建议的最佳做法，若要指定可从要在生产中使用的 BizTalk Server 组中的所有 BizTalk 服务器访问的文件共享上的路径。|  
    |**文件的字符集**|指定要发送的文件的编码的字符集。 **注意：** SMTP 适配器不适用于指定编码的文件。 此选项仅适用于指定要发送的文件已编码的方式。 <br /><br /> 此选项才可用如果**文件**选择选项。<br /><br /> 默认值：UTF-8 (65001)|  
  
5.  在中**SMTP 传输属性**对话框中，在**附件**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**剩余的 BizTalk 消息部分**|指定 BizTalk 消息部分如何附加到电子邮件。<br /><br /> 选项：<br /><br /> -   **不附加任何部分**<br />-   **仅附加正文部分**<br />-   **附加所有部分**<br /><br /> 默认值：不附加任何部分。|  
    |**“添加”**|指定的文件或要附加到电子邮件的文件。 单击后**添加**可以浏览以选择一个文件并将其添加到要附加的文件列表。<br /><br /> 最大路径长度：256 个字符**注意：** 它是建议的最佳做法，若要指定可从要在生产中使用的 BizTalk Server 组中的所有 BizTalk 服务器访问的文件共享上的路径。|  
    |**删除**|从附加到电子邮件的文件列表中删除所选的文件。|  
  
6.  在中**SMTP 传输属性**对话框中，在**处理程序替代**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**SMTP 服务器名称**|指定要发送消息时使用的 SMTP 服务器的名称。<br /><br /> 最大长度：256**注意：** URI 发送端口或接收位置不能超过 256 个字符。|  
    |**发件人 （电子邮件地址）**|指定要放置在 SMTP 的电子邮件地址**从**标头。<br /><br /> 最大长度：256|  
    |**身份验证类型**|指定要对 SMTP 服务器使用身份验证的类型。<br /><br /> 选项：<br /><br /> -   **（默认值）**<br />-   **无身份验证**<br />-   **基本身份验证**<br />-   **进程帐户 (NTLM)**<br /><br /> 默认值表示 SMTP 发送端口将使用发送处理程序中指定的配置值。|  
    |**用户名**|指定要用于 SMTP 服务器的身份验证的用户名。<br /><br /> 此属性需要一个值，如果**身份验证类型**是**基本身份验证**。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**密码**|指定要使用的 SMTP 服务器的身份验证的密码。<br /><br /> 此属性需要一个值，如果**身份验证类型**是**基本身份验证**。<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
  
7.  单击**确定**并**确定**次以保存设置。  
  
## <a name="see-also"></a>请参阅  
 [配置 SMTP 适配器](../core/configuring-the-smtp-adapter.md)