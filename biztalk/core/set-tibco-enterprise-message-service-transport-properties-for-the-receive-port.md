---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-receive-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 856309a744d1874d336bb31840f193494858c81d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393298"
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a>设置 TIBCO Enterprise Message Service 传输属性的接收端口
用于 TIBCO Enterprise 消息系统 (EMS) 接收位置，则**URL**并**Target Namespace**到 TIBCO EMS 系统是所需的唯一配置值。  
  
### <a name="to-specify-tibco-ems-transport-properties"></a>指定 TIBCO EMS 传输属性  
  
1.  展开**系统定义**并输入所需的所有信息以连接到 TIBCO EMS 服务器。  
  
2.  展开**消息处理**并输入所需的所有信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**消息选择器**|此字符串的计算结果为与目标中的消息，则返回 True，才接收消息。<br /><br /> 允许要检索包含在此字段中所述的表达式匹配的标头属性的消息的接收端口。<br /><br /> 消息选择器的语法基于 SQL92 条件表达式语法的子集。 完全在 TIBCO EMS 用户指南中介绍的语法。<br /><br /> 例如，如果一条消息包含标头属性名称 NewsType，接收端口可以检索仅 Sports 或 Editorial 的类型。|  
    |**重试次数**|传输重试计数。 默认值为 0。|  
    |**重试间隔**|启动重试之前的时间段适配器的等待。 默认值为 5 分钟。|  
  
3.  展开**服务器连接定义**并输入所需的所有信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**目标**|强制设置。 定义名称和目标的类型。 定义队列或主题具有以下格式：Queue [queue.name] 或 topic [topic.name]。|  
    |**端口号**|TIBCO EMS 服务器在其侦听的端口。|  
    |**服务器名称**|强制设置。 托管 TIBCO EMS 服务器的系统的名称。|  
  
4.  提供使用单一登录 (SSO) 的凭据。  
  
     有两种方法可用于访问 TIBCO EMS 系统。 可以使用凭据 （用户名称和密码参数） 或单一登录。  
  
    -   选择**是**中**使用 SSO**若要使用单一登录。  
  
    -   在列表中选择关联应用程序。  
  
         企业单一登录工具创建的关联应用程序表示诸如 TIBCO EMS 之类的应用程序。 用于 TIBCO EMS 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。  
  
         有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。  
  
5.  展开**用户凭据**并输入**用户名**并**密码**访问 TIBCO EMS 服务器。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Password`|用于与 TIBCO EMS 守护程序通信的用户的密码。<br /><br /> 如果未选中**使用 SSO**，则必须设置凭据参数，用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。|  
    |`User Name`|用于与 TIBCO EMS 守护程序通信的用户的名称。<br /><br /> 如果未选中**使用 SSO**，则必须设置凭据参数，用于与 TIBCO EMS 守护程序通信的 TIBCO EMS 的 BizTalk 适配器。|  
  
6.  单击**Apply**，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
  [创建 TIBCO Enterprise Message Service 接收处理程序](../core/creating-tibco-enterprise-message-service-receive-handlers.md)