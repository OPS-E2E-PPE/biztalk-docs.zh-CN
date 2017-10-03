---
title: "AS2 消息内容的状态报告 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2dadb3231136255dcf532e5054c1a6228880f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-message-content-status-reports"></a>AS2 消息内容状态报告

## <a name="overview"></a>概述
这些状态报告显示 AS2 消息或 MDN 的上下文属性、标头和负载。 总共有三个 AS2 消息内容状态报告：  
  
-   消息连网格式报表  
  
-   消息解码格式报表  
  
-   Mdn 消息报告  
  
 通过右键单击 AS2/MDN 状态报表中，在 AS2 消息，然后单击显示两个报表**视图消息连网格式**，**视图消息解码格式**，或**视图 Mdn消息**。 MDN 命令将显示与 AS2 消息相关联的 MDN。  
  
 每个这些报表是你选择了相应的"不可否认性数据库中的应用商店消息"属性中方为 AS2 消息发送方页或方为 AS2 属性对话框中的 AS2 消息接收方页面相关当事方时才可用。 此命令以传输格式或解码格式将 AS2 消息或 MDN 存储在 BizTalkDTADb 数据库中。  
  
 此报表使用**消息详细信息属性对话框中**(请参阅 UI 详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) 与分到多个页的信息一起显示消息数据：  
  
|第|显示的数据|  
|----------|--------------------|  
|**常规**|有关消息的概述信息|  
|**上下文**|与此消息关联的上下文属性|  
|**消息部分**|此消息中包含的单独文档负载。 每个文档都可被视为文本或二进制文件：<br /><br /> 文本格式视图显示用户可读的窗体，如下所示的 EDI 文本文件中的 AS2 消息或 MDN 的内容。 此视图显示 AS2 标头、EDI 尾部和 EDI 负载，每个分段都位于单独的行中。<br />-二进制格式视图显示非分隔的文本格式和为 MDN 的 AS2 消息中每个 ASCII 字符的十六进制表示的表中的 AS2 消息或 MDN 的内容。|