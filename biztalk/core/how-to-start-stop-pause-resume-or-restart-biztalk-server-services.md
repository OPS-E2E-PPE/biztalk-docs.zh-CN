---
title: 步骤重启服务，或关闭 |Microsoft 文档
description: 启动、 停止、 暂停、 继续或重新启动 BizTalk Server 服务，或关闭 BizTalk Server 计算机
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d6449ba-2892-49c6-a697-847608d10ec5
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9860625480c2c3e469736989415b4e1510cf6707
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973403"
---
# <a name="restart-biztalk-services-or-shut-down-the-biztalk-server"></a>重新启动 BizTalk 服务，或关闭 BizTalk Server

下表列出了可以启动、停止、暂停、恢复或重新启动的 BizTalk Server 服务：  
  
|Name|说明|启动类型|依赖关系|  
|----------|-----------------|------------------|------------------|  
|BizTalk 服务 BizTalk 组：  *\<BizTalkServerApplication\>*|提供 BizTalk Server 应用程序服务。|自动|-企业单一登录 (SSO) 服务<br />事件日志<br />-远程过程调用 (RPC)|  
|企业单一登录服务|提供对企业应用程序的单一登录服务。|自动|已在本地安装 SQL Server：<br /><br /> 的系统 COM + 应用程序<br />-远程过程调用 (RPC)<br />SQL Server (MSSQLSERVER)<br /><br /> 已远程安装 SQL Server：<br /><br /> 的系统 COM + 应用程序<br />-远程过程调用 (RPC) 无|  
|规则引擎更新服务|通知用户有关部署或取消部署策略的信息。|Automatic|无|  
  
 
## <a name="start-stop-pause-resume-or-restart-a-biztalk-server-service"></a>启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务  
 你可以启动、 停止、 暂停、 恢复或通过使用 Services.msc，或者使用命令提示符重新启动 BizTalk Server 服务。

### <a name="prerequisites"></a>先决条件  
 若要执行该过程，您必须是本地计算机上 Administrators 组的成员，或者您必须被委派了相应的权限。 如果该计算机已加入域，则 Domain Admins 组的成员可能可以执行此过程。 作为安全最佳实践，可考虑使用“运行”来执行此过程。 
  
### <a name="use-services-in-control-panel"></a>使用控制面板中的服务  
  
1.  打开“服务”。 单击**启动**，单击**运行**，然后键入**services.msc**。  
  
2.  右键单击相应的 BizTalk Server 服务，然后单击**启动**，**停止**，**暂停**，**恢复**，或**重新启动**。  
  
### <a name="use-a-command-prompt"></a>使用命令提示符  
  
1.  从开始菜单中，右键单击**命令提示符**，选择**详细**，然后选择**以管理员身份运行**
  
2.  键入以下内容，其中*ServiceName*是你想要启动、 停止、 暂停或恢复的 BizTalk Server 服务的名称：  
  
    -   若要启动服务，则键入：  
  
         **net 开始** *ServiceName*  
  
    -   若要停止服务，则键入：  
  
         **net stop** *ServiceName*  
  
    -   若要暂停服务，则键入：  
  
         **net 暂停** *ServiceName*  
  
    -   若要恢复服务，则键入：  
  
         **net 继续** *ServiceName*  

    |BizTalk 服务|ServiceName|  
    |---|---|  
    |BizTalk 服务 BizTalk 组：BizTalkServerApplication|btssvc$biztalkserverapplication|  
    |企业单一登录服务|Entsso|  
    |规则引擎更新服务|ruleengineupdateservice|
  
## <a name="shut-down-biztalk-server"></a>关闭 BizTalk Server  

### <a name="prerequisites"></a>先决条件  
-   使用是你想要关闭的 BizTalk server 上的本地管理员组的成员的帐户登录。 这是必需的，这样您才能停止服务。  
-   使用 BizTalk Server Administrators 组或 BizTalk Server Operators 组的成员的帐户登录。 

### <a name="task-overview"></a>任务概述
1.  禁用接收位置，并通过对每个活动应用程序执行部分停止来停止业务流程和发送端口。 仅当您要删除或重新部署应用程序时才应执行完全停止。 有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
2.  停止主机实例。 有关详细信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。  
  
3.  关闭 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。 请参阅**如何开始、 停止、 暂停、 继续或重新启动 BizTalk Server Services** （本主题中）。
  
4.  关闭 Internet 信息服务 (IIS)，或停止 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序池和网站。 如果您要完全关闭服务器，可以跳过此步骤。 如果您停止 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的目的是进行维护或者是部署或取消部署 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序，则应当执行该步骤。 当您仅停止与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 相关的网站和应用程序池时，其他 IIS 相关进程将继续运行。  
  
     如何继续执行此步骤在某种程度上取决于您使用的 IIS 版本。 IIS 6 允许您停止应用程序池和网站。 通过 IIS 6，您还可以停止 IIS 管理服务，以关闭包括应用程序池和网站在内的所有 IIS 活动。 IIS 7.0 比 IIS 6.0 更加模块化 ， 而且没有可用于停止所有 IIS 7.0 活动的单个开关 ， 因此您需要单独停止网站和应用程序池 。  
  
     应用程序池和 BizTalk Server 使用的虚拟应用程序 （网站和 Web 服务） 的列表，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。  
  
 有关启动和停止在 IIS 中的应用程序池的信息，请参阅[http://go.microsoft.com/fwlink/?LinkID=140513](http://go.microsoft.com/fwlink/?LinkID=140513)。  
  
 有关启动和停止 IIS 中的 Web 服务器的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=140695](http://go.microsoft.com/fwlink/?LinkId=140695)。  
  
## <a name="see-also"></a>另请参阅  
 [如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)   
 [如何停止主机实例](../core/how-to-stop-a-host-instance.md)   