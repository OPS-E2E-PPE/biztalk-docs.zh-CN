---
title: "处理多部分消息使用 POP3 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ad041f-f155-4c1c-ab87-1405c80d9b68
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26aff4569414103ad8c4f37a9e4699a85874e481
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-multi-part-messages-with-the-pop3-adapter"></a>使用 POP3 适配器处理多部分消息
POP3 适配器可以处理符合 IETF 标准中所述的 MIME 编码消息[RFC 2045](http://go.microsoft.com/fwlink/?LinkId=58810)， [RFC 2046](http://go.microsoft.com/fwlink/?LinkId=58811)，和[RFC 2047](http://go.microsoft.com/fwlink/?LinkId=58812)。 MIME 编码的消息可以只包含一个部分，也可以包含多个部分且各部分具有不同的内容类型。 本主题介绍 POP3 适配器将如何处理多部分 MIME 编码的消息。  
  
## <a name="receiving-multi-part-messages-with-the-pop3-adapter"></a>使用 POP3 适配器接收多部分消息  
 如果具有使用 POP3 适配器接收位置**应用 MIME 解码**选项设置为**True**然后 POP3 适配器接收 MIME 编码消息时执行下列操作：  
  
1.  从其接收的 MIME 编码消息的各部分创建一个多部分 BizTalk 消息。 此多部分消息可包含一到多个部分，并且所包含的部分数与接收到的 MIME 编码消息相同。  
  
2.  扫描 MIME 编码消息的标头。 如果任何标头与匹配的记录在该主题的属性列表[POP3 适配器属性架构和属性](../core/pop3-adapter-property-schema-and-properties.md)然后这些标头将被提升到多一部分 BizTalk 消息作为上下文属性。  
  
3.  使用一个可配置的算法，将 MIME 编码消息中的一个部分指定为 BizTalk 消息的正文部分。 用来确定哪些消息部分将 BizTalk 消息正文部分的算法节所述下面**POP3 适配器使用的正文部分选择算法**。  
  
4.  将多部分 BizTalk 消息发布到 MessageBox。  
  
## <a name="body-part-selection-algorithm-used-by-the-pop3-adapter"></a>POP3 适配器使用的正文部分选择算法  
 当 POP3 适配器从其接收的 MIME 编码消息的各部分创建一个多部分 BizTalk 消息时，它将选择其中的一个消息部分作为 BizTalk 消息的正文部分。 BizTalk Server 将使用 BizTalk 消息正文部分来执行消息验证、映射、属性升级、平面文件组装等操作。 多部分 BizTalk 消息的订户将接收所有的消息部分，但除非使用可以理解多部分消息的业务流程、自定义管道或适配器，它将只使用指定的 BizTalk 消息正文部分。 例如，您可以配置业务流程，使其读取多部分消息的所有部分。SMTP 适配器可以读取多部分消息的所有部分。您也可以配置一个自定义管道，使其使用 MIME/SMIME 编码器管道组件。 有关使用业务流程使用多部分消息的详细信息请参阅以下部分，**在业务流程中处理多部分消息**。  
  
 POP3 适配器从可用的正文部分基于为提供的值选择 BizTalk 消息正文部分**正文部分索引**和**正文部分内容类型**。  
  
> [!NOTE]
>  POP3 适配器旨在识别中定义正文部分内容类型[RFC 2046](http://go.microsoft.com/fwlink/?LinkId=119569)。  
  
 下面介绍了用于选择电子邮件的 BizTalk 消息正文部分的算法：  
  
1.  如果**正文部分索引**设置为 0 和**正文部分内容类型**为空，则将使用以下算法选择 BizTalk 消息正文部分：  
  
    -   使用内容说明标头设置为“body”的第一个 MIME 部分。  
  
    -   否则，使用内容类型标头设置为“text/xml”的第一个 MIME 部分。  
  
    -   否则，使用内容类型标头设置为“text/plain”的第一个 MIME 部分。  
  
    -   否则，使用内容类型标头设置为“text/”的第一个 MIME 部分。  
  
    -   否则，使用第一个 MIME 部分。  
  
2.  否则为如果**正文部分索引**设置为 0 和**正文部分内容类型**是设置，那么匹配所指定的传入消息的第一个正文部分**正文部分内容类型**被选为 BizTalk 消息正文部分。 如果所有部分的内容类型均不与指定的正文部分内容类型匹配，则挂起消息。  
  
3.  否则为如果**正文部分索引**设置为值大于 0 和**正文部分内容类型**为空，则具有指定索引的正文部分被选为 BizTalk 消息正文部分。 如果指定的索引大于正文部分的数量，则挂起消息。  
  
4.  否则为如果**正文部分索引**设置为值大于 0 和**正文部分内容类型**设置，则**正文部分索引**仅应用到那些正文部分具有指定**正文部分内容类型**和相应的正文部分被选为 BizTalk 消息正文部分。 如果指定的索引大于具有匹配内容类型的部分的数量，则挂起消息。 如果所有部分的内容类型均不与指定的正文部分内容类型匹配，则挂起消息。  
  
5.  选择作为 BizTalk 消息正文部分的部分将被首先发布到 MessageBox，其余的多部分 BizTalk 消息部分则保持其在原始 MIME 编码消息中的顺序。  
  
## <a name="processing-multi-part-messages-in-orchestrations"></a>在业务流程中处理多部分消息  
 当 POP3 适配器从其接收的 MIME 编码消息创建多部分 BizTalk 消息时，会将所有部分发布到 MessageBox 数据库，即使只有其中一个部分被指定为 BizTalk 消息正文部分，也会发布所有部分。 随后，订阅多部分消息的业务流程就可以使用这些部分。 本部分说明了一些在业务流程中处理多部分消息时应注意的事项。  
  
### <a name="processing-multi-part-messages-with-a-known-number-of-parts-and-known-part-types"></a>处理部分数和部分类型已知的多部分消息  
 如果业务流程将要接收具有已知部分数和已知部分类型的多部分消息，则可以选择在业务流程中声明一个多部分消息，并在设计时设置部分数和部分类型。  
  
### <a name="processing-multi-part-messages-with-unknown-part-types"></a>处理部分类型未知的多部分消息  
 如果您的业务流程接收具有未知的部件类型的多部分消息，则你可以声明中的业务流程和使用多部分消息**XmlDocument**的每个部分的类型是未知的类型。  
  
### <a name="processing-multi-part-messages-with-an-unknown-number-of-parts-and-all-of-the-part-types-are-unknown"></a>处理部分数和所有部分类型均未知的多部分消息  
 如果您的业务流程接收未知数量的部件的多部分消息，则你可以声明的单个部件的多部分消息**XmlDocument**业务流程中要接收消息的类型。 如果收到包含大于的声明部分数多部分消息时，有多少个部分是在消息中，业务流程引擎读取然后构造中声明的消息的部件的数量匹配的部件的正确部件类型类型，然后构造**XmlDocument**部件的其余部分。