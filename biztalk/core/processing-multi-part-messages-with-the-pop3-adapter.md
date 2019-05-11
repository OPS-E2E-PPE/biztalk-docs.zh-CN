---
title: 使用 POP3 适配器处理多部分消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56ad041f-f155-4c1c-ab87-1405c80d9b68
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68c02f7a5bded3ccffa60ae7327297342ffdc0d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396977"
---
# <a name="processing-multi-part-messages-with-the-pop3-adapter"></a>使用 POP3 适配器处理多部分消息
POP3 适配器可以处理符合 IETF 标准中所述的 MIME 编码的消息[RFC 2045](http://go.microsoft.com/fwlink/?LinkId=58810)， [RFC 2046](http://go.microsoft.com/fwlink/?LinkId=58811)，并[RFC 最多允许 2047年](http://go.microsoft.com/fwlink/?LinkId=58812)。 MIME 编码的消息可以包含一到使用不同的内容类型的许多部件。 本主题讨论如何 POP3 适配器处理多部分 MIME 编码消息。  
  
## <a name="receiving-multi-part-messages-with-the-pop3-adapter"></a>使用 POP3 适配器接收多部分消息  
 使用 POP3 适配器的接收位置是否**应用 MIME 解码**选项设置为**True**然后 POP3 适配器接收的 MIME 编码消息时将执行以下操作：  
  
1.  从其接收的 MIME 编码消息各部分创建多部分 BizTalk 消息。 此多部分消息可以包含一到多个部分，并且将包含接收的 MIME 编码消息相同的部分数。  
  
2.  扫描 MIME 编码消息的标头。 如果任何标头与匹配的主题中描述的属性列表[POP3 适配器属性架构和属性](../core/pop3-adapter-property-schema-and-properties.md)然后这些标头升级到多部分 BizTalk 消息上下文属性为。  
  
3.  使用可配置的算法来指定的 MIME 编码消息部分作为 BizTalk 消息正文部分。 用于确定哪个消息部分将 BizTalk 消息正文部分的算法部分所述下面**POP3 适配器使用的正文部分选择算法**。  
  
4.  将多部分 BizTalk 消息发布到 MessageBox。  
  
## <a name="body-part-selection-algorithm-used-by-the-pop3-adapter"></a>POP3 适配器使用的正文部分选择算法  
 当 POP3 适配器从其接收的 MIME 编码消息的各部分创建多部分 BizTalk 消息时，它选择一个消息部分作为 BizTalk 消息正文部分。 消息验证、 映射、 属性升级、 平面文件的程序集和其他操作等工作，BizTalk Server 使用 BizTalk 消息正文部分。 多部分 BizTalk 消息的订阅服务器接收所有消息部分，但将只使用指定的 BizTalk 消息正文部分，除非使用业务流程、 自定义管道或适配器，它可以理解多部分消息。 例如，可以配置业务流程可读取多部分消息; 的所有部分SMTP 适配器可以读取的所有部件的多部分消息，并可以将自定义管道配置为使用 MIME/SMIME 编码器管道组件。 有关使用业务流程使用多部分消息的详细信息请参阅以下部分**业务流程中处理多部分消息**。  
  
 POP3 适配器从可用正文部分基于为提供的值中选择 BizTalk 消息正文部分**正文部分索引**并**正文部分内容类型**。  
  
> [!NOTE]
>  POP3 适配器专门识别中定义正文部分内容类型[RFC 2046](http://go.microsoft.com/fwlink/?LinkId=119569)。  
  
 用于选择电子邮件的 BizTalk 消息正文部分的算法如下所述：  
  
1.  如果**正文部分索引**设置为 0，**正文部分内容类型**为空，则使用以下算法来选择 BizTalk 消息正文部分：  
  
    -   设置为"body"的内容说明标头，使用第一个 MIME 部分。  
  
    -   否则，第一个 MIME 部分使用设置为"text/xml"的内容类型标头。  
  
    -   否则，第一个 MIME 部分使用设置为"text/plain"的内容类型标头。  
  
    -   否则，第一个 MIME 部分使用内容类型标头设置为"text /"。  
  
    -   否则使用第一个 MIME 部分。  
  
2.  否则为如果**正文部分索引**设置为 0，**正文部分内容类型**为集，则匹配所指定的传入消息的第一个正文部分**正文部分内容类型**选为 BizTalk 消息正文部分。 如果没有具有匹配的内容类型的部件会挂起消息。  
  
3.  否则为如果**正文部分索引**设置为值大于 0 并**正文部分内容类型**为空，则选择具有指定索引的正文部分作为 BizTalk 消息正文部分。 如果指定的索引大于正文部分的数量会挂起消息。  
  
4.  否则为如果**正文部分索引**设置为值大于 0 并**正文部分内容类型**设置，则**正文部分索引**，才会应用为正文部分具有指定**正文部分内容类型**并选择相应的正文部分作为 BizTalk 消息正文部分。 如果指定的索引大于具有匹配的内容类型的部分数会挂起消息。 如果没有具有匹配的内容类型的部件会挂起消息。  
  
5.  BizTalk 消息正文部分变得多部分 BizTalk 消息发布到 MessageBox 的第一个部分所选的部分，该消息的其余部分保持顺序在原始 MIME 编码的消息所具有的。  
  
## <a name="processing-multi-part-messages-in-orchestrations"></a>处理业务流程中的多部分消息  
 当 POP3 适配器从其接收的 MIME 编码消息创建多部分 BizTalk 消息时，所有部件被发布到 MessageBox 数据库中，即使只有其中一个部分指定为 BizTalk 消息正文部分。 订阅多部分消息的业务流程可以随后使用这些部件。 处理业务流程中的多部分消息时，本部分将介绍一些注意事项。  
  
### <a name="processing-multi-part-messages-with-a-known-number-of-parts-and-known-part-types"></a>处理具有已知数量的部件和已知的部分类型的多部分消息  
 如果业务流程将要接收具有已知部分数和已知的部分类型的多部分消息然后可以声明一个业务流程中的多部分消息，并在设计时设置部分和部件类型的数量。  
  
### <a name="processing-multi-part-messages-with-unknown-part-types"></a>处理多部分消息具有未知的部分类型  
 如果业务流程将要接收具有未知的部分类型的多部分消息，则可以声明多部分消息中的业务流程和使用**XmlDocument**的每个部分的类型是未知的类型。  
  
### <a name="processing-multi-part-messages-with-an-unknown-number-of-parts-and-all-of-the-part-types-are-unknown"></a>处理多部分消息具有未知的部分数和所有部件类型是未知  
 如果业务流程将要接收具有未知部分数多部分消息，则可以声明多部分消息的单个部分**XmlDocument**业务流程中的类型，用于接收消息。 如果收到包含多于声明部分数量更多部分消息，则业务流程引擎读取有多少个部分是在消息中，然后构造正确的部分类型的部件的匹配部分中声明的消息数类型，然后构造**XmlDocument**部件的剩余部分。