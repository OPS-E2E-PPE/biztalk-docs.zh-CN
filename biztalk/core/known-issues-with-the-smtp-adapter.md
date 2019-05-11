---
title: 使用 SMTP 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b530e39e-c4e7-4b98-be0b-4d02eb2e8dc7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4184d159b75d7a83c32d5d76135bf7cb2215158
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380799"
---
# <a name="known-issues-with-the-smtp-adapter"></a>SMTP 适配器的已知的问题
本部分包含可能帮助您避免错误的信息。  
  
## <a name="known-issues"></a>已知问题  
  
#### <a name="error-in-the-biztalk-server-application-log-if-emailbodytextcharset-is-not-defined"></a>如果未定义 EmailBodyTextCharset 时 BizTalk Server 应用程序日志中的错误  
  
##### <a name="problem"></a>问题  
 如果未定义 EmailBodyTextCharset 并且在 BizTalk Server 应用程序日志中生成类似如下的错误在 BizTalk Server 应用程序日志中生成错误：  
  
```  
Event Type:Error  
Event Source:BizTalk Server 2009  
Event Category:BizTalk Server 2009   
Event ID:5754  
Date:9/1/2006  
Time:10:50:11 AM  
User:N/A  
Computer:TEST2006  
Description:  
A message sent to adapter "SMTP" on send port "TIE Test_1.0.0.0_TIE_Test.TieRespTest_Email_Port_4f4f8f4101d5615a" with URI "mailto:approver@BTS2006.com" is suspended.   
Error details: Unknown Error Description   
MessageId: {3F12EBE1-1CDA-44FE-85FE-C2CB8228F287}  
InstanceID: {0616E750-22FF-4380-B413-C94718421340}  
```  
  
##### <a name="cause"></a>原因  
 必须将值设置为**EmailBodyTextCharset**参数。  
  
##### <a name="resolution"></a>解决方法  
 为指定值**EmailBodyTextCharset**参数。  
  
## <a name="see-also"></a>请参阅  
 [SMTP 适配器故障排除](../core/troubleshooting-the-smtp-adapter.md)