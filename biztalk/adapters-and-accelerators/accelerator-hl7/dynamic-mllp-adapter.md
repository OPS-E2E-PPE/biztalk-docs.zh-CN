---
title: "动态 MLLP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7d1d7046135de1dc1837d1fb8961ef440b5009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-mllp-adapter"></a>动态 MLLP 适配器
从开始[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]，可以在运行时使用单向或双向 （请求-响应） 发送端口配置 MLLP 适配器属性。  
  
## <a name="dynamic-properties"></a>动态属性  
 以下属性位于**GlobalPropertySchemas**命名空间：  
  
|属性|Description|  
|--------------|-----------------|  
|消息 (MLLP.acceptableACKCodes) ="所有确认代码";|值包括：<br /><br /> -所有 ACK 代码<br />-AA 和 CA<br />-AA、 CA、 遍历和 CE<br />-AA、 CA、 AR 和 CR<br /><br /> 它类似于**可接受的 ACK 代码**静态 MLLP 发送端口中的属性。|  
|消息 (MLLP。CarriageReturn) ="0 d";|ASCII 回车符|  
|消息 (MLLP.endBlockDelimiter) ="1 c";|ASCII 结束块字符|  
|消息 (MLLP.startBlockDelimiter) ="0b";|ASCII 起始块字符|  
|消息 (MLLP.timeout) ="60000";|时间段段后 BTAHL7 服务器将会超时的非活动发送套接字 （0 表示无超时）|  
|SendPortName(Microsoft.XLANGs.BaseTypes.Address) ="127.0.0.1:11000";|地址和端口用于路由消息|  
|SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) ="MLLP";|类型的适配器 (MLLP)|  
  
## <a name="additional"></a>补充说明  
  
-   业务流程中创建 HL7，多部分消息时要按照顺序在此创建的消息部分：  
  
    1.  MSH 段  
  
    2.  BodySegments  
  
    3.  ZSegments  
  
     如果你在不同的顺序指定的消息部分，出现以下错误：  
  
     WrongBodyPartException  
  
-   在业务流程，以支持动态路由指定的适配器路由属性。  
  
## <a name="see-also"></a>另请参阅  
 [配置参数发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [处理 MLLP 编码消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)