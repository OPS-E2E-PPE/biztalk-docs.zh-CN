---
title: 通过 FILE 发送端口发送 AS2 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8c5ce9ff-fd73-4d5f-9b16-387c1e520c3a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184a6a1b6a0111dffaf9096e23e60945d8310ecf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399059"
---
# <a name="sending-an-as2-message-over-a-file-send-port"></a>通过 FILE 发送端口发送 AS2 消息
AS2 消息通常是通过 HTTP 适配器发送的。 然而，如果创建了自定义组件，则可以通过 FILE 适配器发送 AS2 消息。 本主题介绍了这种解决方案的工作原理并提供了该解决方案的示例代码。  
  
 通过 HTTP 发送 AS2 消息时，发送管道中的 AS2 编码器会使用发送消息时所需的 HTTP（和 AS2）标头来填充 `HTTP.UserHttpHeaders` 上下文属性。 它将从现有 `HTTP.UserHttpHeaders` 上下文属性、单独的上下文属性或协议属性（按该优先级顺序）中获取这些标头。 发送端口中的 HTTP 适配器会将标头写入消息，并通过 HTTP 发送该消息。  
  
 如果发送端口中使用的是 FILE 适配器而非 HTTP 适配器，则 `HTTP.UserHttpHeaders` 上下文属性中的标头值将不会被写入该消息。 您必须创建一个自定义管道组件以将 `HTTP.UserHttpHeaders` 中的标头置于该消息之前。 然后，可由 FILE 适配器将该消息放入文件夹中，该消息就成了一个包含必需的 HTTP 标头的 AS2 消息。  
  
 您还可能需要创建一个自定义组件，以确保所有 AS2 标头都包含在 `HTTP.UserHttpHeaders` 上下文属性中。 您可以在 AS2Encoder 之前创建一个自定义业务流程或一个自定义管道组件，以设置 AS2 编码器生成 `HTTP.UserHttpHeaders` 时所使用的上下文属性。  
  
## <a name="writing-headers-to-an-as2-message"></a>将标头写入 AS2 消息  
 若要使用 FILE 适配器（而非 HTTP 适配器）生成 AS2 消息，请在自定义 AS2 发送管道中的 AS2 编码器之后添加一个自定义管道组件。 将代码包含在该自定义管道组件中，该自定义管道组件可将 `HTTP.UserHttpHeaders` 上下文属性中的标头写入该消息。 以下为示例代码：  
  
```  
public IBaseMessage Execute(IPipelineContext pContext, IBaseMessage pInMsg)  
        {  
            IPipelineContext pipelineContext = pContext;  
            IBaseMessage baseMessage = pInMsg;  
  
            //Prepend Headers  
            MemoryStream ms = new MemoryStream();  
            string strName = "UserHttpHeaders";  
            string strValue = (string)baseMessage.Context.Read(strName,  
              "http://schemas.microsoft.com/BizTalk/2003/  
              http-properties");  
  
            //Leave an empty line between the headers and the body  
            strValue += "\r\n";  
            ms.Write(Encoding.ASCII.GetBytes(strValue), 0,   
               Encoding.ASCII.GetByteCount(strValue));  
  
            //Append Body  
            Stream sr = baseMessage.BodyPart.Data;  
  
            //Read the body of the message and append it to the memory   
              stream containing the headers  
            int size = 1024;  
            byte[] buffer = new byte[size];  
            while (0 != (size = sr.Read(buffer, 0, buffer.Length)))  
            {  
                ms.Write(buffer, 0, size);  
            }  
  
            //Set the body of the message to the new memory stream  
            baseMessage.BodyPart.Data = ms;  
  
            //Rewind the stream  
            ms.Seek(0, SeekOrigin.Begin);  
  
            return baseMessage;  
        }  
```  
  
## <a name="promoting-as2-header-context-properties"></a>升级 AS2 标头上下文属性  
 您可以使用自定义业务流程或自定义管道组件将 AS2 标头属性升级到消息上下文。  
  
 若要使用自定义管道组件升级 AS2 标头属性，请在自定义 AS2 发送管道中的 AS2 编码器之前添加一个自定义管道组件。 您可以使用如上所示的示例代码中的代码将 `HTTP.UserHttpHeaders` 中的标头写入消息，不过您需将 Read 方法替换为 Promote 方法，并提供要升级的上下文属性的名称、值和命名空间。  
  
 若要使用自定义业务流程升级 AS2 标头属性，请创建一个具有 FILE 接收端口、构造消息形状和 FILE 发送端口的业务流程。 向构造消息形状添加用于设置包含 AS2 标头的已升级属性的代码。 您必须在自定义业务流程中添加到 `Microsoft.BizTalk.HttpTransport.dll` 的引用。  
  
 HTTP 标头的命名空间是非 AS2 HTTP 标头的 `http://schemas.microsoft.com/BizTalk/2003/http-properties` 和 AS2 标头的 `http://schemas.microsoft.com/BizTalk/2003/as2-properties`。  
  
 下面的示例代码说明了如何升级业务流程的构造消息形状中的 AS2 标头属性。 此代码可为 MDN 升级 AS2 标头。  
  
```  
Message_2=new System.Xml.XmlDocument();  
Message_2=Message_1;  
Message_2(EdiIntAS.IsAS2PayloadMessage)=false;  
Message_2(EdiIntAS.IsAS2AsynchronousMdn)=true;  
Message_2(EdiIntAS.IsAS2MdnResponseMessage)=true;  
Message_2(EdiIntAS.SendMDN)=true;  
Message_2(EdiIntAS.IsAS2MessageSigned)=false;  
Message_2(EdiIntAS.AS2To)="Party1";  
Message_2(EdiIntAS.AS2From)="Home";  
Message_2(EdiIntAS.MessageId)="123456";  
Message_2(EdiIntAS.OriginalMessageId)="2123456";  
Message_2(HTTP.UserHttpHeaders)="Message1-Id: xyz\r\nMyHeader: MyValue";  
```  
  
## <a name="see-also"></a>请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)