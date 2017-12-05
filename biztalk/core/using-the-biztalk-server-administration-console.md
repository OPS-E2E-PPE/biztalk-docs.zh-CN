---
title: "使用 BizTalk Server 管理控制台 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Administration Console [BizTalk Server], how to
- Administration Console [BizTalk Server], about Administration Console
- artifacts, list
- groups, Hub
ms.assetid: af00d9de-0f94-407b-b6f4-4da63a0867a0
caps.latest.revision: "42"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de8b806c8a6f39608608a3eabc975cf606410abc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台
BizTalk Server 管理控制台是 Microsoft 管理控制台 (MMC) 可用于管理和监视 BizTalk Server 中，并且你可以用来部署和管理你的 BizTalk Server 应用程序。  
  
 BizTalk Server 管理控制台，控制台树中，左侧组成文件夹和子文件夹表示不同类型的项目，你可以管理。  
  
 当在控制台树中选择一个节点时，管理控制台右侧的详细信息窗格中显示项目的信息。  
  
 在控制台树中选择 BizTalk Server 管理节点将显示起始页上，其中包含你可以执行的如连接到现有的 BizTalk Server 组的操作。 此外，开始页包括 BizTalk Server 文档和在线社区网站的链接。  
  
 有关使用用于管理控制台的键盘快捷方式的信息，请参阅[管理控制台键盘快捷方式](../core/administration-console-keyboard-shortcuts.md)。  
  
## <a name="biztalk-server-artifacts"></a>BizTalk Server 项目  
 你可以管理使用 BizTalk Server 管理控制台的以下项目：  
  
-   **BizTalk 组**。 控制台树中的“BizTalk Group”节点包含表示该 BizTalk 组的项目（应用程序、参与方和平台设置）的其他节点。 BizTalk 组是组织的通常表示企业、 部门、 中心或需要包含的 BizTalk Server 实现其他业务部门单元。 BizTalk 组具有一对一关系 BizTalk 管理数据库。 有关详细信息，请参阅[管理组](../core/managing-groups.md)。  
  
     在 BizTalk Server 管理控制台中选择 BizTalk 组节点，会将 BizTalk Server 组中心数据库页显示详细信息窗格中。 BizTalk Server 组中心数据库页提供了 BizTalk Server 系统的运行状况的总体视图。 有关详细信息，请参阅[使用组中心页](../core/using-the-group-hub-page.md)。  
  
-   **业务流程**。 业务流程使用 Orchestration 设计器设计和部署到在其下它将显示在管理控制台中的 BizTalk 组。 有关详细信息，请参阅[管理业务流程](../core/managing-orchestrations.md)。  
  
-   **角色链接**。 角色链接定义的角色之间的关系定义在两个方向的交互中使用的消息和端口类型。 有关详细信息，请参阅[管理角色链接](../core/managing-role-links.md)。  
  
-   **发送端口组**。 发送端口组是可用于将同一条消息发送到单个配置中的多个目标的发送端口的命名的集合。 有关详细信息，请参阅[管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)。  
  
-   **发送端口**。 发送端口是将消息发送一个 BizTalk 对象。 有关详细信息，请参阅[管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)。  
  
-   **接收端口**。 接收端口是类似的接收位置的逻辑分组。 有关详细信息，请参阅[管理接收端口](../core/managing-receive-ports.md)。  
  
-   **接收位置**。 接收位置被定义为特定地址的入站的文档到达结合 BizTalk Server 管道处理该地址处收到的消息。 有关详细信息，请参阅[管理接收位置](../core/managing-receive-locations.md)。  
  
-   **策略**。 策略是版本控制的业务规则集合。 有关详细信息，请参阅[管理策略](../core/managing-policies.md)。  
  
-   **架构**。 架构是一条消息的结构。 架构可以包含多个子架构。 有关详细信息，请参阅[管理架构](../core/managing-schemas.md)。  
  
-   **地图**。 映射是另一个规范中定义的记录和一个规范中的字段的记录和字段之间的对应关系的 XML 文件。 映射包含一个可扩展样式表语言 (XSL) 样式表，BizTalk Server 可使用该样式表执行该映射中所描述的转换。 有关详细信息，请参阅[管理地图](../core/managing-maps.md)。  
  
-   **管道**。 管道是一个软件基础结构，用于定义并链接一个或多个处理阶段，在预先指定的顺序来完成特定任务中运行它们。 管道将处理过程分为多个阶段，阶段是对一类工作的抽象描述。 管道还确定了执行每类工作的顺序。 有关详细信息，请参阅[管理管道](../core/managing-pipelines.md)。  
  
-   **资源**。 资源是一个脚本，部署的程序集或与应用程序关联其他文件。 有关详细信息，请参阅[管理资源](../core/managing-resources.md)。  
  
-   **方**。 当事方是与业务流程交互的 BizTalk Server 之外的实体。 所有处理你的组织伙伴被视为方，并且你的组织可能具有多个千位合作伙伴。 有关详细信息，请参阅[管理方](../core/managing-parties.md)。  
  
