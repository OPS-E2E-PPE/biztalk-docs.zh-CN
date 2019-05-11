---
title: 如何配置 MIME-SMIME 解码器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, attachments
- pipeline components, MIME/SMIME Decoder
- MIME/SMIME Decoder [pipeline component], configuring
- messages, verifying
- messages, decoding
- messages, digital signatures
- messages, security
ms.assetid: bfd44893-f1c3-4524-abc6-f820b8c0ef07
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cde85adeec5d1155afdba28d2e7ca2bf5647983d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386028"
---
# <a name="how-to-configure-the-mime-smime-decoder-pipeline-component"></a>如何配置 MIME-SMIME 解码器管道组件
MIME/SMIME 解码器管道组件用于解码和解密 MIME/SMIME 编码的消息和验证数字签名的签名消息。 当外部合作伙伴与 BizTalk Server 之间需要安全的文档交换时，此组件非常有用。 此组件还可用于接收带附件的邮件。  
  
> [!NOTE]
>  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，MIME/SMIME 解码器管道组件不具有支持本机 64 位模式。  这意味着，此组件必须在 32 位仿真模式进程 (WOW64) 中运行。  这意味着，必须在 32 位仿真模式下运行此解码器组件 （或它的一部分的接收管道） 运行的主机实例。  要注意的性能 （和其他） 的此限制对此相同的主机实例中运行的 BizTalk 的其他元素的含义。  
> 
> [!NOTE]
>  POP3 适配器中还使用 MIME/SMIME 解码器组件。  因此，运行 POP3 适配器的主机实例存在相同的本机 64 位支持限制。  有关 POP3 适配器的信息，请参阅[POP3 适配器](../core/pop3-adapter.md)。  
  
### <a name="to-configure-the-properties-for-the-mimesmime-decoder-pipeline-component"></a>若要配置 MIME/SMIME 解码器管道组件的属性  
  
1.  将 MIME/SMIME 解码器管道组件拖至接收管道的解码阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**允许非 MIME 消息**|将此属性设置为 **，则返回 True**如果希望接收管道能够接收不是 MIME 编码的消息。 在不同的形式，例如，MIME 编码或普通 XML 中接收消息的管道中使用 MIME/SMIME 解码器管道组件时，此选项非常有用。 默认情况下，此属性设置为**False**，含义组件生成一个错误，如果收到非 MIME 编码的消息输入。 **注意：** MIME 解码器扫描传入的消息搜索"Mime-version"标头的第一个 1024 字节。 如果找不到此标头，该消息被视为非 MIME 消息。 <br /><br /> 默认值：**False**|  
    |**正文部分内容类型**|指示 MIME 部分的内容类型。 与此内容类型的 MIME 部分将成为 BizTalk 消息正文部分。<br /><br /> 默认值：None|  
    |**正文部分索引**|指示 MIME 部分列表中的基于 1 的索引。 在列表中此索引处的 MIME 部分将成为 BizTalk 消息正文部分。 若要禁用按索引选择正文部分，使用值**0**。<br /><br /> 默认值：**0**|  
    |**检查吊销列表**|将此属性设置为 **，则返回 True**如果你想要检查证书吊销列表中的发件人用于发送到 BizTalk Server 的消息进行签名的证书。 如果禁用此选项会增加该组件的性能。<br /><br /> 与证书关联的证书吊销列表从远程网站 (例如 Verisign.com) 下载。 如果 BizTalk Server 无法连接到远程网站中，管道中的消息失败。<br /><br /> 默认值：**True**|  
  
## <a name="see-also"></a>请参阅  
 [MIME-SMIME 解码器管道组件](../core/mime-smime-decoder-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [MIME-SMIME 属性架构和属性](../core/mime-smime-property-schema-and-properties.md)   
 [MIME（BizTalk Server 示例）](../core/mime-biztalk-server-sample.md)