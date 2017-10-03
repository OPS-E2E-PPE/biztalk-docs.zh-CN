---
title: "设置为发送端口的 TIBCO 企业消息服务传输属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, setting transport properties
- transport properties, setting for send port
- setting transport properties, send port
ms.assetid: 156fa3d1-6c47-442b-9c5d-5bcd838115f8
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eba9a07a6b5991d832a0815a4eb63706c3bbbd3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-send-port"></a>设置发送端口的 TIBCO Enterprise Message Service 传输属性
TIBCO Enterprise Message Service 传输属性在设计时配置，在运行时使用。 在**传输属性**对话框中，你设置的连接和凭据参数特定于服务器系统和你尝试访问的对象。  
  
 ![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")  
  
### <a name="to-specify-transport-properties"></a>若要指定传输属性  
  
1.  在**传输属性**对话框框中，展开**系统定义**，然后输入 TIBCO EMS 服务器连接的所有必要的信息。  
  
     您必须设置配置参数才能将用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器连接到 TIBCO EMS。 此数据是区分大小写。  
  
2.  展开**消息处理**并输入所有所需的信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Message Expiration Time`|描述消息保留在队列或主题中的时间长度的整数；该时间到期后，消息将被 TIBCO EMS 服务器删除。<br /><br /> 它与 EMS.Expiration 消息属性标头同义。 业务流程可以将其覆盖。<br /><br /> 默认值为 0 毫秒，这意味着消息在目标中将不会过期。|  
    |`Message is Persistent`|在确认消息之前，TIBCO EMS 服务器已将其写入磁盘。<br /><br /> 这是 TibcoEMS.DeliveryMode 标头属性。 它指示在向适配器确认接收消息之前，服务器已将发送的消息保留在队列中。<br /><br /> 默认值为 **True**。|  
    |`Message Priority`|0 到 9 之间的数字，用于定义消息的优先级；该值越大，优先级就越高。<br /><br /> 优先级影响服务器向使用者传递消息的顺序（较大的值优先）。<br /><br /> JMS 规范定义了十个级别的优先级值，从 0（最低优先级）到 9（最高优先级）。 该规范建议客户端将 0–4 视为正常优先级层次，将优先级 5–9 视为加急优先级层次。<br /><br /> 默认值是**4**。|  
  
3.  展开**服务器连接定义**并输入所有所需的信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Destination`|强制设置。 定义目标名称和类型。 例如： staticqueue [Q1]。<br /><br /> 定义的队列或主题具有以下格式: {静态} {动态] 队列 [queuename] 或 {静态} {动态] 主题 [topicname]。 **注意：**可以将消息发送到的目标，不存在。 在这种情况下，TIBCO 企业消息服务创建目标;这称为*动态目标*。 这是在使用消息时由生成者创建的目标，当生成者断开连接时，此目标会被删除。 A*静态目标*是目标仅可以创建由 TIBCO 企业消息服务管理员。 在您打开与目标的连接时无法连接到动态端口，因为用于 TIBCO Enterprise Message Service 的 BizTalk 适配器在服务器上使用名称查找机制。 当您使用名称查找时，只有静态端口是可见的。 在连接到动态端口时，可以使用静态目标；但是，如果不存在具有该名称的目标，则会创建一个目标。 目标可让您在定义端口时显式指定要使用的目标类型。 目标的语法不区分大小写： staticqueue [queue_name]、 statictopic [topic_name]、 dynamicqueue [queue_name];dynamictopic [topic_name]。|  
    |`Port Number`|TIBCO EMS 服务器侦听的端口。|  
    |`Server Name`|强制设置。 托管 TIBCO EMS 服务器的系统的名称。|  
  
4.  使用单一登录 (SSO) 提供凭据。  
  
     可以使用两种方法来访问 TIBCO EMS 系统。 您可以使用凭据（用户名和密码参数）或单一登录。  
  
    -   选择**是**中**使用 SSO**用于单一登录。  
  
    -   从列表中选择一个关联应用程序。  
  
         企业单一登录工具创建的关联应用程序代表诸如 TIBCO EMS 之类的应用程序。 用于 TIBCO EMS 的 BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。  
  
         有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。  
  
5.  在**事务支持**，选择**是**如果此发送端口将支持事务。  
  
     如果在端口上启用事务支持，则使用此端口的所有业务流程都必须是事务性的；否则，所有调用都会回滚（例如不提交）。 添加到业务流程中的作用域对象控制事务的生命周期。  
  
6.  展开**用户凭据**并输入**用户名**和**密码**访问 TIBCO EMS 服务器。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Password`|用于与 TIBCO EMS 守护程序进行通信的用户的密码。<br /><br /> 如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。|  
    |`User Name`|用来与 TIBCO EMS 守护程序进行通信的用户的名称。<br /><br /> 如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。|  
  
7.  单击**应用**，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [使用单一登录](../core/using-single-sign-on4.md)   
 [创建 TIBCO 企业消息服务发送处理程序](../core/creating-tibco-enterprise-message-service-send-handlers.md)