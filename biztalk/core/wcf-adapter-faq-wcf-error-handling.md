---
title: WCF 适配器常见问题解答：WCF 错误处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdbd1ea6-4898-415c-ac5e-f804565759a8
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43e7eaccfdb13324d374833ee27fe7144abb9cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379850"
---
# <a name="wcf-adapter-faq-wcf-error-handling"></a>WCF 适配器常见问题解答：WCF 错误处理
## <a name="how-do-the-wcf-adapters-handle-errors-and-soap-faults-during-message-processing"></a>WCF 适配器如何处理错误和 SOAP 错误消息处理过程？  
 对于接收位置，可以配置下的两个错误处理选项之一**的错误处理**部分**消息**选项卡中**传输属性**对话框框。  
  
 如果**失败时挂起请求消息**选择选项后，将挂起传入请求消息应该有在接收管道中的处理故障或路由消息的故障。 这样，消息的发件人，要成功传输到 BizTalk Server 并接收确认 (ACK) 消息。 BizTalk Server 将挂起消息并记录失败消息的完整的错误记录。 但是，它也不发送的消息异常返回到发件人在这种情况下。 这适用于单向端口只会发送 ACK 如果选中，并且如果未选中将 NACK。 对于双向端口，如果处理失败，BizTalk 将收到 NACK。  
  
 但是，如果客户端需要有权访问失败的异常，请选择**错误中包括异常详细信息**选项。 选中时，这将返回 SOAP 错误给调用方如果发生处理错误。 这是与 serviceDebug 行为与"IncludeExceptionDetailsInFaults"指定为 True**行为**Wcf-custom 或 Wcf-customisolated 适配器的选项卡。 现在，详细的异常发送到客户端。 此选项是使用更可行、 更安全的比在生产环境中的应用程序开发期间使用，因为内部错误消息最有可能应不会发送到服务调用方。  
  
 对于双向发送端口，您可以选择是否将转发到原始调用方的 SOAP 错误消息通过要求响应发送端口通过选择**传播错误消息**。 如果不选择此选项，BizTalk Server 将首先生成 NACK，然后挂起该消息。 如果选择它，则 BizTalk Server 会将消息视为有效 WCF 响应消息从外部服务和响应消息将不被挂起，因为它传播。  
  
## <a name="how-do-the-wcf-adapters-handle-message-transmission-timing-issues"></a>WCF 适配器如何处理消息传输计时问题？  
 你可以通过使用控制 WCF 适配器的计时问题**绑定**选项卡**传输属性**对话框。 这些设置是**开放**，**发送**，并**关闭超时**。 （没有还可以使用自定义适配器设置的接收超时值。）这些设置分别是一个通道，以打开、 发送和通道关闭 （和接收自定义） 的时间才能完成的操作。 所有三个默认为一分钟至 23:59 最大周期。