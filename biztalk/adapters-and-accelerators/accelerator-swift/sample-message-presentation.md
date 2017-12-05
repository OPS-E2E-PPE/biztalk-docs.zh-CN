---
title: "示例消息演示文稿 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, SWIFT message block
- SWIFT messages, message block example
ms.assetid: 3136a7da-658d-4100-bbe5-2186ee8bafd1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8a3d03e35f6184e6aed6ba4af71e01a9b65e342
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="sample-message-presentation"></a>示例消息演示文稿
下表显示 SWIFT 消息块布局的示例。  
  
|分块|示例|  
|-----------|-------------|  
|**阻止 1**基本标头|{1:F01BCITITMMAXXX0012000123}|  
|**阻止 2** (I) 应用程序标头的输入 （SWIFT)<br /><br /> 或<br /><br /> **阻止 2** （从 SWIFT) (O) 应用程序标头输出|{2:I103VBOEATWWXXXXN}或者 {2:O1030840010605BNPAFRPPAXXX00120078960106051051U3|  
|**块 3**用户标头|{3: {108:BCITITMMA950906}}|  
|**阻止 4**文本|{4:\<CRLF\> : 20:1234567890\<CRLF\> : 23B:CRED\<CRLF\> : 32A:010605GBP45000，\<CRLF\> : 33B:GBP45000，\<CRLF\> : 50K:MASTERS 导入\<CRLF\> RUE DES ARBRES 119\<CRLF\> CAMBRAI\<CRLF\> : 52A:BNPAFRPPCAM\<CRLF\> : 53A:POCIITMM680\<CRLF\> : 57A:BCITITMM680\<CRLF\> : 59: / P03452032022819 30\<CRLF\>总计导入\<CRLF\> PESCARA\<CRLF\> : 70: / RFB/清单 5591\<CRLF\> : 71A:SHA\<CRLF\> -}|  
|**阻止 5**拖车安排|{5: {MAC: 12345678} {CHK:123456789ABC}}|  
  
## <a name="see-also"></a>另请参阅  
 [SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/swift-schemas.md)