---
title: "AS2 接收组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bdab87fd-15b9-4e3c-a4d7-984693262293
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c919a54a307a234237dd4086a0abf2a2c0c2fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-receive-components"></a>AS2 接收组件
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用若干个组件来接收 AS2 消息。  
  
## <a name="as2-receive-pipelines"></a>AS2 接收管道  
 大部分 AS2 接收处理工作都在下列 AS2 接收管道中进行。 在中安装这些管道`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`中 files\microsoft BizTalk Server 20xx\Pipeline 组件\\。  
  
 **AS2EdiReceive 管道**  
  
 此管道处理通过 AS2 接收的 EDI 消息，包括 MDN。 管道包含以下管道组件：  
  
-   AS2 解码器  
  
-   EDI 拆装器  
  
-   BatchMarker。  
  
    > [!NOTE]
    >  使用 AS2EdiReceive 管道时，必须将运行 BizTalk 独立主机实例进程的用户帐户添加到 BizTalk Application Users 组中。 AS2EdiReceive 管道在 BizTalk 独立主机实例进程中执行。 AS2EdiReceive 管道会访问 SSO 存储区，这要求用户属于 BizTalk Application Users 组。  
  
 **AS2Receive 管道**  
  
 如果消息未以 EDI 编码，则此管道处理通过 AS2 接收的消息。 这些消息被视为二进制消息。 此管道还处理通过 AS2 接收的 MDN。 管道包含以下管道组件：  
  
-   AS2 解码器  
  
-   AS2 拆装器。  
  
## <a name="as2-receive-pipeline-components"></a>AS2 接收管道组件  
 AS2 接收管道使用以下管道组件。 这些组件安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`中 files\microsoft BizTalk Server 20xx\Pipeline 组件\\。  
  
> [!NOTE]
>  AS2 接收管道只在 32 位 BizTalk 主机进程中受支持。  
  
 **AS2 解码器**  
  
 AS2 解码器包含在 AS2EDIReceivePipeline 和 AS2Receive 接收管道的解码阶段中。 该解码器使用 BizTalk S/MIME 管道组件向 AS2 和 MDN 消息提供 S/MIME 解码功能。  
  
-   处理 AS2/HTTP 标头  
  
-   如果消息已签名，则验证签名  
  
-   如果消息已加密（针对 EDI/AS2 消息，而不适用于 MDN），则对消息进行解密  
  
-   如果消息已压缩，则对消息进行解压缩  
  
-   协调收到的 MDN 与原始出站消息  
  
-   更新并关联不可否认数据库中的记录  
  
-   写入用于 AS2 状态报告的记录  
  
    > [!NOTE]
    >  如果在接收端处理 AS2 消息的过程中发生错误，AS2 解码器将停止进一步的下游消息处理（例如，EDI 拆装器将不会分析交换）。 但是，AS2 拆装器或 EDI 拆装器仍必须生成 MDN。  
  
    > [!NOTE]
    >  对 AS2 消息使用的是八位编码。 Base64 编码仅应用于 AS2 消息和 MDN 中的签名。  
  
 **AS2 反汇编程序**  
  
 在 AS2Receive 接收管道中，AS2 拆装器执行以下操作：  
  
-   确定是否需要 MDN 以及 MDN 应是同步的还是异步的。  
  
-   生成 AS2 MDN。  
  
-   如果 MDN 是同步的，则将 `EdiIntAS.IsAS2AsynchronousMDN` 属性设置为 False；如果是异步的，则将该属性设置为 True。  
  
-   在 MDN 上设置相关标记和属性。  
  
 **EDI 反汇编程序**  
  
 在 AS2EDIReceivePipeline 中，EDI 拆装器会将 EDI 消息解析为中间 XML 消息以进行处理。 有关详细信息，请参阅[EDI 反汇编程序的工作原理](../core/how-the-edi-disassembler-works.md)。  
  
 **BatchMarker**  
  
 在 AS2EDIReceivePipeline 中，BatchMarker 管道组件可设置处理批处理交换所需的 AgreementPartIdForSend 和 ToBeBatched 上下文属性。 此组件包含在 AS2EDIReceive 管道的最后一个阶段（协议解析）中。 将要对 EDI 消息进行批处理的所有管道都应包含 BatchMarker 管道组件。  
  
> [!NOTE]
>  BatchMarker 管道组件未包含在用于处理非 EDI 消息的 AS2Receive 管道中。 但是，你可以在不包含 EDI 拆装器的自定义接收管道中包含 BatchMarker 组件。 有关详细信息，请参见"处理非 EDI 消息中 BatchMarker 组件"在[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
## <a name="http-adapter"></a>HTTP 适配器  
 用于 AS2 处理的接收端口和位置使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 适配器。 已针对单向传输和请求-响应传输对 HTTP 适配器进行了配置。  
  
## <a name="non-repudiation-database"></a>不可否认数据库  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用不可否认数据库（BizTalkDTADb 数据库的 EdiMessageContent 表）执行以下操作：  
  
> [!NOTE]
>  只有在选中了其中一个不可否认存储协议属性时，EdiMessageContent 表才存在于 BizTalkDTADb 数据库中。  
  
-   为已签名的 MDN 提供不可否认记录  
  
-   将出站消息与其传入 MDN 关联起来  
  
-   通过各种状态更改存储消息  
  
-   将错误代码与 HTTP 响应和 MDN 相关联  
  
-   根据筛选条件显示记录  
  
-   将标记的记录存档。  
  
> [!IMPORTANT]
>  为确保不可否认接收数据库中存储的消息的验证和完整性，应对将存储在此数据库中的所有消息（包括原始 AS2 消息和 MDN）使用数字签名。 有关详细信息，请参阅的部分 9.1 [RFC 1430，"MIME 基于安全对等的业务数据交换使用 HTTP，适用性语句 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 接收 AS2 消息的方式](../core/how-biztalk-server-receives-as2-messages.md)