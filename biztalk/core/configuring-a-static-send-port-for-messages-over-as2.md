---
title: 配置静态发送端口通过 AS2 发送的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2708d6a9-b105-42d3-abe3-7085b39da55a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bec915ded1e7e907066aa65a358077316182782
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356365"
---
# <a name="configuring-a-static-send-port-for-messages-over-as2"></a>配置静态发送端口通过 AS2 发送的消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送 AS2 消息通过静态发送端口。 此配置包括创建静态发送端口和配置协议。 如果需要，你将还设置的加密证书用于通过发送端口。  
  
> [!NOTE]
>  可以配置动态发送端口以发送 AS2 消息，而不是静态发送端口。 有关详细信息，请参阅[配置动态发送端口的消息通过 AS2](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)。  
  
 若要发送带有 EDI AS2 消息或非 EDI 消息或者 EDI 确认，请创建要求响应 HTTP 发送端口使用以下配置：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性：常规**|端口类型|-静态要求响应 (如果在请求 MDN**确认 (Mdn)** 页的单向协议选项卡为选中状态)<br /><br /> -静态单向发送端口 (如果在请求 MDN**确认 (Mdn)** 清除页的单向协议选项卡)|  
|**发送端口属性：常规**|传输类型|HTTP<br /><br /> 注意：<br /><br /> 只有 HTTP 适配器可用于传输 EDIINT/AS2 编码的消息。 此传输不会使用非 HTTP 适配器的适配器。|  
|**发送端口属性：常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性：常规**|发送管道|-AS2EdiSend （用于 EDI 编码的消息）<br /><br /> -AS2Send （对于非 EDI 消息）|  
|**发送端口属性：常规**|接收处理程序<br /><br /> (如果在请求 MDN**确认 (Mdn)** 页的单向协议选项卡为选中状态)|BizTalkServerApplication|  
|**发送端口属性：常规**|接收管道<br /><br /> (如果在请求 MDN**确认 (Mdn)** 页的单向协议选项卡为选中状态)|AS2Receive|  
|**HTTP 传输属性**|目标 URL|\<目标 URL 字符串\>|  
|**HTTP 传输属性**|启用 chunked 编码|已清除|  
|**发送端口属性：筛选器**|属性|BTS.MessageType<br /><br /> 注意：<br /><br /> 可以使用各种筛选器表达式，包括使用 BTS。ReceivePortName。<br /><br /> 注意：<br /><br /> 对于非 EDI 消息，您将需要对不同属性进行筛选）|  
|**发送端口属性：筛选器**|运算符|==|  
|**发送端口属性：筛选器**|ReplTest1|- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>` （对于 EDI 消息）<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root` (对于 X12 确认)<br /><br /> -                   `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root` （对于 EDIFACT 确认）|  
|**发送端口属性：证书**|公用名称和指纹|如果使用的加密证书进行出站 AS2 消息，请输入证书名称和指纹。|  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-configure-biztalk-server-to-send-as2-messages-over-a-static-send-port"></a>若要配置 BizTalk Server 以便发送 AS2 消息通过静态发送端口  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建一个静态单向或要求响应发送端口使用上述配置。  
  
2. 在发送端口列表上**发送端口**页中的单向协议选项卡**协议属性**对话框框中，输入静态发送端口的名称。  
  
   > [!NOTE]
   >  设置发送端口后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为出站 AS2 消息执行协议解析。  
  
3. 中**标识符**页的单向协议选项卡的**协议属性**对话框框中，设置 AS2-到属性设置为目标，然后根据需要在设置其他协议属性不同页**协议属性**对话框。  
  
## <a name="functionality"></a>功能  
 发送端口和管道执行以下操作以通过 AS2 发送同步 EDI 或非 EDI 消息或确认并处理返回的 MDN:  
  
-   如果发送 EDI 消息，EDI 消息进行筛选来提取的属性上`BTS.MessageType`设置为中的消息架构`http://schemas.microsoft.com/BizTalk/EDI/X12/2006`（例如，864 消息的 X12_00401_864） 的命名空间。  
  
-   如果发送 EDI 确认，确认进行筛选来提取的属性上`BTS.MessageType`设置为以下控制架构之一：  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` 997 确认  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` 有关 TA1 确认  
  
    -   `http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` CONTRL 确认  
  
-   如果发送非 EDI 消息，则提取使用另一个筛选器的消息。  
  
-   生成一个 AS2 消息。 有关此过程的详细信息，请参阅[生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)。  
  
-   将消息或确认发送到发送端口的目标 URL。  
  
-   如果启用了，接收到的消息或确认的 MDN 响应。 有关此过程的详细信息，请参阅[处理传入 MDN](../core/processing-an-incoming-mdn.md)。  
  
## <a name="see-also"></a>请参阅  
 [为 AS2 解决方案配置端口](../core/configuring-ports-for-an-as2-solution.md)   
 [生成传出 AS2 消息](../core/generating-an-outgoing-as2-message.md)   
 [处理传入 MDN](../core/processing-an-incoming-mdn.md)