---
title: InfoPath 消息模板 |Microsoft Docs
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
ms.openlocfilehash: 2c929e8ef1edcd88c0976d145354779b3e095634
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024467"
---
# <a name="the-infopath-message-template"></a>InfoPath 消息模板
作为 ESB 管理门户中查看 ESB 错误消息的替代方法，用户可以充分利用一个名为 ESB 异常的消息查看器，随一起提供的 Microsoft InfoPath 消息模板[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。  
  
 ESB 异常管理框架可以保留序列化格式，以及 ESB 异常消息查看器模板中，将显示错误消息和它包含原始消息的多个视图中的消息。 ESB 异常消息查看器提供了以下视图：  
  
- 常规视图  
  
- 异常对象视图  
  
- 消息视图 (Messages view)  
  
  图 1 显示了 ESB 异常消息查看器，后者将显示最异常的环境属性的常规视图。  
  
  ![异常消息常规视图](../esb-toolkit/media/ch4-exceptionmessagegeneralview.gif "Ch4-ExceptionMessageGeneralView")  
  
  **图 1**  
  
  **ESB 异常消息查看器显示常规视图**  
  
  图 2 显示了异常对象视图，其中显示的属性和从堆栈跟踪**System.Exception**对象。  
  
  ![异常消息异常对象](../esb-toolkit/media/ch4-exceptionmessageexceptionobject.gif "Ch4-ExceptionMessageExceptionObject")  
  
  **图 2**  
  
  **ESB 异常消息查看器显示异常对象视图**  
  
  图 3 显示了消息视图，它提供的下拉列表，用户可以从中选择从可用的持久消息。 该视图显示持久的消息和 XML 消息内容的上下文属性的值。  
  
  ![异常消息消息视图](../esb-toolkit/media/ch4-exceptionmessagemessagesview.gif "Ch4-ExceptionMessageMessagesView")  
  
  **图 3**  
  
  **ESB 异常消息查看器显示的消息视图**