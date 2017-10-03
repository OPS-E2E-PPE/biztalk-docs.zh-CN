---
title: "分片入站的批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0807bbe83ea2f477a7e1625488ebbecf578f3adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fragmented-inbound-batch"></a>零碎的入站的批处理
你可以配置[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]若要接收消息批，从该批处理，提取消息，然后单个消息路由到目标系统。 如果启用碎片，到单个消息的入站的批处理片段否则为批处理得到处理，并作为单个 'batch' 或交换路由。 BTAHL7 配置资源管理器用于启用批处理。 有关启用批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。  
  
 下面介绍典型零碎的入站的批处理方案：  
  
1.  运行系统 A 的业务线应用程序将消息批发送到 BTAHL7。  
  
     批处理消息可以在两个不同的格式。 BTAHL7 可以处理以下格式：  
  
    -   格式 1： 包含一个文件标头和尾部 (FHS/FT) 对一个或多个批处理标头和尾部 (BHS/BTS)。  
  
        ```  
        FHS  
        BHS  
        MSH  
        .............  
        MSH  
        ...........  
        BTS  
        BHS  
        MSH  
        ..............  
        MSH  
        ...............  
        BTS  
        FTS  
        ```  
  
    -   格式 2： 不包含 HL7 定义文件和批处理包装器，并挂起一系列流中的消息。  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  BTAHL7 批次中创建单个消息，然后验证针对相应架构的单个消息。  
  
3.  BTAHL7 批次中提取每条消息将单独的确认消息发送到系统 A。  
  
4.  BTAHL7 将各条消息路由到目标系统基于各条消息，而不是消息批处理标头中的路由信息。  
  
    > [!NOTE]
    >  BTAHL7 不会验证批处理和文件标头/拖车安排时**FHS3**字段 （发送方） 包含已启用的碎片的贸易合作伙伴。  
  
## <a name="see-also"></a>另请参阅  
 [配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)