---
title: 配置静态发送端口以发送 EDI 交换和确认 |Microsoft Docs
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
ms.openlocfilehash: d5c9e3e1648d570c41567339617c9a0b20ad8d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391372"
---
# <a name="configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments"></a>配置静态发送端口以发送 EDI 交换和确认
若要发送 EDI 确认或交换，可以使用静态单向发送端口或静态要求响应 （双向） 发送端口。  
  
-   创建一个单向发送端口，如果您还将创建一个单向接收端口以接收 EDI 确认 （如果已启用）。  
  
-   创建要求响应发送端口以发送 EDI 交换和通过关联的接收管道接收 EDI 确认 （如果启用）。  
  
## <a name="configuring-a-static-one-way-send-port"></a>配置一个静态单向发送端口  
 若要创建静态单向发送端口以发送 EDI 交换和确认，请使用以下配置：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性：常规**|端口类型|静态单向|  
|**发送端口属性：常规**|传输类型|可以是许多类型，包括文件、 FTP、 HTTP、 MQSeries、 MSMQ、 SMTP、 SOAP、 SQL、 WCF 类型和 Windows SharePoint Services。|  
|**发送端口属性：常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性：常规**|发送管道|EdiSend|  
|**传输属性：验证 （适用于 FILE 传输类型）**|主机没有访问网络共享位置 （使用用户名和密码） 时使用这些凭据|如果需要进行身份验证，设置。|  
|**发送端口属性：筛选器**|属性|BTS.MessageType<br /><br /> 注意：<br /><br /> 此外可以使用 BTS。ReceivePortName 或其他升级的属性。|  
|**发送端口属性：筛选器**|运算符|==|  
|**发送端口属性：筛选器**|ReplTest1|**使用 BTS。对于交换 MessageType:**<br /><br /> - **对于 X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`，或<br /><br /> - **对于 EDIFACT**: `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **使用 BTS。对于确认 MessageType**:<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`，或<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`，或<br /><br /> -                     **对于 EDIFACT**: `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="configuring-a-static-solicit-response-send-port"></a>配置静态要求响应发送端口  
 若要创建静态要求-响应 （双向） 发送端口以发送 EDI 交换和确认，请使用以下配置：  
  
|Location|属性|设置|  
|--------------|--------------|-------------|  
|**发送端口属性：常规**|端口类型|静态要求响应|  
|**发送端口属性：常规**|传输类型|可以是许多类型，包括 HTTP、 MQSeries、 MSMQ、 SOAP、 SQL 和 WCF 类型。 不能为文件、 FTP、 SMTP 或 Windows SharePoint Services。|  
|**发送端口属性：常规**|发送处理程序|BizTalkServerApplication|  
|**发送端口属性：常规**|发送管道|EdiSend|  
|**发送端口属性：常规**|接收管道|EdiReceive|  
|**传输属性：验证 （适用于 HTTP 传输类型）**|主机没有访问网络共享位置 （使用用户名和密码） 时使用这些凭据|如果需要进行身份验证，设置。|  
|**发送端口属性：筛选器**|属性|BTS.MessageType<br /><br /> 注意：<br /><br /> 此外可以使用 BTS。ReceivePortName 或其他升级的属性。|  
|**发送端口属性：筛选器**|运算符|==|  
|**发送端口属性：筛选器**|ReplTest1|**使用 BTS。对于交换 MessageType:**<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`，或<br /><br /> -                     **对于 EDIFACT**: `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **使用 BTS。对于确认 MessageType**:<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`，或<br /><br /> -                     **对于 X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`，或<br /><br /> -                     **对于 EDIFACT**: `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>设置协议属性  
 创建发送端口后，你需要设置发送管道工作所需的协议属性。 这些属性设置中的多个页**协议属性**对话框。  
  
## <a name="see-also"></a>请参阅  
 [为 EDI 解决方案配置端口](../core/configuring-ports-for-an-edi-solution.md)   
 [如何创建发送端口](../core/how-to-create-a-send-port2.md)