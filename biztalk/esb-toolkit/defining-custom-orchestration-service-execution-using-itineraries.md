---
title: 定义自定义业务流程服务执行使用路线 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5c475178865f0ebe990dd75c87b29e75ab47753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394645"
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a>定义自定义业务流程服务执行使用路线
在此用例，提交以进行处理的消息包含描述的服务执行，而其分辨率要求列表的路线 SOAP 标头。 路线指定一个或多个自定义业务流程或进程通过该消息将直接处理周期。 自定义业务流程具有完全控制路线和其他自定义属性在消息上下文中公开。 （可选） 路线可能包含确定转换需求和消息的终结点的动态解析信息。 图 1 显示了该过程的示意图。  
  
 ![定义自定义业务流程](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3-DefiningCustomOrchestration")  
  
 **图 1**  
  
 **使用路线定义自定义业务流程服务执行**  
  
 路线接入点示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。 它演示如何创建路线解析、 路由和服务调用说明中包含的一系列的路线定义 ESB 和 BizTalk Server 将如何处理输入的消息的步骤。 单向和请求-响应示例包括在内。  
  
 有关详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。