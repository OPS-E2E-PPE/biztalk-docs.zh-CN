---
title: 重新启动服务，或关闭的情况下的步骤 |Microsoft Docs
description: 启动、 停止、 暂停、 继续或重新启动 BizTalk Server 服务，或关闭的情况下 BizTalk Server 计算机
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
ms.openlocfilehash: 85e8c353e4a8fa157352aa62238b107a07831465
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333981"
---
# <a name="restart-biztalk-services-or-shut-down-the-biztalk-server"></a>重新启动 BizTalk 服务中，或关闭 BizTalk Server

下表列出了可以启动、 停止、 暂停、 恢复或重新启动的 BizTalk Server 服务：  
  
|“属性”|Description|启动类型|依存关系|  
|----------|-----------------|------------------|------------------|  
|BizTalk 服务 BizTalk 组：*\<BizTalkServerApplication\>*|提供 BizTalk Server 应用程序服务。|自动|企业单一登录 (SSO) 服务<br />事件日志<br />-远程过程调用 (RPC)|  
|企业单一登录服务|提供对企业应用程序的单一登录服务。|自动|在本地安装的 SQL server:<br /><br /> -COM + 系统应用程序<br />-远程过程调用 (RPC)<br />-   SQL Server (MSSQLSERVER)<br /><br /> 远程安装了 SQL server:<br /><br /> -COM + 系统应用程序<br />-远程过程调用 (RPC) 无|  
|规则引擎更新服务|通知用户有关部署或取消部署策略的信息。|Automatic|None|  
  
 
## <a name="start-stop-pause-resume-or-restart-a-biztalk-server-service"></a>启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务  
 可以启动、 停止、 暂停、 恢复或通过使用 Services.msc，或者使用命令提示符重新启动 BizTalk Server 服务。

### <a name="prerequisites"></a>先决条件  
 若要执行此过程，您必须是本地计算机上 Administrators 组的成员或您必须被委派了适当的权限。 如果将计算机加入到域中，Domain Admins 组的成员可以执行此过程。 作为安全性最佳实践，请考虑使用运行方式来执行此过程。 
  
### <a name="use-services-in-control-panel"></a>使用控制面板中的服务  
  
1.  打开服务。 单击**启动**，单击**运行**，然后键入**services.msc**。  
  
2.  右键单击相应的 BizTalk Server 服务，然后单击**启动**，**停止**，**暂停**，**恢复**，或**重新启动**。  
  
### <a name="use-a-command-prompt"></a>使用命令提示符  
  
1.  从开始菜单中，右键单击**命令提示符**，选择**详细**，然后选择**以管理员身份运行**
  
2.  键入以下内容，其中*ServiceName*是你想要启动、 停止、 暂停或恢复的 BizTalk Server 服务的名称：  
  
    -   若要启动服务，请键入：  
  
         **net start** *ServiceName*  
  
    -   若要停止服务，请键入：  
  
         **net stop** *ServiceName*  
  
    -   若要暂停服务，请键入：  
  
         **net pause** *ServiceName*  
  
    -   若要恢复服务，请键入：  
  
         **net continue** *ServiceName*  

    |BizTalk 服务|ServiceName|  
    |---|---|  
    |BizTalk 服务 BizTalk 组：BizTalkServerApplication|btssvc$biztalkserverapplication|  
    |企业单一登录服务|Entsso|  
    |规则引擎更新服务|ruleengineupdateservice|
  
## <a name="shut-down-biztalk-server"></a>关闭 BizTalk Server  

### <a name="prerequisites"></a>先决条件  
-   使用该帐户是你想要关闭的情况下在 BizTalk server 上的本地管理员组的成员登录。 这是必需的因此可以停止服务。  
-   使用 BizTalk Server Administrators 组或 BizTalk Server Operators 组的成员帐户登录。 

### <a name="task-overview"></a>任务概述
1. 禁用接收位置，并停止业务流程和发送端口通过对每个活动的应用程序执行部分停止。 仅当你想要删除或重新部署应用程序，你应执行完全停止。 有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
2. 停止主机实例。 有关详细信息，请参阅[如何停止主机实例](../core/how-to-stop-a-host-instance.md)。  
  
3. 关闭[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。 请参阅**如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services** （在本主题中）。
  
4. 关闭关闭 Internet 信息服务 (IIS) 或停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序池和网站。 如果想要关闭服务器完全可以跳过此步骤。 如果您要停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行维护或进行部署或取消部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序中，应执行此步骤。 当停止网站和应用程序池与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，其他与 IIS 相关的进程将继续运行。  
  
    如何继续进行此步骤取决于您所使用的 IIS 版本在某种程度上。 IIS 6 允许您停止应用程序池和网站。 使用 IIS 6 还可以停止 IIS 管理服务，以关闭包括应用程序池和网站的所有 IIS 活动。 IIS 7.0 比 IIS 6.0 更加模块化，并且没有可用于停止 IIS 7.0 的所有活动，因此将需要单独都停止网站和应用程序池的单个开关。  
  
    应用程序池和 BizTalk Server 使用的虚拟应用程序 （网站和 Web 服务） 的列表，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。  
  
   有关启动和停止应用程序池在 IIS 中的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=140513 ](http://go.microsoft.com/fwlink/?LinkID=140513)。  
  
   有关启动和停止 IIS 中的 Web 服务器的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=140695 ](http://go.microsoft.com/fwlink/?LinkId=140695)。  
  
## <a name="see-also"></a>请参阅  
 [如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)   
 [如何停止主机实例](../core/how-to-stop-a-host-instance.md)   