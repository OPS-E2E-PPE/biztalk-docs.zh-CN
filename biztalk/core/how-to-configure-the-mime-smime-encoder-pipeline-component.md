---
title: 如何配置 MIME-SMIME 编码器管道组件 |Microsoft Docs
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
ms.openlocfilehash: 6f1fb6b75692e221bd1ed56b3b107e9f7039b1f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340807"
---
# <a name="how-to-configure-the-mime-smime-encoder-pipeline-component"></a>如何配置 MIME-SMIME 编码器管道组件
使用 MIME/SMIME 编码器管道组件进行编码，并对传出消息进行加密并对传出消息进行签名。 当你需要 BizTalk Server 与外部合作伙伴之间的安全的文档交换时，此组件非常有用。 此组件还可用于将 BizTalk Server 发送多部分消息。  

> [!NOTE]
>  在 BizTalk 2006 中，MIME/SMIME 编码器管道组件不会支持本机 64 位模式。  这意味着，此组件必须在 32 位仿真模式进程 (WOW64) 中运行。  这意味着，必须在 32 位仿真模式下运行此编码器组件 （或它的一部分的发送管道） 运行的主机实例。  要注意的性能 （和其他） 的此限制对此相同的主机实例中运行的 BizTalk 的其他元素的含义。  

### <a name="to-configure-the-properties-for-the-mimesmime-encoder-pipeline-component"></a>若要配置 MIME/SMIME 编码器管道组件的属性  

1. 将 MIME/SMIME 编码器管道组件拖至发送管道的编码阶段。  

2. 在属性窗口中**管道组件属性**部分中，执行以下操作。  


   |             使用此选项             |                                                                                                                                                                                                                                                                                                                              执行的操作                                                                                                                                                                                                                                                                                                                               |
   |----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **向消息添加签名证书**  |                                                                                                                                                                                                                    如果**签名类型**属性不是**NoSign**，您可以选择是否向签名的消息添加签名证书，方法是设置**向消息添加签名证书**属性。<br /><br /> 默认值：**True**                                                                                                                                                                                                                     |
   |    **检查吊销列表**     |                                                                                                                                                                                                                                                                   指定是否要在处理 SMIME 消息时检查证书吊销列表。<br /><br /> 默认值：**True**                                                                                                                                                                                                                                                                    |
   |  **内容传输编码**   |                                                                                                                                                                                                                                                     指示编码格式。<br /><br /> 选项：Base64、 QuotedPrintable、 SevenBit、 EightBit、 Binary 和 UUEncode。<br /><br /> 默认值：**Base64**                                                                                                                                                                                                                                                      |
   |      **启用加密**       |                                                                                                                                     设置为 **，则返回 True**如果想要对传出消息进行加密。 如果启用此选项，则用户可以选择要通过设置使用的加密算法**加密算法**属性。 对消息加密的 MIME/SMIME 编码器管道组件使用与 BizTalk 浏览器中的发送端口相关联的公钥证书。<br /><br /> 默认值：**False**                                                                                                                                     |
   |     **加密算法**     |                                                                            定义加密算法。<br /><br /> 可以仅设置此属性，如果**启用加密**设置为**True**。<br /><br />**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]及更高版本**，将自动包括 AES 加密。 选项包括：DES3、 DES、 RC2、 AES128 （默认）、 AES192 和 AES256。<br /><br />对于以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]版本中，选项包括：DES3 （默认）、 DES、 RC2。                                                                             |
   | **将正文部分作为附件发送** |                                                                                                                                        设置为 **，则返回 True**如果你想要将 BizTalk 消息的正文参与方作为 MIME 附件发送。<br /><br /> 默认值：**False** **重要：** 不应将此属性设置为 **，则返回 True**时 BizTalk Server 之间发送消息。 否则，消息解码将需要自定义编码，因为消息被解释为两部分消息在接收端。                                                                                                                                        |
   |        **签名类型**        | 如果你想要对传出消息进行签名，选择签名格式使用此属性。 此属性具有三个值：<br /><br /> -   **NoSign**。 将不会对消息进行签名。<br />-   **ClearSign**。 签名将附加到消息。 **ClearSign**如果不能使用**启用加密**设置为**True**。<br />-   **BlobSign**。 签名将附加到消息，并将编码消息。<br /><br /> 进行消息签名的 MIME/SMIME 编码器组件使用 BizTalk 管理控制台中与 BizTalk 组相关联的私钥客户端证书。<br /><br /> 默认值：**NoSign** |

   若要设置 MIME 附件的文件名，使用**文件名**属性中的**系统**消息部分的命名空间。  

## <a name="see-also"></a>请参阅  
 [MIME-SMIME 编码器管道组件](../core/mime-smime-encoder-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [MIME-SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)   
 [MIME（BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)