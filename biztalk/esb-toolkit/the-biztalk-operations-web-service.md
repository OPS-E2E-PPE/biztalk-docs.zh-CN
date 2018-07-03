---
title: BizTalk 操作 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af38815f-f643-4598-9148-6499071d12e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b9a78dddbbd76566c5c97b1e571e5ad80073d4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997966"
---
# <a name="the-biztalk-operations-web-service"></a>BizTalk 操作 Web 服务
Microsoft BizTalk 操作 Web 服务公开的对象和 BizTalk Server 中的消息有关的信息。 服务名称是**ESB.BizTalkOperationsService**，并且服务会公开各种返回诸如主机、 业务流程、 应用程序，以及 BizTalk 应用程序状态的列表的方法。  
  
 以下方法有：  
  
-   **应用程序**。 此方法采用任何参数，并返回的名称和说明的所有已安装的 BizTalk 应用程序作为一系列**BTApplication**对象。  
  
-   **ApplicationStatus**。 此方法将作为参数的应用程序名称，并返回有关指定的 BizTalk 应用程序作为信息**BTSysStatus**实例。 此信息包括业务流程、 发送端口、 接收位置和主机的详细信息。  
  
-   **GetLiveMessageBody**。 消息 ID 和实例 ID，此方法将作为参数并返回该消息的正文从与实时环境**BTMsgBody**实例。  
  
-   **GetMessageInstances**。 此方法将作为参数的消息类型，并返回匹配的所有消息作为一系列**BTMsgInstance**对象。  
  
-   **GetOrchestrationInstances**。 此方法将作为参数的业务流程名称和它返回的集合**BTOrchestrationInstance**包含匹配的业务流程的详细信息的对象。  
  
-   **GetTrackedMessageBody**。 此方法将作为参数的消息的 GUID，并返回作为该消息的正文**BTMsgBody**实例后在 BizTalk 中进行处理。  
  
-   **主机**。 此方法将作为参数的名称的主机，并返回作为一系列指定的主机实例的信息**BTHost**实例。 使用主机名称参数为空字符串返回有关所有主机实例的信息。  
  
-   **MessageFlowTree**。 此方法将作为参数的实例 ID，并返回作为该消息的消息流的详细信息**RouteTreeNode**实例。  
  
-   **业务流程**。 此方法将作为参数的业务流程名称并返回作为该业务流程的所有信息**BTSysStatus**实例。 业务流程名称参数为空字符串用于返回有关所有业务流程的信息。  
  
-   **ReceiveLocations**。 此方法将作为参数的名称的接收位置，并返回匹配位置的所有信息**BTSysStatus**实例。 接收位置名称参数为空字符串用于返回有关所有位置的信息。  
  
-   **ReceiveLocationsByDescription**。 此方法将作为参数的说明接收位置，并返回匹配位置的所有信息**BTSysStatus**实例。 Description 参数为空字符串用于返回有关所有位置的信息。  
  
-   **发送端口**。 此方法将作为参数的名称的发送端口，并返回匹配的端口的所有信息**BTSysStatus**实例。 发送端口名称参数为空字符串用于返回有关所有端口的信息。  
  
-   **SendPortsByDescription**。 此方法将作为参数的说明的发送端口，并返回匹配的端口的所有信息**BTSysStatus**实例。 使用 description 参数为空字符串返回有关所有端口的信息。  
  
-   **StatusChanged**。 此方法采用一个参数作为一个时间戳，并返回作为指定的时间戳以来修改的 BizTalk 对象 （如端口、 主机和业务流程） 的详细信息**BTSysStatus**实例。  
  
-   **SystemStatus**。 此方法采用任何参数，并返回作为 BizTalk 系统状态的完整详细信息**BTSysStatus**实例。  
  
-   **UpdateReceiveLocationDescription**。 此方法更新使用包含应用程序名称、 接收端口名称、 接收位置名称和接收位置描述的参数值的指定的接收位置的说明。 它返回一个字符串，表示操作的结果。 请注意测试客户端应用程序从其 App.config 文件中读取此信息。  
  
