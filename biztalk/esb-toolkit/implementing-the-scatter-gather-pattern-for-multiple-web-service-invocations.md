---
title: 对多个 Web 服务调用实施散播-聚集模式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2682418922c17fd4c6fbe8a6bffbac51051f7841
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010654"
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a>对多个 Web 服务调用实施散播-聚集模式
在使用此种情况下，消息包含指定多个 BizTalk Server 应访问的外部服务路线服务步骤。 它使用动态的解决方法来确定服务位置和终结点和任何可选的 BizTalk 服务图对于转换返回的数据。 实现此服务业务流程执行转换和调用，并且所有服务调用以异步方式都发生。 所有服务调用都完成后，路线服务将响应聚合为单个响应消息，并将消息发送到客户端通过动态分配的终结点。 图 1 说明此用例。  
  
 ![实现散点图收集模式](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3 ImplementingScatter")  
  
 **图 1**  
  
 **实现多个 Web 服务调用的散播-聚集模式**  
  
 散播-聚集示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。  
  
 有关详细信息，请参阅[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)。