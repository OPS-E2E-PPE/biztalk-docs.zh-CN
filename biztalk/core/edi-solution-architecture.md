---
title: "EDI 解决方案体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55709a89-7706-4c64-ada3-16951951c943
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42afbb604a8cef1387418e175a39150f0182c607
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-solution-architecture"></a>EDI 解决方案体系结构
电子数据交换 (EDI) 是业务实体以电子方式交换数据的最常见方式之一。 使用 EDI 必须了解消息语法和标准（包括 ANSI X12 和 UN/EDIFACT）、消息传送协议以及传输。 以下是 EDI 消息传送的一些特性：  
  
-   EDI 消息传送协议可确保数据始终如期到达，并自动检测和报告损坏的数据或不正确的数据。  
  
-   EDI 机制通常指定数据聚合方案（批处理）。  
  
-   用户常常通过实现部分 EDI 准则或特定 EDI 准则来自定义 EDI 文档定义。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用特定于 EDI 的接收和发送管道处理 EDI 消息，这些管道可以对 EDI 消息进行分析和序列化。 本节介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 EDI 解决方案的体系结构，包括接收端和发送端处理、消息验证和状态报告的细节。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [EDI 消息传递](../core/edi-messaging.md)  
  
-   [协议在 EDI 处理过程中的角色](../core/the-role-of-agreements-in-edi-processing.md)  
  
-   [BizTalk Server 接收 EDI 消息的方式](../core/how-biztalk-server-receives-edi-messages.md)  
  
-   [BizTalk Server 将 EDI 消息的发送](../core/how-biztalk-server-sends-edi-messages.md)  
  
-   [EDI 消息验证](../core/edi-message-validation.md)  
  
-   [使用 XML 工具扩展](../core/using-the-xml-tool-extensions.md)