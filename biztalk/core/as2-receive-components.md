---
title: AS2 接收组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdab87fd-15b9-4e3c-a4d7-984693262293
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c64053bbfc818cd2c345e6a2e2268328c3b6b99a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528565"
---
# <a name="as2-receive-components"></a>AS2 接收组件
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用多个组件来接收 AS2 消息。  
  
## <a name="as2-receive-pipelines"></a>AS2 接收管道  
 大部分 AS2 接收处理工作都在下面的示例 AS2 接收管道。 这些管道安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中\\。  
  
 **AS2EdiReceive 管道**  
  
 此管道处理接收的 EDI 消息通过 AS2，包括 Mdn。 管道由以下管道组件组成：  
  
- AS2 解码器  
  
- EDI 拆装器  
  
- BatchMarker。  
  
  > [!NOTE]
  >  使用 AS2EdiReceive 管道时，必须添加到 BizTalk Application Users 组运行 BizTalk 独立主机实例进程的用户帐户。 AS2EdiReceive 管道在 BizTalk 独立主机实例进程中执行。 AS2EdiReceive 管道会访问 SSO 存储区，这要求用户属于 BizTalk Application Users 组。  
  
  **AS2Receive 管道**  
  
  此管道处理通过 AS2 接收时未以 EDI 编码消息的消息。 这些消息被视为二进制消息。 此管道还处理通过 AS2 接收的 Mdn。 管道由以下管道组件组成：  
  
- AS2 解码器  
  
- AS2 拆装器。  
  
## <a name="as2-receive-pipeline-components"></a>AS2 接收管道组件  
 AS2 接收管道都使用以下管道组件。 这些组件安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中\\。  
  
> [!NOTE]
>  AS2 接收管道只能在 32 位 BizTalk 主机进程中。  
  
 **AS2 解码器**  
  
 AS2 解码器包含在 AS2EDIReceivePipeline 的解码阶段中，AS2Receive 接收管道。 它使用 BizTalk S/MIME 管道组件来提供 S/MIME 解码的 AS2 和 MDN 消息的功能。  
  
- 处理 AS2/HTTP 标头  
  
- 验证签名时，如果已对消息签名  
  
- 如果消息已加密 （对于 EDI/AS2 消息，不适用于 MDN） 对消息进行解密  
  
- 如果消息已压缩进行解压缩消息，  
  
- 协调收到的 MDN 和原始的出站消息  
  
- 更新并关联不可否认数据库中的记录  
  
- 写入 AS2 状态报告的记录  
  
  > [!NOTE]
  >  如果在 AS2 消息的接收端处理期间发生错误，AS2 解码器将停止进一步的下游消息处理 （例如，EDI 拆装器将不会分析交换）。 但是，AS2 拆装器或 EDI 拆装器仍必须生成 MDN。  
  
  > [!NOTE]
  >  对 AS2 消息，则使用 8 位编码。 Base64 编码仅应用于中的 AS2 消息和 Mdn 的签名。  
  
  **AS2 拆装器**  
  
  在 AS2Receive 接收管道，AS2 拆装器执行以下任务：  
  
- 确定是否 MDN 是必需的并且是否 MDN 应该同步或异步。  
  
- 生成 AS2 MDN。  
  
- 如果 MDN 是同步的设置`EdiIntAS.IsAS2AsynchronousMDN`属性设置为 False; 如果异步的该属性设置为 True。  
  
- 在 MDN 上设置的相关标记和属性。  
  
  **EDI 拆装器**  
  
  在 AS2EDIReceivePipeline 中，EDI 拆装器会将 EDI 消息解析为中间 XML 消息以进行处理。 有关详细信息，请参阅[EDI 拆装器的工作原理](../core/how-the-edi-disassembler-works.md)。  
  
  **BatchMarker**  
  
  在 AS2EDIReceivePipeline 中，BatchMarker 管道组件设置处理批的交换所需的 AgreementPartIdForSend 和 ToBeBatched 上下文属性。 此组件包含在 AS2EDIReceive 管道的最后一个阶段 （协议解析）。 将 EDI 消息进行批处理的所有管道应都包含 BatchMarker 管道组件。  
  
> [!NOTE]
>  BatchMarker 管道组件不包括在用于处理非 EDI 消息的 AS2Receive 管道。 但是，您可以不包含 EDI 拆装器的自定义接收管道中包含 BatchMarker 组件。 详细信息，请参阅"处理非 EDI 消息在 BatchMarker 组件"中[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
## <a name="http-adapter"></a>HTTP 适配器  
 接收端口和位置用于 AS2 处理使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。 HTTP 适配器配置为单向和请求-响应传输。  
  
## <a name="non-repudiation-database"></a>不可否认数据库  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用不可否认数据库 （BizTalkDTADb 数据库的 EdiMessageContent 表） 执行以下操作：  
  
> [!NOTE]
>  仅当已选中的不可否认存储协议属性之一，EdiMessageContent 表存在 BizTalkDTADb 数据库中。  
  
-   为经过签名的 MDN 提供不可否认记录  
  
-   将出站消息与其传入 mdn 关联起来  
  
-   将通过各种状态更改的消息存储  
  
-   将错误代码与 HTTP 响应和 MDN 相关联  
  
-   显示根据筛选条件的记录  
  
-   标记的记录存档。  
  
> [!IMPORTANT]
>  若要确保身份验证和存储在不可否认接收数据库中的消息的完整性，应将存储在数据库中，原始 AS2 消息和 Mdn 的所有消息使用数字签名。 有关详细信息，请参阅的 9.1 节[RFC 1430、"基于 MIME 的安全对等业务数据交换使用 HTTP，Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)