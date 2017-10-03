---
title: "为路线服务的订阅服务器使用发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 898b461c-4d0d-4703-a8ca-7f52f3f15f70
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5213b22c1bdfaa505dbf4b62a03095bcec5a1746
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a>为路线服务的订阅服务器使用发送端口
作为示例，了解如何为路线服务的订阅服务器使用发送端口，图 1 显示满足以下条件的消息将拾取动态单向发送端口的筛选器条件：  
  
-   **IsRequestResponse = False**  
  
-   **ServiceName = DynamicTest**  
  
-   **ServiceState = 挂起**  
  
-   **ServiceType = 消息传送**  
  
 ![发送端口](../esb-toolkit/media/ch4-sendport.gif "第四章第 4-发送端口")  
  
 **图 1**  
  
 **发送端口筛选器的示例**  
  
 使用发送端口筛选器表达式来指定它将从通过路线负载增加消息框数据库选取的消息的属性和值集。  
  
> [!NOTE]
>  它使用非常重要的是为特定，尽可能; 专注于筛选条件否则，为拾取意外消息，可能会在大容量环境中引起问题的风险。 架构系统 Properties.xsd 定义订阅的筛选器属性。