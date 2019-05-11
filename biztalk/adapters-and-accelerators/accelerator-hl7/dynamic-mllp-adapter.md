---
title: 动态 MLLP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d603af67031c0e0429a362c6a3681f94f812b503
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258969"
---
# <a name="dynamic-mllp-adapter"></a>动态 MLLP 适配器
从开始[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]，可以在运行时使用的单向或双向 （请求-响应） 发送端口配置 MLLP 适配器属性。  
  
## <a name="dynamic-properties"></a>动态属性  
 以下属性以**GlobalPropertySchemas**命名空间：  
  
|属性|Description|  
|--------------|-----------------|  
|Message(MLLP.acceptableACKCodes)=”All ACK Codes”;|值包括：<br /><br /> -所有确认代码<br />-AA 和 CA<br />-AA、 CA、 AE 和 CE<br />-AA、 CA、 AR 和 CR<br /><br /> 它类似于**接受确认代码**中静态 MLLP 发送端口属性。|  
|Message(MLLP.CarriageReturn)=”0d”;|ASCII 回车符|  
|Message(MLLP.endBlockDelimiter)=”1c”;|ASCII 结束块字符|  
|Message(MLLP.startBlockDelimiter)=”0b”;|ASCII 开始块字符|  
|Message(MLLP.timeout)=”60000”;|超过这个有效期之后 BTAHL7 服务器将会超时的非活动发送套接字 （0 表示无超时）|  
|SendPortName(Microsoft.XLANGs.BaseTypes.Address) = “127.0.0.1:11000”;|地址和端口将消息路由|  
|SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = “MLLP”;|类型的适配器 (MLLP)|  
  
## <a name="additional"></a>其他  
  
- 时为 HL7 中创建业务流程中的多部分消息，要按照顺序在此创建消息部分：  
  
  1. MSH 段  
  
  2. BodySegments  
  
  3. ZSegments  
  
     如果在不同的顺序中指定的消息部分，将发生以下错误：  
  
     WrongBodyPartException  
  
- 适配器路由属性可以指定在业务流程，以支持动态路由。  
  
## <a name="see-also"></a>请参阅  
 [配置参数，以便进行发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [处理用 MLLP 编码的消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)