---
title: "设置 TIBCO 企业消息服务传输属性接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, setting transport properties
- transport properties, setting for receive port
- setting transport properties, receive port
ms.assetid: bccddf84-d92e-469f-aa6f-4234c91a0be9
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94229364e3bed8faaf1407603f17db76c70e6bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-tibco-enterprise-message-service-transport-properties-for-the-receive-port"></a>设置 TIBCO 企业消息服务传输属性接收端口
TIBCO 企业消息系统 (EMS) 接收位置， **URL**和**目标 Namespace**到 TIBCO EMS 系统是所需的唯一配置值。  
  
### <a name="to-specify-tibco-ems-transport-properties"></a>指定 TIBCO EMS 传输属性  
  
1.  展开**系统定义**然后输入 TIBCO EMS 服务器连接的所有必要的信息。  
  
2.  展开**消息处理**并输入所有所需的信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**消息选择器**|仅当目标消息中的此字符串的评估结果为 True 时，才接收消息。<br /><br /> 允许接收端口仅检索其包含的标头属性与本字段中介绍的表达式匹配的消息。<br /><br /> 消息选择器的语法基于 SQL92 条件表达式语法的子集。 TIBCO EMS 用户指南中完整说明了该语法。<br /><br /> 例如，如果一个消息包含标头属性名称 NewsType，则接收端口将仅接收类型为 Sports 或 Editorial 的消息。|  
    |**重试计数**|传输重试计数。 默认值为 0。|  
    |**重试间隔**|适配器发起重试之前的等待时间。 默认值为 5 分钟。|  
  
3.  展开**服务器连接定义**并输入所有所需的信息。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**目标**|强制设置。 定义目标名称和类型。 使用以下格式定义队列或主题：Queue[queue.name] 或 Topic[topic.name]。|  
    |**端口号**|TIBCO EMS 服务器侦听的端口。|  
    |**服务器名称**|强制设置。 托管 TIBCO EMS 服务器的系统的名称。|  
  
4.  使用单一登录 (SSO) 提供凭据。  
  
     有两种方法可用于访问 TIBCO EMS 系统。 你可以使用凭据 （用户名称和密码参数） 或上单一登录。  
  
    -   选择**是**中**使用 SSO**用于单一登录。  
  
    -   在列表中选择一个关联应用程序。  
  
         企业单一登录工具创建的关联应用程序代表诸如 TIBCO EMS 之类的应用程序。 用于 TIBCO EMS 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。  
  
         有关如何创建关联应用程序的详细信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications5.md)。  
  
5.  展开**用户凭据**并输入**用户名**和**密码**访问 TIBCO EMS 服务器。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |`Password`|用于与 TIBCO EMS 后台程序通信的用户的密码。<br /><br /> 如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。|  
    |`User Name`|用于与 TIBCO EMS 后台程序进行通信的用户的名称。<br /><br /> 如果你未选择**使用 SSO**，你必须设置为 BizTalk 适配器 TIBCO EMS 与 TIBCO EMS 后台程序进行通信的凭据参数。|  
  
6.  单击**应用**，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [创建发送端口](../core/creating-send-ports1.md)   
 [创建 TIBCO 企业消息服务接收处理程序](../core/creating-tibco-enterprise-message-service-receive-handlers.md)