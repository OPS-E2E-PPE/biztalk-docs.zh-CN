---
title: 创建路线订阅方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84a76aeb-8d40-490a-8ae6-7abfdd2d2573
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2998b47ec136414af896cadb40b8336fe41ef2ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394667"
---
# <a name="creating-itinerary-subscribers"></a>创建路线订阅方
BizTalk Server 会自动将发布到 Messagebox 数据库中; 通过接收管道到达的消息这会使消息准备好进行提取相关的订阅服务器。 此种去耦的方法是首选的方法来开发 BizTalk 解决方案，因为它提供了最大的灵活性、 扩展性好，并使用发布-订阅机制。  
  
 有两种方法来创建路线服务订阅方：  
  
-   [将发送端口用作路线服务订阅方](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)  
  
-   [将业务流程用作路线服务订阅方](../esb-toolkit/using-an-orchestration-as-an-itinerary-service-subscriber.md)