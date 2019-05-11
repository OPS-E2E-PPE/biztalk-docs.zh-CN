---
title: 适配器框架是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e2fd7-4e77-49c4-839d-c2bf16b10ba2
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd96ab8287a3c8d02bb612d4595c9f418e566eb9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243220"
---
# <a name="what-is-the-adapter-framework"></a>适配器框架是什么？
BizTalk 适配器框架提供了稳定、 开放的机制，用于所有适配器来实现或访问来自工作[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息引擎。 接口中所述**Microsoft.BizTalk.Adapter.Framework**命名空间启用适配器，以提供用于修改配置属性页。 它也是一种服务和架构导入到 BizTalk 项目。  
  
 下图显示了适配器和适配器框架如何协同工作以应用程序连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 ![适配器框架](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
 以下步骤介绍在此图中所示的步骤序列：  
  
1. 从侦听指定地址处的特定协议的消息的接收位置接收数据。 接收位置是与适配器和接收管道相关联。 您可以配置适配器和管道组件执行某个逻辑上预先确定的协议的消息。  
  
2. 接收位置接收此消息后，将消息发送到适配器，会创建新的 BizTalk 消息、 将数据流附加到消息 （通常在消息的正文部分）、 添加到终结点相关的任何元数据数据已收到，，然后将该消息提交到消息引擎。  
  
3. 消息引擎将消息发送到接收管道，其中数据转换为 XML、 邮件发件人进行身份验证、 对消息进行解密，并验证 XML。  
  
4. 消息引擎将消息发布到 MessageBox 数据库。 MessageBox 是一个 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]表，它包含要处理的消息。 业务流程和发送端口可以订阅 MessageBox。  
  
5. 消息引擎将消息发送到业务流程或发送端口订阅服务器根据订阅服务器上的筛选器中所设置规范匹配的消息上下文属性。  
  
6. 如果业务流程是订户，它处理消息，并通过发送端口将其发送出去。 如果订户是发送该消息会传递经过发送管道到发送适配器传输之前。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用适配器框架工具](../core/using-the-adapter-framework-tools.md)  
  
-   [适配器消息交换模式](../core/adapter-message-exchange-patterns.md)  
  
-   [适配器框架组件](../core/adapter-framework-components.md)  
  
-   [适配器宿主模型](../core/adapter-hosting-model.md)  
  
-   [适配器组件](../core/adapter-components.md)