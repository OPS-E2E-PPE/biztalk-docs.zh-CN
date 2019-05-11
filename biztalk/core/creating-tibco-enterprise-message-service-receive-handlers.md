---
title: 创建 TIBCO EMS 接收项目 |Microsoft Docs
description: 创建接收端口，并设置要在 BizTalk Server 中使用 TIBCO Enterprise Message Service 适配器的传输属性
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
ms.openlocfilehash: 27dd4ff3e317f178c2b9085cf531a6b963aafc7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390230"
---
# <a name="create-tibco-ems-receive-artifacts"></a>创建 TIBCO EMS 接收项目

## <a name="overview"></a>概述
TIBCO Enterprise Message Service 接收器是侦听器服务，注册特殊的队列或主题，并接收相关消息。 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器第一次注册与 TIBCO Enterprise Message Service 通过打开新的会话，，然后它会继续轮询以接收消息... 本部分介绍如何设置要连接到 TIBCO Enterprise Message Service 的接收端口以及如何将 XML 包含在您的业务流程在运行时与 TIBCO EMS 交互。  

## <a name="create-a-receive-port"></a>创建接收端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**接收端口**，选择**新建**，然后单击**单向接收端口**。  
  
3.  在中**接收端口属性**窗口，然后在**常规**页上，执行以下操作：  
  
    1.  在中**名称**字段中，键入`ReceiveFromTIBCOEMS`。  
  
    2.  在中**身份验证**组框中，指定如何处理消息时使用身份验证。  
  
    3.  选择**失败消息启用路由功能**复选框。  
  
4.  上**接收位置**页上，执行以下操作：  
  
    1.  单击 **“新建”**。  
  
    2.  在中**接收位置**窗口，然后在**常规**页上，键入**名称**的接收位置。  
  
    3.  从**类型**下拉列表中，选择传输类型和从**接收处理程序**下拉列表中，选择的传输地址。  
  
    4.  从**接收管道**下拉列表中，选择接收管道。  
  
    5.  上**计划**页上，选择**开始日期**并**结束日期**以限制接收文档。  
  
    6.  选择**启用服务时段**复选框。  
  
    7.  单击“确定” 。  
  
5.  上**入站映射**页上，选择用于转换所选端口上的文档的入站的映射。  
  
6.  上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。  
  
7.  单击“确定” 。  

## <a name="set-the-receive-port-transport-properties"></a>设置接收端口传输属性
用于 TIBCO Enterprise 消息系统 (EMS) 接收位置，则**URL**并**Target Namespace**到 TIBCO EMS 系统是所需的唯一配置值。    
 
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

## <a name="next-steps"></a>后续步骤
[TIBCO EMS 消息上下文属性](../core/message-context-properties-in-biztalk-server.md)