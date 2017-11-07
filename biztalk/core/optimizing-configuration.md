---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 2b0a1aa81971e3e086881e23bcfd6d7ba5d5799d
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="optimize-configuration"></a>优化配置
本部分介绍如何优化适用于 PeopleSoft Enterprise 的 BizTalk 适配器的配置，并且包括了用于设置适配器的参数说明。  
  
## <a name="message-overload-protection"></a>消息重载保护  
 `Max Concurrent Calls` 参数是一种用来优化配置的功能。 在吞吐量超过了后端处理能力的情况下，可以使用此参数。 你可以将参数添加到中的适配器**发送端口传输属性**对话框中，若要激活消息重载保护。 默认值为 -1，表示不限制调用数量。  
  
 当 BizTalk Server 将消息提交到传输适配器时，它首先接收来自适配器的一个批并对批调用 `TransmitMessage()` 以传输每个消息。 完成上述操作后，BizTalk Server 对批调用 `Done()`，然后适配器开始将消息传输到后端。 如果 BizTalk Server 在调用 `Done` 之前获得了多个批，`Done` 命令可能永远不会发生。 通过设置批中的最大消息数量，可以控制传输到后端的消息。 对此参数的更改会在一分钟后生效。 BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。  
  
## <a name="change-the-max-concurrent-calls-parameter"></a>更改最大并发调用参数  
  
1.  在**发送端口传输属性**对话框框中，输入**连接**值。  
  
     默认值为 40 个会话。 如果您使用一个较小的值，可能会出现运行时性能下降。 反之亦然，使用较大的值，则会超出服务器的能力并导致运行时错误。  
  
2.  选择**是**为**刷新代理**强制 runtimeagent.exe 以及要在需要时自动重新启动 browsingagent.exe 过程。  
  
     例如，您希望进程在出现以下情况时自动重新启动：丢失了与服务器的连接；或者向服务器中添加了内容，但是由于它没有显示在 Microsoft 适配器向导中而无法选择它。  
  
     **刷新代理**参数刷新浏览和运行时代理。 runtimeagent.exe 在一分钟延迟后或在下一次发送呼叫时更新。  
  
3.  提供凭据以访问 PeopleSoft 系统。  
  
     您可以使用两种方法来访问系统：  
  
    -   登录凭据（传输属性登录参数）  
  
    -   单一登录  
  
4.  选择**是**为**使用 SSO**用于单一登录。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[安全适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)。 
  
5.  在列表中选择一个关联应用程序。  
  
     由企业单一登录工具创建的关联应用程序，表示一个应用程序，如 PeopleSoft。 适用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。 凭据是启动 BizTalk 项目的用户（应用程序用户）的凭据。  
  
    > [!NOTE]
    >  有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)，或 Microsoft BizTalk Server 联机帮助。  
  
6.  提供所有所需的信息，以接受连接信息后，单击**应用**，然后单击**确定**。  
  
     您必须为适用于 PeopleSoft Enterprise 的 BizTalk 适配器设置连接参数，以访问 PeopleSoft。  
  
## <a name="see-also"></a>另请参阅  
 [创建 PeopleSoft 发送处理程序](../core/creating-peoplesoft-send-handlers.md)