---
title: 配置静态发送端口发送 EDI 交换和确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b432c5e-ea0c-4174-bb4a-958b061c1827
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8645cd36447c814a5c43534e6c01de51e4be52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234453"
---
# <a name="configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments"></a>配置静态发送端口以发送 EDI 交换和确认
若要发送 EDI 确认或交换，可以使用静态单向发送端口或静态要求响应（双向）发送端口。  
  
-   如果还要创建单向接收端口以接收 EDI 确认（如果启用），则创建单向发送端口。  
  
-   创建要求响应发送端口可发送 EDI 交换并在关联的接收管道上接收 EDI 确认（如果启用）。  
  
## <a name="configuring-a-static-one-way-send-port"></a>配置静态单向发送端口  
 若要创建静态单向发送端口以发送 EDI 交换和确认，请使用以下配置：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性： 常规**|端口类型|静态单向|  
|**发送端口属性： 常规**|传输类型|可以是许多类型，包括 FILE、FTP、HTTP、MQSeries、MSMQ、SMTP、SOAP、SQL、WCF 类型和 Windows SharePoint Services。|  
|**发送端口属性： 常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性： 常规**|发送管道|EdiSend|  
|**传输属性： 身份验证 （用于文件传输类型）**|在主机无权访问网络共享位置时使用这些凭据（使用“用户名”和“密码”）|如果需要验证，则加以设置。|  
|**发送端口属性： 筛选器**|属性|BTS.MessageType<br /><br /> 注意：<br /><br /> 此外，还可以使用 BTS.ReceivePortName 或其他升级的属性。|  
|**发送端口属性： 筛选器**|运算符|==|  
|**发送端口属性： 筛选器**|值|**使用 BTS。交换的的 MessageType:**<br /><br /> - **对于 X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`，或<br /><br /> - **对于 EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **使用 BTS。MessageType 的 Ack**:<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`，或<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`，或<br /><br /> -                     **对于 EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="configuring-a-static-solicit-response-send-port"></a>配置静态要求响应发送端口  
 若要创建静态要求响应（双向）发送端口以发送 EDI 交换和确认，请使用以下配置：  
  
|位置|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性： 常规**|端口类型|静态-请求作出响应|  
|**发送端口属性： 常规**|传输类型|可以是许多类型，包括 HTTP、MQSeries、MSMQ、SOAP、SQL 和 WCF 类型。 不能是 FILE、FTP、SMTP 或 Windows SharePoint Services。|  
|**发送端口属性： 常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性： 常规**|发送管道|EdiSend|  
|**发送端口属性： 常规**|接收管道|EdiReceive|  
|**传输属性： 身份验证 （对于 HTTP 传输类型）**|在主机无权访问网络共享位置时使用这些凭据（使用“用户名”和“密码”）|如果需要验证，则加以设置。|  
|**发送端口属性： 筛选器**|属性|BTS.MessageType<br /><br /> 注意：<br /><br /> 此外，还可以使用 BTS.ReceivePortName 或其他升级的属性。|  
|**发送端口属性： 筛选器**|运算符|==|  
|**发送端口属性： 筛选器**|值|**使用 BTS。交换的的 MessageType:**<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`，或<br /><br /> -                     **对于 EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **使用 BTS。MessageType 的 Ack**:<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`，或<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`，或<br /><br /> -                     **对于 EDIFACT**:`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>设置协议属性  
 在创建后发送端口，你需要设置所需的函数到发送管道协议属性。 各种页中设置这些属性**协议属性**对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为 EDI 解决方案配置端口](../core/configuring-ports-for-an-edi-solution.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)