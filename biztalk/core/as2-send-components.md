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
ms.openlocfilehash: 352cde6b72aecaf0baa9c53d1f67b63f3da215c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359005"
---
# <a name="as2-send-components"></a>AS2 发送组件
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用多个组件发送 AS2 消息。  
  
## <a name="as2-send-pipelines"></a>AS2 发送管道  
 大部分 AS2 发送处理工作都在下列 AS2 发送管道。 这些管道安装在`Microsoft.BizTalk.Edi.EdiIntPipelines.dll`\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中。  
  
> [!NOTE]
>  AS2 发送管道只能在 32 位 BizTalk 主机进程中。  
  
 **AS2EDISend 管道**  
  
 此管道生成，并通过 AS2 发送 EDI 消息。 管道由以下管道组件组成：  
  
- EDI 组装器  
  
- AS2 编码器  
  
  此管道不用于生成和 Mdn 通过 AS2 发送，因为 MDN 不需要由 EDI 组装器处理。 使用 AS2SendPipeline 发送 Mdn。  
  
> [!NOTE]
>  不支持从业务流程中运行 AS2EDISend 管道。  
  
 **AS2Send 管道**  
  
 未以 EDI 编码消息时，此管道通过 AS2 发送消息。 它还通过 AS2 发送 Mdn。 管道由以下管道组件组成：  
  
- AS2 编码器。  
  
  如果要通过 AS2 发送的消息是 EDI 既不 XML 消息，可以创建自定义的 AS2Send 管道来处理这些消息。 此管道必须具有自定义组装器，以便以 ediint/as2 对消息编码前将 BizTalk Server 中的中间 XML 转换成其他格式。  
  
> [!NOTE]
>  不支持从业务流程运行 AS2Send 管道。  
  
## <a name="as2-send-pipeline-components"></a>AS2 发送管道组件  
 AS2 发送管道使用以下管道组件。 这些组件安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中\\。  
  
 **EDI 组装器**  
  
 在 EDIINT 发送管道中，EDI 组装器序列化 EDI 交换。  
  
 **AS2 编码器**  
  
 AS2 编码器包括在 AS2 发送管道的编码阶段。 它使用 BizTalk S/MIME 管道组件来提供 S/MIME 编码的 AS2 和 MDN 消息的功能。 AS2 编码器执行以下任务：  
  
-   应用 AS2/HTTP 标头  
  
-   对传出消息，如果启用了进行签名  
  
-   对传出消息进行加密，如果已启用 （适用于 EDI/AS2，不适用于 MDN)  
  
-   压缩消息，如果已启用 （适用于 EDI/AS2，不适用于 MDN)  
  
-   如果以传输格式存储负载**已为解码后的出站 AS2 消息启用 NRR**属性选择，并且将该消息以传输格式存储，如果**已为出站编码 AS2 消息启用 NRR**选择属性  
  
-   计算的 MIC 值并将其存储在数据存储区  
  
-   更新并关联不可否认接收数据库中的记录  
  
-   对于 MDN 消息，充当直通管道，路由 MDN 生成的 AS2 解码器在 AS2Receive 接收管道。 如果所需的配置设置，则 AS2 编码器将对 MDN 签名。  
  
    > [!NOTE]
    >  对 AS2 消息，则使用 8 位编码。 Base64 编码仅应用于中的 AS2 消息和 Mdn 的签名。  
  
## <a name="http-adapter"></a>HTTP 适配器  
 EDIINT AS2 处理用于使用的发送端口[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。 在这种单向配置 HTTP 适配器和要求-响应传输。  
  
## <a name="non-repudiation-database"></a>不可否认数据库  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用不可否认数据库 （BizTalkDTADb 数据库的 EdiMessageContent 表） 执行以下操作：  
  
> [!NOTE]
>  BizTalkDTADb 数据库中 EdiMessageContent 表存在，才选中一个不可否认存储协议属性。  
  
-   为经过签名的 MDN 提供不可否认记录  
  
-   将出站消息与其传入 mdn 关联起来  
  
-   存储通过各种状态更改的消息  
  
-   将错误代码与 HTTP 响应和 MDN 相关联  
  
-   显示根据筛选条件的记录  
  
-   将标记的记录存档  
  
> [!IMPORTANT]
>  若要确保身份验证和不可否认数据库中存储的消息的完整性，应将存储在数据库中，原始 AS2 消息和 Mdn 的所有消息使用数字签名。 有关详细信息，请参阅的 9.1 节[RFC 1430、"基于 MIME 的安全对等业务数据交换使用 HTTP，Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)