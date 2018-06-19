---
title: 配置动态发送端口发送 EDI 交换和确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a124059c-c29c-4a7f-a8a3-13dffc09ae5c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a793fc22394c2b4d294bcd48fae1f9403ae9278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232813"
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a>配置动态发送端口以发送 EDI 交换和确认
若要发送 EDI 确认或交换，可以使用静态发送端口或动态发送端口。 使用动态发送端口，您可以向多个目标中的任何一个发送交换，原因是它将对协议进行解析，并基于 DestinationPartyName 上下文属性中的值确定目标地址。  
  
> [!NOTE]
>  如果您基于收到的 XML 消息发送 EDI 交换，并且使用直通接收管道接收该应用程序，则必须升级 DestinationPartyName 上下文属性。 有关详细信息，请参阅[协议解析和传出的 EDI 消息的架构确定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
> [!NOTE]
>  如果发送确认的将是动态发送端口，则一定已经升级 DestinationPartyName 上下文属性，原因是已接收交换的端口中的 EDI 拆装器将填充确认上的 DestinationPartyName 属性。  
  
 若要创建单向动态发送端口，请使用以下配置：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性： 常规**|端口类型|动态单向|  
|**发送端口属性： 常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性： 常规**|发送管道|EdiSend|  
|**文件传输属性： 身份验证**|在主机无权访问网络共享位置时使用这些凭据（使用“用户名”和“密码”）|如果需要验证，则加以设置。|  
|**发送端口属性： 筛选器**|属性|BTS.MessageType|  
|**发送端口属性： 筛选器**|运算符|==|  
|**发送端口属性： 筛选器**|值|**为交换**:<br /><br /> - `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`或<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`或<br /><br /> **Ack**:<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`或<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`或<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>设置协议属性  
 在创建后发送端口，你需要设置所需的函数到发送管道协议属性。 各种页中设置这些属性**协议属性**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为 EDI 解决方案配置端口](../core/configuring-ports-for-an-edi-solution.md)