---
title: 交换状态和 ACK 的详细信息状态报告 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ebba4af5-6dff-4bb8-9c63-739ef49bbbb8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cc596a99d1a49b01ccc417abccb73d12ed34ad5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257637"
---
# <a name="interchange-status-and-ack-details-status-report"></a>“交换状态和确认详细信息”状态报告
此状态报告显示交换及其相关交换（技术）确认和功能确认的详细信息。 右键单击交换/ACK 状态报表中中的交换，然后单击为此报表显示**交换状态和 ack 的详细信息**。  
  
 此报告为交换及相关确认提供了以下不同的视图：  
  
## <a name="interchange-status"></a>交换状态  
 此视图提供一个表格，显示了以下字段的值：  
  
-   发送方 ID  
  
-   接收方 ID  
  
-   控件 ID  
  
-   接收方名称  
  
-   发件人方名称  
  
-   方向  
  
-   交换日期时间  
  
    > [!NOTE]
    >  对于收到的文档，如果在交换中指定的日期格式为 YYMMDD 且 YY 大于等于 75，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将年份显示为 19YY。 如果日期中的 YY 小于 75，将显示为 20YY。  
    >   
    >  例如，如果你收到的交换在 ISA09 中包含值 991113，则在报告中将“交换日期”显示为 11/13/1999。  
  
-   组计数  
  
-   端口 ID  
  
-   交换状态  
  
-   EDI 编码类型  
  
-   事务集相关 ID  
  
 如果为作为交换接收方的参与方启用了技术确认（在“EDI 属性”对话框的“确认处理和验证设置”页中），BizTalk Server 将期待返回为了响应它发送的交换而发回的技术（交换）确认。 在最初为出站交换创建交换状态条目的时候，它将在“交换状态”字段中输入“预期的确认”。 如果它收到了技术确认并且将其关联到原始交换，它会更新“交换状态”字段以指出它已收到确认。  
  
## <a name="interchange-ack-status"></a>交换确认状态  
 此视图显示交换（技术）确认的状态值：  
  
-   ACK 交换控制 ID  
  
-   接收方方  
  
-   发送方  
  
-   方向  
  
-   ACK 交换日期  
  
-   ACK 交换时间  
  
-   ACK 状态  
  
-   状态代码  
  
-   ACK 注释代码 1  
  
-   ACK 注释代码 2  
  
## <a name="functional-acks"></a>功能 Ack(s)  
 此视图显示功能确认的状态值：  
  
-   组控制编号  
  
-   接收方方  
  
-   发送方  
  
-   方向  
  
-   状态  
  
-   状态代码  
  
-   功能 ID 代码  
  
-   TS 计数  
  
-   ACK 交换控制 ID  
  
-   ACK 交换日期  
  
-   ACK 交换时间  
  
-   已送达 TS 计数  
  
-   已接受 TS 计数  
  
-   ErrorCode 1  
  
-   ErrorCode 2  
  
-   Errorcode 3  
  
-   ErrorCode 4  
  
-   错误代码 5  
  
-   接收时间