-   **平台设置**。 “平台设置”节点包含主机、主机实例、MessageBox 数据库和适配器等子节点。 有关详细信息，请参阅[管理平台设置](../core/managing-platform-settings.md)。  
  
    -   **主机**。 “主机”节点包含 BizTalk Server 环境中所有的进程内主机和独立主机。 BizTalk 主机是诸如适配器处理程序、接收位置（包括管道）和业务流程等项的逻辑容器。 有关详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
    -   **托管实例**。 “主机实例”节点包含当前 BizTalk Server 组中的所有主机实例。 主机实例是 BizTalk Server 运行时执行应用程序组件的过程。  
  
         使用“主机实例”节点，可以创建新的主机实例和刷新主机实例信息。 有关详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
    -   **服务器**。 “服务器”节点列出了加入 BizTalk Server 组的所有服务器。 这些是计算机，其中 BizTalk Server 是安装和配置，且主机实例正在运行。 通过将服务器关联与特定主机创建主机实例。 有关详细信息，请参阅[管理服务器](../core/managing-servers.md)。  
  
    -   **消息框**。 “MessageBox”节点包含当前 BizTalk Server 组使用的所有 MessageBox 数据库。 使用“MessageBox”节点，可以创建新的 MessageBox 数据库和刷新 MessageBox 数据库信息。 MessageBox 数据库是工作项之间的负载平衡进行协作处理的服务器的基础。 工作项可以通过传递 MessageBox 数据库不止一次在其处理生命期。 MessageBox 数据库的名称不能超过 100 个字符。 有关详细信息，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。  
  
    -   **适配器**。 “适配器”节点包含为 BizTalk Server 组和关联适配器处理程序配置的所有发送和接收适配器的子节点。 适配器是用来发送和接收终结点之间的消息的消息传递中间件。 有关详细信息，请参阅[使用适配器](../core/using-adapters.md)。  

## <a name="tips-and-tricks"></a>提示和技巧

#### <a name="update-settings-for-multiple-hosts-and-host-instances-simultaneously"></a>同时更新多个主机和主机实例的设置
从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，你可以选择多个主机和主机实例，并更新它的部分中的设置**设置仪表板**。

**步骤**:

1. 在 BizTalk 管理，展开**BizTalk 组**，然后展开**平台设置**。
2. 选择**主机**。 在主机列表中，使用 CTRL 或 SHIFT 键选择多个主机同时。
3. 右键单击的主机选中，然后选中**设置**。 或者，选择**设置**在操作窗格中。
4. 设置仪表板中的常规和限制设置可以设置，并应用于多个主机所选。 
5. 接下来，选择**主机实例**。 在主机实例列表中，使用 CTRL 或 SHIFT 键同时选择多个主机实例。 在**设置**，.NET CLR 和限制设置的业务流程可以应用到所选的多个主机实例。 

> [!NOTE]
> 你可以选择多个主机和主机具有相同的主机类型的实例。 如果主机类型不同，**设置**选项将灰显。例如，如果你选择多进程内主机和一个独立主机，然后**设置**灰显。

#### <a name="filter-artifacts-in-your-application"></a>你的应用程序中的筛选器项目
从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，您可以搜索你的应用程序中的项目。 例如，你可以搜索特定的架构或应用程序中的业务流程。 

**步骤**:

1. 在 BizTalk 管理，展开**BizTalk 组**，展开**应用程序**，，展开其中一个应用程序的项目。 例如，展开**BizTalk EDI 应用程序**。 
2. 选择**架构**。 在架构列表中，使用**搜索**框架构，搜索或筛选显示的架构。 例如，在中键入**x12**在搜索框中，然后按的 Enter。 显示与 X12 名称中的所有架构。 清除您的搜索。 

    接下来，在键入**批处理**在搜索框中，然后按的 Enter。 显示的批处理架构。 
    
可以使用此搜索来查找或筛选与应用程序，包括发送端口、 资源、 映射和等等的任何项目。 

#### <a name="save-multiple-suspended-messages-simultaneously-to-a-file-within-group-hub"></a>将多个挂起的消息同时保存到组中心数据库中的文件 
从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，你可以将多个挂起的消息同时保存到文件。

**步骤**:

1. 在 BizTalk 管理，选择**BizTalk 组**
2. 选择**新查询**，并在查询中，**的搜索**

    搜索字段名称：  
    运算符： 等于  
    值： 消息
3. 选择**运行查询**。 在查询结果中，使用 CTRL 或 SHIFT 键同时选择多个挂起的实例。 右键单击，然后选择**安全文件**。 
4. 选择文件夹来保存文件。 保存时，为每个消息创建一个 XML 文件。

## <a name="in-this-section"></a>本节内容  
  
-   [如何打开 BizTalk Server 管理控制台](../core/how-to-open-the-biztalk-server-administration-console.md)  
  
-   [配置使用 BizTalk Server 管理控制台的跟踪](http://msdn.microsoft.com/en-us/49b7f9d3-60b5-41bd-ba8b-029253926bef)  
  
-   [使用“组中心”页](../core/using-the-group-hub-page.md)