---
title: 创建 TIBCO EMS 发送项目 |Microsoft Docs
description: 创建发送端口，并配置要在 BizTalk Server 中使用 TIBCO Enterprise Message Service 适配器的传输属性
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f82609c-1847-4796-a24c-28cb350ec739
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98bc13b59826c7f5e938d4749776adb742f70133
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353579"
---
# <a name="creating--tibco-enterprise-message-service-send-handlers"></a>创建 TIBCO Enterprise Message Service 发送处理程序
本部分解释如何设置发送端口以连接到 TIBCO Enterprise Message Service (EMS) 以及如何将 XML 包括到业务流程中以在运行时与 TIBCO EMS 交互。  


## <a name="create-a-send-port"></a>创建发送端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**发送端口**，选择**新建**，然后选择**静态要求响应发送端口**。  
  
3.  在中**发送端口属性**，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToTIBCOEMS`。  
  
    2.  从**类型**下拉列表中，选择**TIBCO EMS**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从**发送管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。 从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  

        > [!NOTE]
        > 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器要求接收 XMLTransmit 发送和 XMLReceive 的选择。  
  
    6.  选择**配置**可配置的发送端口。  
  
4.  在中**TIBCO EMS 传输属性**对话框框中，执行以下操作：  
  
    1.  输入**消息处理**，**服务器连接定义**，**事务支持**，**用户名**，和**密码**。  
  
         不需要设置的登录信息。  
  
    2.  在列表中，选择为表示 TIBCO EMS 系统所创建的关联应用程序。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  选择 **确定**。  
  
5.  选择 **确定**。 

## <a name="set-send-port-transport-properties"></a>设置发送端口传输属性
在设计时配置，在运行时中使用 TIBCO Enterprise Message Service 传输属性。 在中**传输属性**，设置连接和凭据参数特定于服务器系统和你尝试访问的对象。  
  
 ![](../core/media/tib-tibcoemssendtransportpropertiess.gif "TIB_TIBCOEMSSendTransportPropertiess")  
  
  
1.  在中**传输属性**，展开**系统定义**，并输入所需的所有信息以连接到 TIBCO EMS 服务器。  
  
     必须设置连接到 TIBCO EMS 的 TIBCO Enterprise Message service 的 Microsoft BizTalk 适配器的配置参数。 **此数据是区分大小写。**  
  
2.  展开**消息处理**，并输入所需的所有信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Message Expiration Time`|一个整数，描述的时间长度消息保留在队列或主题;该时间到期后，该消息是由 TIBCO EMS 服务器删除。<br /><br /> 它等效于 EMS。过期消息属性标头。 将使用业务流程可以重写。<br /><br /> 默认值为 0 毫秒，这意味着不会从目标过期消息。|  
    |`Message is Persistent`|消息写入磁盘由 TIBCO EMS 服务器后再进行确认。<br /><br /> 这是 TibcoEMS.DeliveryMode 标头属性。 它指示发送的消息可持久保留在队列中在服务器确认接收到适配器消息之前。<br /><br /> 默认值为 **True**。|  
    |`Message Priority`|Numeric 排名从 0 到 9，这是定义的消息; 优先级值越大，优先级越高。<br /><br /> 优先级影响服务器将消息传递给使用者的顺序 （更高版本的值优先）。<br /><br /> JMS 规范定义了十个级别的优先级值，从 0 （最低优先级） 到 9 （最高优先级）。 该规范建议客户端视为正常优先级和优先级 5 – 9 视为等级加急优先级等级考虑 0 – 4。<br /><br /> 默认值是**4**。|  
  
3.  展开**服务器连接定义**并输入所需的所有信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Destination`|强制设置。 定义名称和目标的类型。 例如： staticqueue [第 1 季度]。<br /><br /> 定义队列或主题具有以下格式: {static} {dynamic] Queue [queuename] 或 {static} {dynamic] Topic [topicname]。 **注意：** 可以将一条消息发送到一个目标，它不存在。 在这种情况下，TIBCO Enterprise Message Service 创建目标;这被称为*动态目标*。 这是由生成者创建和删除消息使用和生成者断开连接时的目标。 一个*静态目标*是一个目标仅创建由 TIBCO Enterprise 消息服务管理员。 无法连接到动态端口时你打开与目标的连接，因为用于 TIBCO Enterprise Message Service 的 BizTalk 适配器在服务器上使用名称查找机制。 使用名称查找时，只有静态端口是可见的。 连接到动态端口时，可以使用静态目标;但是，如果不存在该名称的任何目标，将创建一个目标。 目标可让您显式指定的目标定义端口时要使用的类型。 为目标的语法不区分大小写： staticqueue [queue_name]、 statictopic [topic_name]、 dynamicqueue [queue_name];dynamictopic [topic_name]。|  
    |`Port Number`|TIBCO EMS 服务器在其侦听的端口。|  
    |`Server Name`|强制设置。 托管 TIBCO EMS 服务器的系统的名称。|  
  
4.  提供使用单一登录 (SSO) 的凭据。  
  
     两种方法可用于访问 TIBCO EMS 系统。 您可以使用凭据 （用户名和密码参数） 或单一登录。  
  
    -   选择**是**中**使用 SSO**若要使用单一登录。  
  
    -   从列表中选择关联应用程序。  
  
         企业单一登录工具创建的关联应用程序表示诸如 TIBCO EMS 之类的应用程序。 用于 TIBCO EMS 的 BizTalk 适配器使用应用程序用户的凭据。 从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。  
  
         有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。  
  
5.  在中**事务支持**，选择**是**如果此发送端口将支持事务。  
  
     如果启用事务支持的端口上，使用此端口的所有业务流程必须是事务性的;否则，所有调用都会都回滚 （例如，不是已提交）。 添加到业务流程的作用域对象控制事务的生命周期。  
  
6.  展开**用户凭据**并输入**用户名**并**密码**访问 TIBCO EMS 服务器。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Password`|用于与 TIBCO EMS 后台程序通信的用户的密码。<br /><br /> 如果未选中**使用 SSO**，必须设置凭据参数以便用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。|  
    |`User Name`|用于与 TIBCO EMS 守护程序进行通信的用户的名称。<br /><br /> 如果未选中**使用 SSO**，必须设置凭据参数以便用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。|  
  
7.  单击**Apply**，然后单击**确定**。  

   
## <a name="next-steps"></a>后续步骤
[创建接收项目](../core/creating-tibco-enterprise-message-service-receive-handlers.md)  
[TIBCO EMS 消息上下文属性](../core/message-context-properties-in-biztalk-server.md)