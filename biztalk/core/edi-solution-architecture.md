---
title: EDI 解决方案体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9df4d308af97e0fcccf52d2c6f42660afa7cf079
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350255"
---
# <a name="edi-solution-architecture"></a>EDI 解决方案体系结构
电子数据交换 (EDI) 是通过业务实体数据以电子方式交换的最常见方式之一。 使用 EDI 必须了解消息语法和标准 （包括 ANSI X12 和 UN/EDIFACT），消息传送协议以及传输。 EDI 消息传送的特征如下：  
  
- EDI 消息传送协议可确保数据始终如期到达，并损坏或不正确的数据自动检测和报告。  
  
- EDI 机制通常指定数据聚合方案 （批处理）。  
  
- 用户通常通过实现子集或特定 EDI 准则来自定义 EDI 文档定义。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理 EDI 消息使用接收和发送管道特定于 EDI 的可以解析和序列化 EDI 消息。 本部分介绍的 EDI 解决方案体系结构上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，包括接收端和发送端处理、 消息验证和状态报告的细节。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [EDI 消息传送](../core/edi-messaging.md)  
  
-   [协议在 EDI 处理中的角色](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [EDI 消息验证](../core/edi-message-validation.md)  
  
-   [使用 XML 工具扩展](../core/using-the-xml-tool-extensions.md)