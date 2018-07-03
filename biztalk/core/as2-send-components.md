---
title: AS2 发送组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3378dbb623c2d47a56946805908f9d104500a8ac
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994558"
---
# <a name="as2-send-components"></a>AS2 发送组件
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用若干个组件来发送 AS2 消息。  
  
## <a name="as2-send-pipelines"></a>AS2 发送管道  
 大部分 AS2 发送处理工作都在下列 AS2 发送管道中进行。 这些管道安装在 \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中的 `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` 中。  
  
> [!NOTE]
>  AS2 发送管道只在 32 位 BizTalk 主机进程中受支持。  
  
 **AS2EDISend 管道**  
  
 此管道生成 EDI 消息并通过 AS2 发送这些消息。 管道由以下管道组件组成：  
  
- EDI 组装器  
  
- AS2 编码器  
  
  此管道不用于生成和通过 AS2 发送 MDN，因为 MDN 不需要由 EDI 组装器处理。 使用 AS2SendPipeline 发送 MDN。  
  
> [!NOTE]
>  不支持从业务流程中运行 AS2EDISend 管道。  
  
 **AS2Send 管道**  
  
 如果消息未以 EDI 编码，则此管道通过 AS2 发送消息。 此管道还通过 AS2 发送 MDN。 管道由以下管道组件组成：  
  
- AS2 编码器。  
  
  如果要通过 AS2 发送的消息既不是 EDI 消息，也不是 XML 消息，则可以创建一个自定义 AS2Send 管道来处理这些消息。 此管道必须具有自定义组装器，以便将 BizTalk Server 中的中间 XML 转换为其他格式后再以 EDIINT/AS2 对消息进行编码。  
  
> [!NOTE]
>  不支持从业务流程运行 AS2Send 管道。  
  
## <a name="as2-send-pipeline-components"></a>AS2 发送管道组件  
 AS2 发送管道使用以下管道组件。 这些组件安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中\\。  
  
 **EDI 组装器**  
  
 在 EDIINT 发送管道中，EDI 组装器将对 EDI 交换进行序列化。  
  
 **AS2 编码器**  
  
 AS2 编码器包括在 AS2 发送管道的编码阶段中。 该编码器使用 BizTalk S/MIME 管道组件向 AS2 和 MDN 消息提供 S/MIME 编码功能。 AS2 编码器执行以下操作：  
  
-   应用 AS2/HTTP 标头  
  
-   对传出消息进行签名（如果已启用）  
  
-   对传出消息进行加密（如果已启用）（适用于 EDI/AS2，不适用于 MDN）  
  
-   压缩消息（如果已启用）（适用于 EDI/AS2，不适用于 MDN）  
  
-   如果以传输格式存储负载**已为解码后的出站 AS2 消息启用 NRR**属性选择，并且将该消息以传输格式存储，如果**已为出站编码 AS2 消息启用 NRR**选择属性  
  
-   计算 MIC 值并将其存储在数据存储区中  
  
-   更新并关联不可否认接收数据库中的记录  
  
-   对于 MDN 消息，充当直通管道，在 AS2Receive 接收管道中路由 AS2 解码器生成的 MDN。 如果配置设置要求，AS2 编码器将对 MDN 进行签名。  
  
    > [!NOTE]
    >  对 AS2 消息使用的是八位编码。 Base64 编码仅应用于 AS2 消息和 MDN 中的签名。  
  
## <a name="http-adapter"></a>HTTP 适配器  
 EDIINT AS2 处理用到的发送端口使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 适配器。 在单向传输和要求-响应传输中均对 HTTP 适配器进行了配置。  
  
## <a name="non-repudiation-database"></a>不可否认数据库  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用不可否认数据库（BizTalkDTADb 数据库的 EdiMessageContent 表）执行以下操作：  
  
> [!NOTE]
>  BizTalkDTADb 数据库中 EdiMessageContent 表存在，才选中一个不可否认存储协议属性。  
  
-   为经过签名的 MDN 提供不可否认记录  
  
-   将出站消息与其传入 mdn 关联起来  
  
-   存储通过各种状态更改的消息  
  
-   将错误代码与 HTTP 响应和 MDN 关联起来  
  
-   显示根据筛选条件的记录  
  
-   将标记的记录存档  
  
> [!IMPORTANT]
>  为确保不可否认数据库中存储的消息的验证和完整性，应对将存储在此数据库中的所有消息使用数字签名，原始 AS2 消息和 MDN 都包含在内。 有关详细信息，请参阅的 9.1 节[RFC 1430、"基于 MIME 的安全对等业务数据交换使用 HTTP，Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)