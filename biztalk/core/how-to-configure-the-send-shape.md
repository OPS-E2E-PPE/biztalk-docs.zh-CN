---
title: 如何配置发送形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Send shape [Orchestration Designer], delivery notification
- send ports, delivery notifications
- configuring [Orchestration Designer], Send shapes
- Send shape [Orchestration Designer], configuring
- delivery notification
- messages, delivery notification
ms.assetid: 2cf4755b-1cfc-484e-bd9c-c9f3855af556
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbfedd5067be1de443c20ce522cbe30f27395db1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989958"
---
# <a name="how-to-configure-the-send-shape"></a>如何配置发送形状
![](../core/media/ebiz-orch-send.gif "ebiz_orch_send")  
发送形状  
  
 对于已发送的消息，如果希望接收到间接或异步响应（不使用请求-响应端口），则需要将该消息与当前正在运行的业务流程实例相关联，以便响应者可以获得对正确实例的响应。 您可以应用沿用相关集**发送**形状以前初始化的相关，或者你可以应用初始化相关集。 有关详细信息，请参阅[业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。  
  
### <a name="to-configure-a-send-shape"></a>配置发送形状  
  
1.  设置消息和端口操作。  
  
    1.  在“业务流程视图”窗口中，确认您的业务流程具有消息以及为要发送的多部分消息类型定义的端口操作。  
  
    2.  在属性窗口中，选择要从发送的消息**消息**属性下拉列表。  
  
    3.  在属性窗口中，选择将消息从发送端口操作**端口操作**下拉列表。  
  
         -或-  
  
         将从发送连接器拖**发送**发送消息的端口套接字的形状。  
  
2.  指定相关集来限制的消息**发送**将发送形状或初始化相关集中的值。  
  
    1.  你想要使用每个相关集，请检查该相关集从下拉列表**沿用相关集**属性。  
  
    2.  有关每个相关集要用于初始化，检查该相关集从下拉列表**初始化相关集**属性。  
  
## <a name="delivery-notification"></a>送达通知  
 若要测试是否成功通过发送端口发送了某一消息，请完成以下步骤：  
  
1. 将发送形状放置于非事务性、长期或原子作用域中。  
  
2. 在您的发送端口，将 DeliveryNotification 属性设置为**传输**。  
  
3. 将某一 catch 处理程序添加到您的作用域中，以便处理 DeliveryFailureException。  
  
   > [!NOTE]
   >  如果发送形状包含在原子作用域中，将 DeliveryFailureException 仍可以捕获，但需要在外部作用域形状添加事务类型设置为**长期**或**None**. 原子作用域不能直接捕获异常。  
  
   业务流程等待封闭式非原子作用域结束时（或业务流程结束时）的确认，以便接收该确认。  
  
> [!NOTE]
>  这只适用于单向操作；双向（请求-响应）操作中的失败将导致 SoapException（否定确认），即使未设置端口属性时也是如此。  
  
> [!NOTE]
>  对于直接绑定，不支持送达通知。  
  
## <a name="see-also"></a>请参阅  
 [错误处理](../core/error-handling.md)