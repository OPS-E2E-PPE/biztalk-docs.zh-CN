---
title: "通过 AS2 消息配置静态发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2708d6a9-b105-42d3-abe3-7085b39da55a
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 068b7d8295710157af7a8a7358768e85e006beb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-a-static-send-port-for-messages-over-as2"></a>通过 AS2 消息配置静态发送端口
本主题介绍如何配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以通过静态发送端口发送 AS2 消息。 该配置包括创建静态发送端口和配置协议。 如果需要，还将设置要由发送端口使用的加密证书。  
  
> [!NOTE]
>  可以配置动态发送端口而不是静态发送端口以发送 AS2 消息。 有关详细信息，请参阅[配置通过 AS2 消息动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)。  
  
 若要发送带有 EDI 或非 EDI 消息或者 EDI 确认的 AS2 消息，请通过以下配置创建要求响应 HTTP 发送端口：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性： 常规**|端口类型|-静态要求响应 (如果在请求 MDN**确认 (Mdn)**的单向协议选项卡中的页处于选定状态)<br /><br /> -静态单向发送端口 (如果在请求 MDN**确认 (Mdn)**清除的单向协议选项卡中的页)|  
|**发送端口属性： 常规**|传输类型|HTTP<br /><br /> 注意：<br /><br /> 只有 HTTP 适配器可用于传输 EDIINT/AS2 编码消息。 此传输不能用于除 HTTP 适配器之外的其他适配器。|  
|**发送端口属性： 常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性： 常规**|发送管道|-AS2EdiSend （对于 EDI 编码消息）<br /><br /> -AS2Send （对于非 EDI 消息）|  
|**发送端口属性： 常规**|接收处理程序<br /><br /> (如果在请求 MDN**确认 (Mdn)**的单向协议选项卡中的页处于选定状态)|BizTalkServerApplication|  
|**发送端口属性： 常规**|接收管道<br /><br /> (如果在请求 MDN**确认 (Mdn)**的单向协议选项卡中的页处于选定状态)|AS2Receive|  
|**HTTP 传输属性**|目标 URL|\<目标 URL 字符串\>|  
|**HTTP 传输属性**|启用 Chunked 编码|已清除|  
|**发送端口属性： 筛选器**|属性|BTS.MessageType<br /><br /> 注意：<br /><br /> 可以使用各种筛选器表达式，包括使用 BTS.ReceivePortName。<br /><br /> 注意：<br /><br /> 对于非 EDI 消息，必须对不同属性进行筛选。|  
|**发送端口属性： 筛选器**|运算符|==|  
|**发送端口属性： 筛选器**|值|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>`（对于 EDI 消息）<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root`(对于 X12 确认)<br /><br /> -                   `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root`（对于 EDIFACT 确认）|  
|**发送端口属性： 证书**|公用名和指纹|如果对出站 AS2 消息使用加密证书，请输入证书名称和指纹。|  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-biztalk-server-to-send-as2-messages-over-a-static-send-port"></a>将 BizTalk Server 配置为通过静态发送端口发送 AS2 消息  
  
1.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建具有以上配置的静态单向或要求响应发送端口。  
  
2.  上的发送端口列表中**发送端口**页中的单向协议选项卡**协议属性**对话框框中，输入静态发送端口的名称。  
  
    > [!NOTE]
    >  设置发送端口后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将能够为出站 AS2 消息执行协议解析。  
  
3.  在**标识符**的单向协议选项卡页**协议属性**对话框框中，设置 AS2-到目标的属性并根据需要在中将其他协议属性不同页**协议属性**对话框。  
  
## <a name="functionality"></a>功能  
 发送端口和管道执行以下操作可通过 AS2 发送同步 EDI 或非 EDI 消息或确认并处理返回的 MDN：  
  
-   如果发送一个 EDI 消息，则通过设置为 `BTS.MessageType` 命名空间（例如，864 消息的架构为 X12_00401_864）的属性 `http://schemas.microsoft.com/BizTalk/EDI/X12/2006` 进行筛选来提取 EDI 消息。  
  
-   如果发送 EDI 确认，则通过对设置为以下控制架构中某架构的属性 `BTS.MessageType` 进行筛选来提取确认：  
  
    -   997 确认的 `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root`  
  
    -   TA1 确认的 `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root`  
  
    -   CONTRL 确认的 `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root`  
  
-   如果发送非 EDI 消息，则使用其他筛选器提取消息。  
  
-   生成 AS2 消息。 有关此过程的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
-   将消息或确认发送至发送端口的目标 URL。  
  
-   如果已启用，将接收对消息或确认的 MDN 响应。 有关此过程的详细信息，请参阅[处理传入 MDN](../core/processing-an-incoming-mdn.md)。  
  
## <a name="see-also"></a>另请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)   
 [生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)   
 [处理传入 MDN](../core/processing-an-incoming-mdn.md)