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
ms.openlocfilehash: d6c4ce03c9188a03b47cc2fbe3f67a8be163acdc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009974"
---
# <a name="edi-solution-architecture"></a>EDI 解决方案体系结构
电子数据交换 (EDI) 是业务实体以电子方式交换数据的最常见方式之一。 使用 EDI 必须了解消息语法和标准（包括 ANSI X12 和 UN/EDIFACT）、消息传送协议以及传输。 以下是 EDI 消息传送的一些特性：  
  
- EDI 消息传送协议可确保数据始终如期到达，并自动检测和报告损坏的数据或不正确的数据。  
  
- EDI 机制通常指定数据聚合方案（批处理）。  
  
- 用户常常通过实现部分 EDI 准则或特定 EDI 准则来自定义 EDI 文档定义。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用特定于 EDI 的接收和发送管道处理 EDI 消息，这些管道可以对 EDI 消息进行分析和序列化。 本节介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 EDI 解决方案的体系结构，包括接收端和发送端处理、消息验证和状态报告的细节。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [EDI 消息传送](../core/edi-messaging.md)  
  
-   [协议在 EDI 处理中的角色](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [EDI 消息验证](../core/edi-message-validation.md)  
  
-   [使用 XML 工具扩展](../core/using-the-xml-tool-extensions.md)