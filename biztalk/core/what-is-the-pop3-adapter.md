---
title: POP3 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- POP3 adapters, availability
- authenticating, POP3 adapters
- POP3 adapters, data duplication
- data duplication
- POP3 adapters, receive adapters
- high availability, POP3 adapters
- POP3 adapters, supported platforms
- POP3 adapters, authenticating
- POP3 adapters, algorithims
- receive adapters, POP3 adapters
ms.assetid: 05e9598b-cdfe-4216-b6bf-1b84f8ddfeae
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c298af8c35aaea90c9f078dbf43d5ff8483bc742
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242813"
---
# <a name="what-is-the-pop3-adapter"></a>POP3 适配器是什么？
本部分将介绍 POP3 接收适配器。  
  
## <a name="pop3-receive-adapter"></a>POP3 接收适配器  
 POP3 接收适配器，可以将数据从启用 POP3 的邮箱移到 BizTalk Server。  
  
 主要功能的 POP3 接收适配器是：  
  
-   请求按需从 POP3 服务器邮箱的文件。  
  
-   基于可配置的计划运行轮询。  
  
-   轮询 POP3 服务器邮箱，并将数据发送到 BizTalk Server 直接。  
  
-   指定 POP3 服务器邮箱为 IP 地址或主机名、 端口、 用户名和密码。  
  
-   若要从需要安全套接字层 (SSL) 连接的邮件服务器下载电子邮件的功能。  
  
-   确保文件送达。  
  
-   隐式 MIME 处理。 不需要使用 POP3 适配器时，在接收管道中使用 MIME 解码器。  
  
## <a name="pop3-adapter-supported-platforms"></a>POP3 适配器支持的平台  
 POP3 适配器可使用任何符合以下 Rfc 的 POP3 服务器：  
  
- **RFC 1939。** 邮局协议版本 3 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58808 ](http://go.microsoft.com/fwlink/?LinkId=58808))  
  
- **RFC 1734。** POP3 身份验证命令 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58809 ](http://go.microsoft.com/fwlink/?LinkId=58809))  
  
- **RFC 2045。** 多用途 Internet 邮件扩展 (MIME) 第 1 部分：Internet 消息正文的格式 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58810 ](http://go.microsoft.com/fwlink/?LinkId=58810))  
  
- **RFC 2046。** 多用途 Internet 邮件扩展 (MIME) 第二部分：媒体类型 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58811 ](http://go.microsoft.com/fwlink/?LinkId=58811))  
  
- **RFC 最多允许 2047年。** MIME （多用途 Internet 邮件扩展） 第 3 部分：为非 ASCII 文本消息标头扩展 (请参阅[ http://go.microsoft.com/fwlink/?LinkId=58812 ](http://go.microsoft.com/fwlink/?LinkId=58812))  
  
  针对 Microsoft Exchange Server 2003，POP3 适配器已进行广泛测试。  
  
## <a name="considerations-for-preventing-data-duplication-when-using-the-pop3-adapter"></a>使用 POP3 适配器时防止数据重复的注意事项  
 POP3 适配器不是事务性适配器，因此可能出现处理同一消息的多个副本可能会导致数据重复。 此外，可以 POP3 适配器将在以下方案中提供的一条消息的重复副本：  
  
-   POP3 适配器从邮箱配置来监视电子邮件已成功提交到 BizTalk Server 进行处理后始终删除电子邮件。 如果 POP3 适配器从邮箱中检索电子邮件、 将电子邮件发送至 BizTalk Server 提交进行处理，并且无法删除邮箱中的电子邮件，电子邮件将重新提交到 BizTalk Server 的下一步时间 POP3 适配器轮询该邮箱。  
  
-   如果 POP3 适配器在单独的 BizTalk 主机实例中的多个实例正在同时监视同一个邮箱，并且 POP3 服务器允许对其邮箱进行多个并发连接，该适配器可能传送消息的重复副本。  
  
## <a name="high-availability-for-the-pop3-adapter"></a>POP3 适配器的高可用性  
 某些 POP3 服务器允许与给定邮箱的多个并发连接。 如果 POP3 适配器的多个实例配置为从 POP3 服务器上的邮箱中检索邮件可能出现数据重复。 因此应配置 POP3 适配器从允许多个并发连接的邮箱中检索邮件的一个实例。  
  
 若要为此方案中的 POP3 适配器提供容错，单个 POP3 适配器接收处理程序应配置为在群集 BizTalk 主机中运行。 有关详细信息请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
## <a name="authentication-warnings-when-multiple-instances-of-the-pop3-adapter-connect-to-the-same-mailbox"></a>POP3 适配器的多个实例连接到同一邮箱时的验证警告  
 BizTalk Server 可能配置为具有从同一邮箱中检索邮件的 POP3 适配器的多个实例。 在这种情况下，很可能身份验证警告，可能会由于某些 POP3 服务器采用了锁定机制在 BizTalk Server 应用程序日志中进行生成。 这些警告将对 POP3 适配器功能没有任何影响，可以在此方案中安全地忽略。  
  
## <a name="encrypted-messages-received-by-the-pop3-adapter-that-are-sent-to-the-suspended-queue-may-be-viewable-in-clear-text"></a>发送到挂起队列 POP3 适配器接收加密消息可能会以明文形式的可视区域大小  
 可以配置 POP3 适配器进行解密进行数字加密的电子邮件。 这是通过设置**应用 MIME 解码**属性设置为**True**的接收位置，使用 POP3 适配器。 如果 POP3 适配器收到经数字加密的电子邮件并**应用 MIME 解码**接收位置属性设置为**True** POP3 适配器尝试解密该电子邮件，如下所示：  
  
- POP3 适配器搜索匹配用来加密电子邮件的公用证书的私钥证书。 私钥证书必须在运行 POP3 接收主机实例的服务器的个人证书存储中处理程序绑定到。  
  
- 如果 POP3 适配器找到相应的私钥证书，则使用该私钥证书对电子邮件消息进行解密。  
  
- 电子邮件是解密，并保存到 BizTalk MessageBox。  
  
  如果经过解密并保存到 BizTalk MessageBox 中后被挂起一条消息，消息的内容将以明文形式在 BizTalk 挂起队列中可见。  
  
  如果需要阻止的挂起队列中的安全消息中文本的显示，请执行以下步骤：  
  
- 设置**应用 MIME 解码**属性设置为**False**为该使用 POP3 适配器接收位置和解密使用 SMIME 管道组件的管道中的消息。  
  
  > [!NOTE]
  >  此方法将阻止你无法升级到消息上下文的电子邮件特定属性。  
  
- 如果你需要升级到消息上下文的电子邮件特定属性，并确保其路由到挂起队列加密的消息保持加密，请按照下列步骤：  
  
  -   选中选项**失败消息启用路由功能**使用 POP3 适配器的接收位置所在接收端口上。  
  
  -   创建一个业务流程订阅到使用 POP3 适配器的接收位置所在接收端口传递失败的消息。  
  
  -   配置加密使用 SMIME 管道组件的管道中的消息的发送端口业务流程。  
  
  -   使用挂起形状，以挂起业务流程实例和消息配置业务流程。  
  
  -   生成和部署业务流程、 接收端口绑定到相应部署的业务流程。  
  
## <a name="maximum-message-size-supported-by-the-pop3-adapter"></a>POP3 适配器支持的最大消息大小  
 POP3 适配器进行了测试和支持接收消息最多为 50 MB 的大小。  
  
## <a name="see-also"></a>请参阅  
 [POP3 适配器](../core/pop3-adapter.md)