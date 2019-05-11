---
title: 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d3e669f31f1050a0e2c37388cd8106a2386da45
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361074"
---
# <a name="adapters"></a>适配器
为了与外部系统、 应用程序和实体交换消息 Microsoft BizTalk Server 使用的适配器的概念。 *适配器*是 COM 或。传输消息在业务终结点 （如文件系统、 数据库和自定义业务应用程序） 的基于 NET 的组件使用各种通信协议。  
  
 适配器使用 BizTalk server 交换消息与外部实体发送和接收操作  
  
-   BizTalk Server 在将信息发送到使用该适配器支持的协议的外部实体时，会发生发送 （或发送端） 操作。  
  
-   接收 （或接收方） 时，适配器从外部实体接收信息并将其传递到 BizTalk Server 消息引擎执行的操作。  
  
## <a name="the-adapter-framework"></a>适配器框架  
 下图显示了适配器和适配器框架如何协同工作以连接到 BizTalk Server 应用程序。  
  
1. 通过侦听指定地址的特定协议的消息的接收位置接收的数据。 接收位置是与适配器和接收管道相关联。 您可以配置适配器和管道组件对具有预设的协议的消息执行特定逻辑。  
  
2. 接收位置接收此消息后，将消息发送到适配器，适配器创建新的 BizTalk Server 消息、 将数据流附加到消息 （通常在消息的正文部分）、 添加所有相关终结点，通过元数据收到数据，然后将该消息提交到消息引擎。  
  
3. 消息引擎将消息发送到接收管道，其中数据转换为 XML、 邮件发件人进行身份验证、 对消息进行解密，并验证 XML。  
  
4. 消息引擎将消息发布到 MessageBox。 MessageBox 是一个包含要处理的消息的 Microsoft SQL Server 表。 业务流程和发送端口可以订阅 MessageBox。  
  
5. 消息引擎将消息发送到业务流程或发送端口订阅服务器根据订阅服务器上的筛选器中所设置规范匹配的消息上下文属性。  
  
6. 如果业务流程是订户，它处理消息，并将其发送出使用发送端口。 发送端口有这个功能，或仅订阅服务器后，该消息会传递经过发送管道到发送适配器然后通过网络进行传输。  
  
   适配器框架  
  
   ![适配器框架](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
## <a name="receive-adapters"></a>接收适配器  
 接收适配器负责通过将网络/数据源流附加到消息正文来创建新的 BizTalk Server 消息。 它还会添加到终结点的数据接收的则该将消息提交到消息引擎相关的任何元数据。  
  
 适配器从接收终结点删除数据，或将相应的确认消息发送到客户端，该值指示数据已被接受到 BizTalk Server。  
  
## <a name="send-adapters"></a>发送适配器  
 发送适配器负责将 BizTalk 消息发送到指定的终结点使用其特定的传输协议。  
  
 适配器和编写自定义适配器的结构有关适配器的详细信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
## <a name="see-also"></a>请参阅  
 [项目](../core/artifacts.md)