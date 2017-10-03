---
title: "适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- adapters
- send adapters
- adapters, about adapters
- send adapters, about send adapters
- receive adapters, about receive adapters
- adapters, adapter framework
- receive adapters
- adapters, send adapters
ms.assetid: 7803a806-3396-4662-877f-eae11cb5e3e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a7f58a9d67b9702cfbb7b21788f751717ac61e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapters"></a>适配器
为了与外部系统、应用程序和实体交换消息，Microsoft BizTalk Server 使用了适配器的概念。 *适配器*是 COM 或。传输消息与其他业务终结点 （例如文件系统、 数据库和自定义业务应用程序） 的基于网络的组件使用各种通信协议。  
  
 BizTalk Server 在发送和接收操作中使用适配器与外部实体交换消息。  
  
-   使用适配器支持的协议从 BizTalk Server 向外部实体发送信息时，即执行发送（或发送端）操作。  
  
-   适配器从外部实体接收信息并将其传递给 BizTalk Server 消息引擎时，即执行接收（或接收端）操作。  
  
## <a name="the-adapter-framework"></a>适配器框架  
 下图显示了适配器和适配器框架如何协同工作，以将您的应用程序连接到 BizTalk Server。  
  
1.  通过在侦听指定地址处的协议的消息的接收位置接收的数据。 接收位置与适配器和接收管道相关联。 您可以配置适配器和管道组件对具有预设协议的消息执行某个逻辑操作。  
  
2.  接收位置接收到消息后，消息将发送给适配器，适配器会创建新的 BizTalk Server 消息、将数据流附加到该消息（通常在消息的正文部分）中、添加接收数据的终结点的所有相关元数据，然后将消息提交到消息引擎中。  
  
3.  消息引擎将消息发送到接收管道，在这里会将数据转换成 XML，验证消息发件人的身份，对消息进行解密，然后验证 XML。  
  
4.  消息引擎将消息发布到 MessageBox。 MessageBox 是一个包含待处理消息的 Microsoft SQL Server 表。 两种业务流程和发送端口都可以订阅 MessageBox。  
  
5.  消息引擎根据与订户筛选器所设置规范匹配的消息上下文属性，将消息发送给业务流程或发送端口订户。  
  
6.  如果某个业务流程是订户，它会处理消息并使用发送端口将消息发送出去。 在发送端口获得消息后，或者在发送端口是唯一订户的情况下，该消息会经过发送管道传递到发送适配器中，然后通过网络进行传输。  
  
 适配器框架  
  
 ![适配器 framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
## <a name="receive-adapters"></a>接收适配器  
 接收适配器负责通过将网络/数据源流附加到消息正文来创建新的 BizTalk Server 消息。 它还添加有关接收数据的终结点的所有元数据，然后将消息提交到消息引擎。  
  
 接收适配器从接收终结点删除数据，或向客户端发送相应的确认消息以指示数据已被 BizTalk Server 接受。  
  
## <a name="send-adapters"></a>发送适配器  
 发送适配器负责将 BizTalk 消息发送到指定的终结点使用其特定传输协议。  
  
 有关适配器的详细信息，结构适配器，以及如何编写自定义适配器，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [项目](../core/artifacts.md)