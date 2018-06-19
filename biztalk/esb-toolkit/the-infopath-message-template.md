---
title: InfoPath 消息模板 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb055b1-8480-44dd-8739-f2981bca63c3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b8ec04d16da25f39060540aa8a8205421397d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295141"
---
# <a name="the-infopath-message-template"></a>InfoPath 消息模板
作为在 ESB 管理门户中查看 ESB 错误消息的替代方法，用户可以利用的名为 ESB 异常的消息查看器，使用提供的 Microsoft InfoPath 消息模板[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 ESB 异常管理框架可以保留在序列化格式，以及 ESB 异常消息查看器模板中，将显示错误消息和其中包含的原始消息的多个视图中的消息。 ESB 异常消息查看器提供以下视图：  
  
-   常规视图  
  
-   异常对象视图  
  
-   消息视图 (Messages view)  
  
 图 1 显示常规 ESB 异常消息查看器的视图，其中显示了最环境属性的异常。  
  
 ![异常消息常规视图](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "第四章第 4 ExceptionMessageGeneralView")  
  
 **图 1**  
  
 **显示常规视图的 ESB 异常消息查看器**  
  
 图 2 显示异常对象视图中，显示的属性和堆栈跟踪从**System.Exception**对象。  
  
 ![异常消息异常对象](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "第四章第 4 ExceptionMessageExceptionObject")  
  
 **图 2**  
  
 **显示异常对象视图的 ESB 异常消息查看器**  
  
 图 3 显示的消息视图中，它提供，用户可以从中选择可用的持久消息从下拉列表。 该视图显示持久化的消息和 XML 消息内容的上下文属性的值。  
  
 ![异常消息的消息视图](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "第四章第 4 ExceptionMessageMessagesView")  
  
 **图 3**  
  
 **ESB 异常消息查看器显示的消息视图**