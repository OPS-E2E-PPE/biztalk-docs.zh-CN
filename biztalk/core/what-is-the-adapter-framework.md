---
title: "适配器框架概述 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 648c22a52e543b24458daa73146836e1e3a5463e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-adapter-framework"></a>适配器框架概述
BizTalk 适配器框架提供了一个稳定、 打开机制，以实现或访问工作中的所有适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。 接口中所述**Microsoft.BizTalk.Adapter.Framework**命名空间启用适配器，以提供一种方式来修改配置属性页。 它还可用于将服务和架构导入到 BizTalk 项目中。  
  
 下图显示了适配器和适配器框架如何协同工作来应用程序连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 ![适配器 framework](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
 下面的步骤描述上图中的一系列步骤：  
  
1.  通过接收位置接收数据，接收位置会侦听指定地址的特定协议的消息。 接收位置与适配器和接收管道相关联。 你可以配置适配器和管道组件来执行某些逻辑上预先确定的协议的消息。  
  
2.  接收位置接收到消息后，消息将发送给适配器，适配器会创建新的 BizTalk 消息、将数据流附加到该消息（通常在消息的正文部分）中、添加接收数据的终结点的所有相关元数据，然后将消息提交到消息引擎中。  
  
3.  消息引擎将消息发送到接收管道，在这里会将数据转换成 XML，验证消息发件人的身份，对消息进行解密，然后验证 XML。  
  
4.  消息引擎将消息发布到 MessageBox 数据库中。 MessageBox 是 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]表包含要处理的消息。 两种业务流程和发送端口都可以订阅 MessageBox。  
  
5.  消息引擎根据与订户筛选器所设置规范匹配的消息上下文属性，将消息发送给业务流程或发送端口订户。  
  
6.  如果某个业务流程是订户，它会处理消息并通过发送端口将消息发送出去。 如果该订户是发送订户，则该消息会经过发送管道传递到发送适配器中，然后进行传输。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用适配器 Framework 工具](../core/using-the-adapter-framework-tools.md)  
  
-   [适配器消息交换模式](../core/adapter-message-exchange-patterns.md)  
  
-   [适配器 Framework 组件](../core/adapter-framework-components.md)  
  
-   [承载模型的适配器](../core/adapter-hosting-model.md)  
  
-   [适配器组件](../core/adapter-components.md)