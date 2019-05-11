---
title: 发送端口用作路线服务订阅方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 898b461c-4d0d-4703-a8ca-7f52f3f15f70
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ab596b01c515fad670b959c00e0571b5e9962c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396475"
---
# <a name="using-a-send-port-as-an-itinerary-service-subscriber"></a>发送端口用作路线服务订阅方
为举例说明如何将发送端口用作路线服务订阅方，图 1 显示了满足以下条件的消息会选取一个动态单向发送端口的筛选器条件：  
  
- **IsRequestResponse = False**  
  
- **ServiceName = DynamicTest**  
  
- **ServiceState = Pending**  
  
- **ServiceType = Messaging**  
  
  ![发送端口](../esb-toolkit/media/ch4-sendport.gif "Ch4-SendPort")  
  
  **图 1**  
  
  **发送端口筛选器的示例**  
  
  使用发送端口筛选器表达式来指定它将从 Messagebox 数据库路线接入点通过选取的消息的属性和值集。  
  
> [!NOTE]
>  务必要使用的是为特定且其焦点位于尽可能; 筛选条件否则，为存在风险的意外消息，可能会在大容量环境中引起问题的提取。 架构系统 Properties.xsd 定义订阅的筛选器属性。