-   **UpdateSendPortDescription**。 此方法将更新指定的发送端口使用包含发送端口名称和发送端口描述的参数值的说明。 它返回一个字符串，表示操作的结果。 请注意测试客户端应用程序从其 App.config 文件中读取此信息。  
  
## <a name="configuring-the-biztalk-operations-web-service"></a>配置 BizTalk 操作 Web 服务  
 BizTalk 操作 Web 服务或者直接与 BizTalk Server 管理数据库使用 Windows Management Instrumentation (WMI) 通信或它使用 BizTalk 操作和资源管理器 API 来获取所需的信息。 因此，必须确保你的系统满足以下条件和配置以下安全权限设置：  
  
- 设置**allowOverride**到计算机级别的 Web.config 文件中的属性**false**以确保开发人员不能更改他们的应用程序的信任级别。  
  
- 默认情况下，BizTalk 操作 Web 服务未配置为需要安全套接字层 (SSL) 客户端进行访问时。 应配置服务，因此它需要 SSL 客户端访问和保护 Internet 信息服务 (IIS) Web 服务主机计算机和运行托管 BizTalkMgmtDb 数据库使用 SQL Server 的计算机之间的连接网络级别 IPSec 和相应的文件级访问控制列表 (ACL) 权限。  
  
- 访问 BizTalk 操作 Web 服务的用户必须对某些方法的默认 BizTalk Server Administrators 组的成员和其他方法的默认 BizTalk Application Users 组的成员。  
  
- 必须确保 BizTalk 操作 Web 服务驻留在名为已禁用匿名访问的 ESB.BizTalkOperationsService 的 IIS 虚拟目录中。  
  
- 用户必须具有**选择**位于 BizTalkMgmtDb 数据库和在 BizTalkMsgBoxDb 数据库中的 SQL Server 中的多个表的权限。 使用 SQL Server Management Studio 设置以下权限：  
  
  -   在 BizTalkMgmtDb 数据库中，配置具有 BTS_ADMIN_USERS 数据库角色**选择**以下表的权限：  
  
      -   adm_Server2HostMapping  
  
      -   adm_Server  
  
      -   adm_hostInstance  
  
  -   在 BizTalkMsgBoxDb 数据库中，配置具有 BTS_ADMIN_USER 数据库角色**选择**ProcessHeartbeats 表的权限。  
  
  在 SQL Server Management Studio，可以配置所需的权限。 若要执行此操作，请展开**安全**在对象资源管理器的左的窗格树视图中，展开**角色**，展开**DatabaseRoles**、 选择 BTS_ADMIN_USERS 角色，然后编辑对于此角色，如图 1 中所示的属性。  
  
  ![SQL Server 管理 Studio](../esb-toolkit/media/ch4-sqlservermgmtstudio.gif "Ch4 SQLServerMgmtStudio")  
  
  **图 1**  
  
  **编辑 Microsoft SQL Server Management Studio 中的 BTS_ADMIN_USERS 数据库角色的权限**  
  
> [!NOTE]
>  必须配置为使用 Windows 集成安全性并在内置网络服务帐户下运行此服务。 您还必须启用 Kerberos 身份验证在 IIS Web 服务器上，以便它将发送标头**Negotiate、 NTLM**到客户端。 有关详细信息，请参阅[如何配置 IIS 以用于网络身份验证支持 Kerberos 协议和 NTLM 协议](http://go.microsoft.com/fwlink/?LinkId=186430)([http://go.microsoft.com/fwlink/?LinkId=186430](http://go.microsoft.com/fwlink/?LinkId=186430))。  
>   
>  默认情况下，BizTalk 操作 Web 服务未配置为需要 SSL 客户端进行访问时。 应配置服务，因此它需要 SSL 客户端访问和保护 IIS Web 服务主机计算机和服务器托管 UDDI 服务使用网络级别 IPSec 和相应的文件级 ACL 权限之间的连接。