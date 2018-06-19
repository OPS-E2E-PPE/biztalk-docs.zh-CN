---
title: 如何配置 MIME SMIME 编码器管道组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encrypting digital signatures
- pipeline components, MIME/SMIME Encoder
- Partner Management, security
- MIME/SMIME Encoder [pipeline component], configuring
- messages, encoding
- messages, multi-parts
ms.assetid: dcbb08e8-d300-4e7f-9c1c-907fb602e721
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07cabef8510fb2189da759ba9b0c156ef672410e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249653"
---
# <a name="how-to-configure-the-mime-smime-encoder-pipeline-component"></a>如何配置 MIME SMIME 编码器管道组件
使用 MIME/SMIME 编码器管道组件可对传出消息进行编码和加密并对传出消息进行签名。 当 BizTalk Server 与外部合作伙伴之间需要进行安全文档交换时，此组件非常有用。 还可以使用此组件发送 BizTalk Server 多部分消息。  
  
> [!NOTE]
>  在 BizTalk 2006 中，MIME/SMIME 编码器管道组件将不再支持本机 64 位模式。  这意味着此组件必须运行在 32 位仿真模式进程 (WOW64) 中。  这表示运行此编码器组件（或其所属发送管道）的主机实例必须以 32 位仿真模式运行。  请注意此限制对运行在此主机实例中的其他 BizTalk 元素性能（和其他方面）的影响。  
  
### <a name="to-configure-the-properties-for-the-mimesmime-encoder-pipeline-component"></a>配置 MIME/SMIME 编码器管道组件的属性  
  
1.  将 MIME/SMIME 编码器管道组件拖至发送管道的编码阶段。  
  
2.  在属性窗口中，在**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**将签名证书添加到消息**|如果**签名类型**属性不是**NoSign**，你可以选择是否将签名证书添加到已签名的消息，通过设置**添加签名的证书添加到消息**属性。<br /><br /> 默认值： **True**|  
    |**检查吊销列表**|指定处理 SMIME 消息时是否检查证书吊销列表。<br /><br /> 默认值： **True**|  
    |**编码的内容传输**|指示当前的编码格式。<br /><br /> 选项：Base64、QuotedPrintable、SevenBit、EightBit、Binary 和 UUEncode。<br /><br /> 默认值： **Base64**|  
    |**启用加密**|设置为**True**如果你想要对传出消息进行加密。 如果启用此选项，用户可以选择要使用通过设置的加密算法**加密算法**属性。 MIME/SMIME 编码器管道组件使用与 BizTalk 浏览器中发送端口相关联的公钥证书进行消息加密。<br /><br /> 默认值： **False**|  
    |**加密算法**|定义加密算法。<br /><br /> 可以仅设置此属性，如果**启用加密**设置为**True**。<br /><br />**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]和更高版本**，AES 加密会自动包括。 选项包括： DES3、 DES、 RC2、 AES128 （默认值）、 AES192 和 AES256。<br /><br />有关以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本中，选项包括： DES3 （默认值）、 DES、 RC2。|  
    |**将正文部分作为附件发送**|设置为**True**如果你想要以 MIME 附件形式发送 BizTalk 消息的正文当事方。<br /><br /> 默认值： **False** **重要说明：** 不应将此属性设置为**True**发送 BizTalk 服务器之间的消息时。 否则，由于消息在接收端被解释为两部分消息，因而消息解码将需要自定义编码。|  
    |**签名类型**|如果希望对传出消息进行签名，请使用此属性选择签名格式。 此属性有三个值：<br /><br /> -   **NoSign**。 不对消息进行签名。<br />-   **ClearSign**。 该签名将追加到消息。 **ClearSign**如果不能使用**启用加密**设置为**True**。<br />-   **BlobSign**。 签名将附加到消息中，并且消息将被编码。<br /><br /> MIME/SMIME 编码器组件使用与 BizTalk 管理控制台中 BizTalk 组关联的私钥客户端证书进行消息签名。<br /><br /> 默认值： **NoSign**|  
  
 若要设置 MIME 附件的文件名称，使用**FileName**中的属性**系统**消息部分的命名空间。  
  
## <a name="see-also"></a>另请参阅  
 [MIME SMIME 编码器管道组件](../core/mime-smime-encoder-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [MIME SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)   
 [MIME （BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)