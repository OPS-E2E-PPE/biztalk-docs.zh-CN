---
title: 创建 TIBCO EMS 接收项目 |Microsoft 文档
description: 创建接收端口，并设置要在 BizTalk Server 中使用 TIBCO 企业消息服务适配器传输属性
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1307e3c-0237-4f19-a642-58e694fe95d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5810dc012c7aa5dcc2fbdfcecd9d59d066ced7
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015372"
---
# <a name="create-tibco-ems-receive-artifacts"></a>创建 TIBCO EMS 接收项目

## <a name="overview"></a>概述
TIBCO Enterprise Message Service 接收器是一种侦听服务，可以注册特殊的队列或主题，并接收相关消息。 TIBCO Enterprise Message Service 的 BizTalk 适配器首先通过打开一个新会话向 TIBCO Enterprise Message Service 注册，然后继续轮询以接收消息。 该部分介绍了如何设置接收端口以连接到 TIBCO Enterprise Message Service，如何在您的业务流程中加入 XML 以在运行时与 TIBCO EMS 进行交互。  

## <a name="create-a-receive-port"></a>创建接收端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**接收端口**，选择**新建**，然后单击**单向接收端口**。  
  
3.  在**接收端口属性**窗口，请在**常规**页上，执行以下操作：  
  
    1.  在**名称**字段中，键入`ReceiveFromTIBCOEMS`。  
  
    2.  在**身份验证**组框中，指定使用身份验证时处理消息的方式。  
  
    3.  选择**启用路由失败消息**复选框。  
  
4.  上**接收位置**页上，执行以下操作：  
  
    1.  单击 **“新建”**。  
  
    2.  在**接收位置**窗口，请在**常规**页上，键入**名称**的接收位置。  
  
    3.  从**类型**下拉列表中，选择传输类型，并从**接收处理程序**下拉列表中，选择的传输地址。  
  
    4.  从**接收管道**下拉列表中，选择接收管道。  
  
    5.  上**计划**页上，选择**开始日期**和**结束日期**限制接收的文档。  
  
    6.  选择**启用服务窗口**复选框。  
  
    7.  单击 **“确定”**。  
  
5.  上**入站映射**页上，选择转换所选的端口上的文档的入站的映射。  
  
6.  上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。  
  
7.  单击 **“确定”**。  

## <a name="set-the-receive-port-transport-properties"></a>设置接收端口传输属性
TIBCO 企业消息系统 (EMS) 接收位置， **URL**和**目标 Namespace**到 TIBCO EMS 系统是所需的唯一配置值。    
 
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

## <a name="next-steps"></a>后续步骤
[TIBCO EMS 消息上下文属性](../core/message-context-properties-in-biztalk-server.md)