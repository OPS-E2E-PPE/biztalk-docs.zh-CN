---
title: 交换状态和确认详细信息状态报告 |Microsoft Docs
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
ms.openlocfilehash: 167162a47516279c22bd250589246b3dbd12f109
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381932"
---
# <a name="interchange-status-and-ack-details-status-report"></a>交换状态和确认详细信息状态报告
此状态报告显示交换及其相关的交换 （技术） 确认和功能确认的详细信息。 显示此报告，右键单击交换 /ACK 状态报表中的某个交换，然后单击**交换状态和确认详细信息**。  
  
 此报表提供的交换和相关的确认以下不同的视图：  
  
## <a name="interchange-status"></a>交换状态  
 此视图提供的表格显示以下字段的值：  
  
- 发送方 ID  
  
- 接收方 ID  
  
- 控件 ID  
  
- 接收方名称  
  
- 发送方的参与方名称  
  
- Direction  
  
- 交换日期时间  
  
  > [!NOTE]
  >  对于收到的文档，如果交换中指定的日期格式为 YYMMDD 且 YY 大于或等于 75，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将年份显示为 19YY。 如果日期是小于 75，将显示为 20YY。  
  > 
  >  例如，如果收到包含在 ISA09 中的值 991113 的交换，交换日期将是报告中列出为 1999 年 11/13。  
  
- 组计数  
  
- 端口 ID  
  
- 交换状态  
  
- EDI 编码类型  
  
- 事务集相关 Id  
  
  如果为参与方作为交换接收方 （在 EDI 属性对话框的确认处理和验证设置页中） 启用了技术确认，BizTalk Server 期望在响应中返回的技术 （交换） 确认发送的交换。 当它最初创建交换状态条目的出站交换时，它将进入预期的确认在交换状态字段中。 当它收到了技术确认，并将其关联到原始交换时，它将更新交换状态字段以指示它已收到确认。  
  
## <a name="interchange-ack-status"></a>交换确认状态  
 此视图显示交换 （技术） 确认的状态值：  
  
-   Ack 交换控制 ID  
  
-   接收方  
  
-   发送方  
  
-   Direction  
  
-   Ack 交换日期  
  
-   Ack 交换时间  
  
-   Ack 状态  
  
-   状态代码  
  
-   Ack 注释代码 1  
  
-   Ack 注释代码 2  
  
## <a name="functional-acks"></a>功能确认  
 此视图显示功能确认的状态值：  
  
-   组控制编号  
  
-   接收方  
  
-   发送方  
  
-   Direction  
  
-   “登录属性”  
  
-   状态代码  
  
-   功能 ID 代码  
  
-   TS 计数  
  
-   Ack 交换控制 ID  
  
-   Ack 交换日期  
  
-   Ack 交换时间  
  
-   已送达的 TS 计数  
  
-   已接受的 TS 计数  
  
-   ErrorCode 1  
  
-   错误代码 2  
  
-   ErrorCode 3  
  
-   ErrorCode 4  
  
-   ErrorCode 5  
  
-   接收时间