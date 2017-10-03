---
title: "WCF 适配器常见问题： WCF 错误处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdbd1ea6-4898-415c-ac5e-f804565759a8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efbac0b7aaffd6121cba406031a8330cfd5bbf2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faq-wcf-error-handling"></a>WCF 适配器常见问题： WCF 错误处理
## <a name="how-do-the-wcf-adapters-handle-errors-and-soap-faults-during-message-processing"></a>WCF 适配器在消息处理过程中如何处理错误和 SOAP 错误？  
 对于接收位置，你可以配置下的两个错误处理选项之一**错误处理**节**消息**选项卡中**传输属性**对话框框。  
  
 如果**失败的挂起请求消息**选择选项后，将被挂起，传入的请求消息应有接收管道中的处理失败或失败的消息的路由。 此操作允许消息发送方将消息成功传输到 BizTalk Server 并接收确认消息。 BizTalk Server 将挂起消息并记录失败消息的完整错误。 但是，在这种情况下，也不会将消息异常发送回发送方。 此操作仅适用于单向端口，如果选中则发送 ACK，如果未选中则发送 NACK。 对于双向端口，如果处理失败，BizTalk 将收到 NACK。  
  
 但是，如果客户端必须有权访问失败的异常，请选择**错误中包括异常详细信息**选项。 选中时，如果发生处理错误则将 SOAP 错误返回到调用方。 这相当于将指定其 serviceDebug 行为与"IncludeExceptionDetailsInFaults"为 True 上**行为**的 WCF 自定义或 WCF CustomIsolated 适配器的选项卡。 此时，详细异常将发送到客户端。 在应用程序开发过程中使用此选项比在生产中使用更可行、更安全，因为内部失败消息多数情况下不会发送到服务调用方。  
  
 为双向发送端口，你可以选择是否将转发到原始调用方的 SOAP 错误消息通过要求响应发送端口通过选择**传播错误消息**。 如果未选中此选项，BizTalk Server 将首先生成 NACK，然后挂起该消息。 如果选中，BizTalk Server 会将该消息视为来自外部服务的有效 WCF 响应消息，并且由于传播响应消息而不将其挂起。  
  
## <a name="how-do-the-wcf-adapters-handle-message-transmission-timing-issues"></a>WCF 适配器如何处理消息传输计时问题？  
 你可以通过使用控制 WCF 适配器的计时问题**绑定**选项卡中**传输属性**对话框。 这些设置**打开**，**发送**，和**关闭超时**。 （还有一个可以使用自定义适配器设置的“接收超时”设置。）这些设置分别是通道打开、发送和通道关闭（和接收自定义）操作完成所需的时间。 所有三个设置的默认值均为一分钟至 23:59。