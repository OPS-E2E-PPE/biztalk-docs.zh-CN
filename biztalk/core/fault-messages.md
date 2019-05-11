---
title: 错误消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
- ports, error messages
- Catch Exception block [Orchestration Designer], error messages
- error messages, receiving
- messages, errors
- error messages, sending
ms.assetid: 33d62260-b5e0-4d14-b2d2-996733d588e7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe3ab052612166b55fb966507a4a4c95b1b8f81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388081"
---
# <a name="fault-messages"></a>错误消息
请求-响应端口可以具有与其相关联的错误消息，因此，如果出现问题后发送的请求，响应服务可以将错误发送给请求者，代替响应。  
  
 每个操作的请求-响应端口可以处理任意数量的不同错误。 错误消息可具有多种消息类型，但消息类型必须是唯一的操作，并不能使用该端口操作中的响应的类型。  
  
## <a name="receiving-fault-messages"></a>接收错误消息  
 如果端口操作发送请求，然后接收响应，可用于接收一个或多个不同的故障消息类型。  
  
 你可以配置**捕获异常**块来处理传入的错误消息，通过从作为其异常对象类型的请求-响应端口操作中选择相应的错误。  
  
## <a name="sending-fault-messages"></a>发送错误消息  
 如果端口操作接收响应，然后发送请求，可用于将一个或多个不同的故障消息类型发送。  
  
 如果例如您的业务流程遇到错误情况并引发异常，您可以在发送错误消息**捕获异常**块处理异常。 构造相应类型的错误消息来传达给参与的服务，这种情况，并将在端口操作中使用该相应错误的发送形状上指定该错误消息。  
  
## <a name="see-also"></a>请参阅  
 [异常](../core/exceptions.md)