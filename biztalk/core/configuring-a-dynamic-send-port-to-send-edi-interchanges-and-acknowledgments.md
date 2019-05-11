---
title: 配置动态发送端口以发送 EDI 交换和确认 |Microsoft Docs
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
ms.openlocfilehash: d4883eb78a24eb7ad7254e319c901602dfcb97a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391401"
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a>配置动态发送端口以发送 EDI 交换和确认
若要发送 EDI 确认或交换，可以使用静态发送端口或动态发送端口。 动态发送端口，您可以向多个目标，任何一个发送交换，因为它解析协议，并确定基于 DestinationPartyName 上下文属性中的值的目标地址。  
  
> [!NOTE]
>  如果发送 EDI 交换，它基于收到，一条 XML 消息，并且使用直通接收管道接收该应用程序，您必须升级 DestinationPartyName 上下文属性。 有关详细信息，请参阅[协议解析和架构确定传出 EDI 消息的](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)。  
  
> [!NOTE]
>  如果动态发送端口将发送确认，因为该端口接收交换中的 EDI 拆装器上填充 DestinationPartyName 属性将已进行升级 DestinationPartyName 上下文属性确认。  
  
 若要创建单向动态发送端口，请使用以下配置：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性：常规**|端口类型|动态单向|  
|**发送端口属性：常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性：常规**|发送管道|EdiSend|  
|**文件传输属性：身份验证**|主机没有访问网络共享位置 （使用用户名和密码） 时使用这些凭据|如果需要进行身份验证，设置。|  
|**发送端口属性：筛选器**|属性|BTS.MessageType|  
|**发送端口属性：筛选器**|运算符|==|  
|**发送端口属性：筛选器**|ReplTest1|**对于交换**:<br /><br /> - `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`或<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`或<br /><br /> **对于确认**:<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`或<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`或<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>设置协议属性  
 创建发送端口后，你需要设置发送管道工作所需的协议属性。 这些属性设置中的多个页**协议属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [为 EDI 解决方案配置端口](../core/configuring-ports-for-an-edi-solution.md)