---
title: 配置动态发送端口通过 AS2 发送的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 246d64e8-70ca-48f4-8b72-d43b0964dbb4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1952947120a6f90310244f7ef17ee6fc5810d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356392"
---
# <a name="configuring-a-dynamic-send-port-for-messages-over-as2"></a>配置动态发送端口通过 AS2 发送的消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送 AS2 消息通过动态发送端口。 此配置包括创建动态发送端口和后端应用程序配置为设置相应的上下文属性。 在创建动态发送端口以发送 AS2 消息时，必须升级为发送端口，若要运行特定属性。 有关详细信息，请参阅[配置 BizTalk Server 以便发送 AS2 消息通过动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc)下面。  
  
 动态发送端口，您可以将消息发送到多个参与方，无需进行硬编码的参与方配置。 用于发送消息的协议和目标通过上下文属性动态确定。 无需为每个单独的客户创建静态发送端口。  
  
 若要发送带有 EDI AS2 消息或非 EDI 消息或者 EDI 确认，创建动态响应 HTTP 发送端口使用以下配置：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性：常规**|端口类型|-动态要求响应 (如果在请求 MDN**确认 (Mdn)** 页的单向协议选项卡为选中状态)<br /><br /> -动态单向发送端口 (如果在请求 MDN**确认 (Mdn)** 清除页的单向协议选项卡)|  
|**发送端口属性：常规**|发送管道|-AS2EdiSend （用于 EDI 编码的消息）<br /><br /> -AS2Send （对于非 EDI 消息）|  
|**发送端口属性：常规**|接收管道<br /><br /> (如果在请求 MDN**确认 (Mdn)** 页的单向协议选项卡为选中状态)|AS2Receive （用于动态要求响应发送端口）|  
|**发送端口属性：筛选器**|属性|BTS.MessageType|  
|**发送端口属性：筛选器**|运算符|==|  
|**发送端口属性：筛选器**|ReplTest1|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>` （对于 EDI 消息）<br /><br /> - `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root` (对于 X12 确认)<br /><br /> - `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root` （对于 EDIFACT 确认）|  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
##  <a name="BKMK_Proc"></a> 若要配置 BizTalk Server 以便发送 AS2 消息通过动态发送端口  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建动态单向发送端口 （如果未请求 MDN） 或动态要求响应发送端口 （如果请求一个 MDN） 使用上述配置。  
  
2. 适用于此消息的协议，将设置所需的 AS2 和 EDI 属性。  
  
3. 升级到消息上下文的以下属性：  
  
   -   `BTS.MessageType`  
  
   -   `EdiIntAS.MessageID`  
  
4. 将功能添加到后端应用程序要写入到消息上下文中，将其设置为适当的值的以下属性：  
  
   -   `EdiIntAS.AS2To`  
  
   -   `BTS.OutboundTransportLocation`  
  
   -   `HTTP.EnableChunkedEncoding`  
  
   -   `BTS.EncryptionCert`  
  
   > [!NOTE]
   >  `AS2To`上下文属性和`OutboundTransportLocation`上下文属性必须写入到消息上下文的动态发送端口才能正常工作。 `AS2To`属性是必需的端口，以确定在处理传出消息要使用的协议和`OutboundTransportLocation`属性是必需的发送端口，以确定消息的目标。 有关详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
## <a name="functionality"></a>功能  
 动态发送端口和管道执行以下操作以通过 AS2 发送同步 EDI 或非 EDI 消息或确认并处理返回的 MDN:  
  
- 如果发送 EDI 消息，EDI 消息进行筛选来提取的属性上`BTS.MessageType`设置为中的消息架构`http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace`(例如，864 消息的为 X12_00401_864)。  
  
- 如果发送 EDI 确认，确认进行筛选来提取的属性上`BTS.MessageType`设置为以下控制架构之一：  
  
  -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` 997 确认  
  
  -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` 有关 TA1 确认  
  
  -   `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` CONTRL 确认  
  
- 如果发送非 EDI 消息，则提取使用相应的筛选器的消息。  
  
- 生成一个 AS2 消息。 有关此过程的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
  > [!NOTE]
  >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 确定要从 URL，即 http、 smtp、 ftp 等格式动态发送端口要使用的传输类型。  
  
- 将消息或确认路由到发送端口的目标 URL。  
  
- 如果启用，并且要求响应发送端口接收到的消息或确认的 MDN 响应。 有关此过程的详细信息，请参阅[处理传入 MDN](../core/processing-an-incoming-mdn.md)。  
  
## <a name="see-also"></a>请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)