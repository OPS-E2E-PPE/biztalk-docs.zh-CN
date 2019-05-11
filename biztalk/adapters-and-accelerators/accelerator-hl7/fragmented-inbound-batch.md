---
title: 零碎的入站的批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac8e0d99bfa9ea8696a7cd9f6eeed8a6be16006d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267815"
---
# <a name="fragmented-inbound-batch"></a>零碎的入站的批处理
你可以配置[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]若要接收消息批，从批处理中提取消息，然后将各个消息路由到目标系统。 如果启用碎片，为单个消息; 的入站的批处理片段否则为批处理是处理，并作为单个 'batch' 或交换路由。 BTAHL7 配置资源管理器用于启用批处理。 有关启用批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。  
  
 下面介绍典型零碎的入站的批处理方案：  
  
1.  在系统 A 上运行的业务线应用程序将消息批发送到 BTAHL7。  
  
     批处理消息，可以在两个不同的格式。 BTAHL7 可以处理以下格式：  
  
    -   格式 1:包括一个文件标头和尾部 (FHS/FTS) 对一个或多个批处理标头和尾部 (BHS/BTS)。  
  
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
  
    -   格式 2:不包含 HL7 定义文件和批处理包装器，并挂起一系列是流中的消息。  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  BTAHL7 批中创建各条消息，然后验证对相应架构的单个消息。  
  
3.  BTAHL7 将单独的确认消息发送到系统 A，从批处理中提取每条消息。  
  
4.  BTAHL7 将单个消息路由到目标系统基于各条消息，而不是消息批处理标头中的路由信息。  
  
    > [!NOTE]
    >  BTAHL7 不会验证 batch 和文件的标头/尾部时**FHS3**字段 （发送方） 包含贸易合作伙伴的已启用的碎片。  
  
## <a name="see-also"></a>请参阅  
 [配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)