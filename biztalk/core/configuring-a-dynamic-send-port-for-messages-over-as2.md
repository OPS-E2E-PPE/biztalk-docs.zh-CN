---
title: "通过 AS2 消息配置动态发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246d64e8-70ca-48f4-8b72-d43b0964dbb4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6df553a3f03e9d2e60b78de9877ad6113b04e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-for-messages-over-as2"></a>通过 AS2 消息配置动态发送端口
本主题介绍如何配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以通过动态发送端口发送 AS2 消息。 此配置包括创建动态发送端口和配置后端应用程序以设置相应的上下文属性。 在创建动态发送端口以发送 AS2 消息时，您必须升级特定属性才能使相应发送端口工作。 有关详细信息，请参阅[配置 BizTalk Server 发送 AS2 消息通过动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc)下面。  
  
 动态发送端口允许您在参与方配置未进行硬编码的情况下，将消息发送至多个参与方。 发送消息时要使用的协议和目标通过上下文属性动态确定。 您不必为每个单独的客户创建静态发送端口。  
  
 若要发送带有 EDI 或非 EDI 消息或者 EDI 确认的 AS2 消息，请使用以下配置创建动态响应 HTTP 发送端口：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性： 常规**|端口类型|-动态请求响应 (如果在请求 MDN**确认 (Mdn)**的单向协议选项卡中的页处于选定状态)<br /><br /> -动态单向发送端口 (如果在请求 MDN**确认 (Mdn)**清除的单向协议选项卡中的页)|  
|**发送端口属性： 常规**|发送管道|-AS2EdiSend （对于 EDI 编码消息）<br /><br /> -AS2Send （对于非 EDI 消息）|  
|**发送端口属性： 常规**|接收管道<br /><br /> (如果在请求 MDN**确认 (Mdn)**的单向协议选项卡中的页处于选定状态)|AS2Receive（用于动态要求响应发送端口）|  
|**发送端口属性： 筛选器**|属性|BTS.MessageType|  
|**发送端口属性： 筛选器**|运算符|==|  
|**发送端口属性： 筛选器**|值|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>`（对于 EDI 消息）<br /><br /> - `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root`(对于 X12 确认)<br /><br /> - `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root`（对于 EDIFACT 确认）|  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
##  <a name="BKMK_Proc"></a>若要配置 BizTalk Server 发送 AS2 消息通过动态发送端口  
  
1.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，使用以上配置创建动态单向发送端口（如果未请求 MDN）或动态要求响应发送端口（如果请求了 MDN）。  
  
2.  对于适用于此消息的协议，请设置必需的 AS2 和 EDI 属性。  
  
3.  将下列属性升级到消息上下文：  
  
    -   `BTS.MessageType`  
  
    -   `EdiIntAS.MessageID`  
  
4.  向后端应用程序添加功能以将下列属性写入到消息上下文，并为这些属性设置相应的值：  
  
    -   `EdiIntAS.AS2To`  
  
    -   `BTS.OutboundTransportLocation`  
  
    -   `HTTP.EnableChunkedEncoding`  
  
    -   `BTS.EncryptionCert`  
  
    > [!NOTE]
    >  `AS2To` 上下文属性和 `OutboundTransportLocation` 上下文属性必须写入到消息上下文中，这样才能使动态发送端口正常工作。 端口需要使用 `AS2To` 属性来确定在处理传出消息时要使用的协议，而发送端口需要使用 `OutboundTransportLocation` 属性来确定消息的目标。 有关详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
## <a name="functionality"></a>功能  
 动态发送端口和管道执行以下操作来通过 AS2 发送同步 EDI 或非 EDI 消息或确认并处理返回的 MDN：  
  
-   如果发送一个 EDI 消息，则通过设置为 `BTS.MessageType`（例如，864 消息的架构为 X12_00401_864）的属性 `http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace` 进行筛选来提取 EDI 消息。  
  
-   如果发送 EDI 确认，则通过对设置为以下控制架构中某架构的属性 `BTS.MessageType` 进行筛选来提取确认：  
  
    -   997 确认的 `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root`  
  
    -   TA1 确认的 `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root`  
  
    -   CONTRL 确认的 `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root`  
  
-   如果发送非 EDI 消息，则使用相应的筛选器来提取消息。  
  
-   生成 AS2 消息。 有关此过程的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 根据 URL 的格式（即 http、smtp、ftp 等）确定动态发送端口要使用的传输类型。  
  
-   将消息或确认路由至发送端口的目标 URL。  
  
-   如果已启用而且是要求响应发送端口，则接收对消息或确认的 MDN 响应。 有关此过程的详细信息，请参阅[处理传入 MDN](../core/processing-an-incoming-mdn.md)。  
  
## <a name="see-also"></a>另请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)