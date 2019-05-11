---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 7d7c30262fabbbde4f555deb7f0b01c3ef4ffb95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262984"
---
# <a name="optimize-configuration"></a>优化配置
本部分包含有关如何优化适用于 PeopleSoft Enterprise 的 BizTalk 适配器的配置信息，并且包括用于设置适配器的参数说明。  
  
## <a name="message-overload-protection"></a>消息重载保护  
 `Max Concurrent Calls`参数是一项功能，可用于优化您的配置。 在吞吐量超过了后端处理能力的实例中使用此参数。 可以将参数添加到中的适配器**发送端口传输属性**对话框以激活消息重载保护。 默认值为-1，这意味着不限制调用数量。  
  
 当 BizTalk Server 将消息提交到传输适配器时，它首先接收来自适配器的批处理并调用`TransmitMessage()`对批，将每个消息传送。 完成后，BizTalk Server 调用`Done()`批处理，然后适配器开始将消息传输到后端上。 如果 BizTalk Server 之前获得了多个批`Done`调用时，`Done`命令可能永远不会发生。 通过在批处理中设置的最大消息数，可以控制到后端的消息。 更改此参数在一分钟内将生效。 BizTalk Server 必须检索保存在 SQL 数据库中的适配器配置的更改。  
  
## <a name="change-the-max-concurrent-calls-parameter"></a>更改最大并发调用参数  
  
1.  在中**发送端口传输属性**对话框框中，输入**连接**值。  
  
     默认值为 40 个会话。 如果使用较小的值，可能会遇到运行时性能下降。 相反也是如此;较大的值可能会超过服务器和在运行时错误的结果的能力。  
  
2.  选择**是**有关**刷新代理**以强迫 runtimeagent.exe 和 browsingagent.exe 进程在需要时自动重新启动。  
  
     例如，您希望自动重新启动它将失去与服务器的连接，或者如果将内容添加到服务器并且不会出现在 Microsoft 适配器向导中选择的过程。  
  
     **刷新代理**参数刷新浏览和运行时代理。 Runtimeagent.exe 在延迟一分钟或在下一步后的更新发送调用。  
  
3.  提供凭据以访问 PeopleSoft 系统。  
  
     可以使用两种方法来访问系统：  
  
    -   登录凭据 （传输属性登录参数）  
  
    -   单一登录  
  
4.  选择**是**有关**使用 SSO**若要使用单一登录。  
  
    > [!NOTE]
    >  有关详细信息，请参阅[保护适配器](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)。 
  
5.  在列表中选择关联应用程序。  
  
     企业单一登录工具创建的关联应用程序代表诸如 PeopleSoft 之类的应用程序。 用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。 凭据是启动 BizTalk 项目的用户 （应用程序用户）。  
  
    > [!NOTE]
    >  有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications2.md)，或 Microsoft BizTalk Server 联机帮助。  
  
6.  提供所需的所有信息，以接受连接信息后，单击**Apply**，然后单击**确定**。  
  
     必须设置用于访问 PeopleSoft 的 PeopleSoft Enterprise 的 BizTalk 适配器的连接参数。  
  
## <a name="see-also"></a>请参阅  
 [创建 PeopleSoft 发送处理程序](../core/creating-peoplesoft-send-handlers.md)