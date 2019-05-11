---
title: AS2 消息内容状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6244aa59-a80d-450b-ab95-9a5e14c0c40e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89504de79279a42d14061606a31985bed0563635
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358918"
---
# <a name="as2-message-content-status-reports"></a>AS2 消息内容状态报告

## <a name="overview"></a>概述
这些状态报告显示标头和负载的 AS2 消息或 MDN 的上下文属性。 有三个 AS2 消息内容状态报告：  
  
- 消息传输格式报告  
  
- 报告消息解码格式  
  
- Mdn 消息报告  
  
  通过右键单击 AS2/MDN 状态报表中的 AS2 消息，然后单击显示这些报表之一**查看消息传输格式**，**查看消息解码格式**，或**视图 Mdn消息**。 MDN 命令将显示关联的 MDN 的 AS2 消息。  
  
  仅当已选择相应的"在不可否认数据库中的存储区消息"属性的参与方中作为 AS2 消息发送方页或参与方作为 AS2 消息接收方的 AS2 属性对话框的页的相关参与方提供的每个这些报表。 命令以传输格式或 BizTalkDTADb 数据库中的解码的格式存储 AS2 消息或 Mdn。  
  
  此报表使用**消息详细信息属性对话框**(请参阅 UI 详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]) 以显示消息数据，且将信息分到页面：  
  
|第|显示数据|  
|----------|--------------------|  
|**常规**|有关消息的概述信息|  
|**上下文**|与此消息相关联的上下文属性|  
|**消息部件**|此消息中包含的各个文档负载。 为文本或二进制文件，可以查看每个文档：<br /><br /> 文本格式视图显示 AS2 消息或 MDN 的内容中的可读的窗体，如 EDI 文本文件中所示。 此视图显示 AS2 标头、 EDI 尾部和 EDI 负载，使用单独的行上的每个段。<br />的视图二进制格式显示 AS2 消息或 MDN 的内容以非分隔文本格式和 AS2 消息或 MDN 中的每个 ASCII 字符的十六进制表示形式的表。|