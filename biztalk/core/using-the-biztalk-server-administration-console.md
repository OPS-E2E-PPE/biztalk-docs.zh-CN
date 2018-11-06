---
title: 使用 BizTalk Server 管理控制台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af00d9de-0f94-407b-b6f4-4da63a0867a0
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1cfae403a0161f87188b96460e8086cbf90d561
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753213"
---
# <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台
BizTalk Server 管理控制台是 Microsoft 管理控制台 (MMC) 可用于管理和监视 BizTalk Server 中，并且你可以用来部署和管理 BizTalk Server 应用程序。  
  
 左侧和右侧的 BizTalk Server 管理控制台，控制台树中，包含文件夹和子文件夹表示不同类型的可管理的项目。  
  
 当在控制台树中选择一个节点时，在管理控制台右侧的详细信息窗格显示有关项目的信息。  
  
 在控制台树中选择 BizTalk Server 管理节点显示起始页上，其中包含可执行，例如连接到现有 BizTalk Server 组的操作。 此外，开始页包括 BizTalk Server 文档和在线社区网站的链接。  
  
 有关使用键盘快捷键的管理控制台的信息，请参阅[管理控制台键盘快捷方式](../core/administration-console-keyboard-shortcuts.md)。  
  
## <a name="biztalk-server-artifacts"></a>BizTalk Server 项目  
 你可以管理使用 BizTalk Server 管理控制台的以下项目：  
  
-   **BizTalk 组**。 控制台树中的“BizTalk Group”节点包含表示该 BizTalk 组的项目（应用程序、参与方和平台设置）的其他节点。 BizTalk 组是组织的指通常表示企业、 部门、 中心或其他需要包含的 BizTalk Server 实现的业务部门单位。 BizTalk 组拥有与 BizTalk 管理数据库的一对一关系。 有关详细信息，请参阅[管理组](../core/managing-groups.md)。  
  
     当在 BizTalk Server 管理控制台中选择 BizTalk 组节点时，BizTalk Server 组中心页详细信息窗格中显示。 BizTalk Server 组中心页提供了 BizTalk Server 系统的运行状况的总体视图。 有关详细信息，请参阅[使用的组中心页](../core/using-the-group-hub-page.md)。  
  
-   **业务流程**。 业务流程使用业务流程设计器设计并部署到 BizTalk 组中的管理控制台在其下显示。 有关详细信息，请参阅[管理业务流程](../core/managing-orchestrations.md)。  
  
-   **角色链接**。 角色链接定义的角色之间的关系由两个方向的交互中使用的消息和端口类型定义。 有关详细信息，请参阅[管理角色链接](../core/managing-role-links.md)。  
  
-   **发送端口组**。 发送端口组是可用于将同一消息发送到单个配置中的多个目标的发送端口的命名的集合。 有关详细信息，请参阅[管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)。  
  
-   **发送端口**。 发送端口是发送消息的 BizTalk 对象。 有关详细信息，请参阅[管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)。  
  
-   **接收端口**。 接收端口是相似接收位置的逻辑分组。 有关详细信息，请参阅[管理接收端口](../core/managing-receive-ports.md)。  
  
-   **接收位置**。 入站的文档到达特定地址结合使用，通过 BizTalk Server 管道将处理在该地址接收的消息定义的接收位置。 有关详细信息，请参阅[管理接收位置](../core/managing-receive-locations.md)。  
  
-   **策略**。 策略是业务规则的版本控制集合。 有关详细信息，请参阅[管理策略](../core/managing-policies.md)。  
  
-   **架构**。 架构是一条消息的结构。 架构可以包含多个子架构。 有关详细信息，请参阅[管理架构](../core/managing-schemas.md)。  
  
-   **映射**。 地图是另一个规范中定义的记录和一个规范中的字段和记录和字段之间的对应关系的 XML 文件。 映射包含一个可扩展样式表语言 (XSL) 样式表，BizTalk Server 可使用该样式表执行该映射中所描述的转换。 有关详细信息，请参阅[管理映射](../core/managing-maps.md)。  
  
-   **管道**。 管道是软件基础结构，用于定义和链接一个或多个处理阶段，在规定的顺序完成特定任务中运行它们。 管道将处理过程分为多个阶段，阶段是对一类工作的抽象描述。 管道还确定了执行每类工作的顺序。 有关详细信息，请参阅[管理管道](../core/managing-pipelines.md)。  
  
-   **资源**。 资源是一个脚本、 部署的程序集或与应用程序关联的其他文件。 有关详细信息，请参阅[管理资源](../core/managing-resources.md)。  
  
-   **参与方**。 参与方是位于与业务流程交互的 BizTalk Server 之外的实体。 所有合作伙伴组织处理被视为参与方，并且你的组织可能具有数千个合作伙伴。 有关详细信息，请参阅[管理参与方](../core/managing-parties.md)。  
  
-   **平台设置**。 “平台设置”节点包含主机、主机实例、MessageBox 数据库和适配器等子节点。 有关详细信息，请参阅[管理平台设置](../core/managing-platform-settings.md)。  
  
    -   **主机**。 “主机”节点包含 BizTalk Server 环境中所有的进程内主机和独立主机。 BizTalk 主机是诸如适配器处理程序、接收位置（包括管道）和业务流程等项的逻辑容器。 有关详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
    -   **主机实例**。 “主机实例”节点包含当前 BizTalk Server 组中的所有主机实例。 主机实例是 BizTalk Server 运行时执行应用程序组件的进程。  
  
         使用“主机实例”节点，可以创建新的主机实例和刷新主机实例信息。 有关详细信息，请参阅[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)。  
  
    -   **服务器**。 “服务器”节点列出了加入 BizTalk Server 组的所有服务器。 这些是计算机，其中安装和配置，BizTalk Server，且正在运行的主机实例。 通过将服务器关联与特定主机创建的主机实例。 有关详细信息，请参阅[管理服务器](../core/managing-servers.md)。  
  
    -   **消息框**。 “MessageBox”节点包含当前 BizTalk Server 组使用的所有 MessageBox 数据库。 使用“MessageBox”节点，可以创建新的 MessageBox 数据库和刷新 MessageBox 数据库信息。 MessageBox 数据库是工作项之间的负载平衡服务器执行协作处理的基础。 工作项可以通过 MessageBox 数据库超过一次在其处理生命期。 MessageBox 数据库的名称不能超过 100 个字符。 有关详细信息，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。  
  
    -   **适配器**。 “适配器”节点包含为 BizTalk Server 组和关联适配器处理程序配置的所有发送和接收适配器的子节点。 适配器是用来发送和接收终结点之间的消息的消息传递中间件。 有关详细信息，请参阅[使用适配器](../core/using-adapters.md)。  

## <a name="tips-and-tricks"></a>提示和技巧

#### <a name="update-settings-for-multiple-hosts-and-host-instances-simultaneously"></a>同时更新多个主机和主机实例的设置
从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，可以选择多个主机和主机实例，并更新它的部分中的设置**设置仪表板**。

**步骤**:

1. 在 BizTalk 管理中，展开**BizTalk 组**，然后展开**平台设置**。
2. 选择**主机**。 在主机列表中，使用 CTRL 或 SHIFT 键同时选择多个主机。
3. 右键单击的主机选中，然后选中**设置**。 或者，选择**设置**操作窗格中。
4. 在设置仪表板、 常规和限制设置可以设置，并应用于多个主机所选。 
5. 接下来，选择**主机实例**。 在主机实例列表中，使用 CTRL 或 SHIFT 键同时选择多个主机实例。 在中**设置**，.NET CLR 和业务流程阻止设置可应用于所选的多个主机实例。 

> [!NOTE]
> 可以选择多个主机和主机实例的相同的主机类型。 如果主机类型不同，**设置**选项灰显。例如，如果您多选进程内主机和独立主机，然后**设置**灰显。

#### <a name="filter-artifacts-in-your-application"></a>在应用程序中的筛选器项目
从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，可以在应用程序中搜索的项目。 例如，您可以搜索特定的架构或业务流程应用程序中。 

**步骤**:

1. 在 BizTalk 管理中，展开**BizTalk 组**，展开**应用程序**，展开你的应用程序的项目之一。 例如，展开**BizTalk EDI 应用程序**。 
2. 选择**架构**。 在架构列表中，使用**搜索**框架构，搜索或筛选显示的架构。 例如，键入**x12**在搜索框中，然后按的 Enter。 显示与 X12 在名称中的所有架构。 清除您的搜索。 

    接下来，键入**批处理**在搜索框中，然后按的 Enter。 显示批处理架构。 
    
可以使用此搜索来查找或筛选与应用程序，包括发送端口、 资源、 映射和等等的所有项目。 

#### <a name="save-multiple-suspended-messages-simultaneously-to-a-file-within-group-hub"></a>同时将多个挂起的消息保存到组中心中的文件 
从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]，可以同时将多个挂起的消息保存到一个文件。

**步骤**:

1. 在 BizTalk 管理选择**BizTalk 组**
2. 选择**新查询**，并在查询中，**的搜索**

    搜索字段名称：  
    运算符： 等于  
    值： 消息
3. 选择**运行查询**。 在查询结果中，使用 CTRL 或 SHIFT 键同时选择多个挂起的实例。 右键单击，然后选择**安全文件**。 
4. 选择文件夹来保存文件。 保存时，会为每个消息创建一个 XML 文件。

## <a name="next-steps"></a>后续步骤
  
-   [打开 BizTalk Server 管理控制台](../core/how-to-open-the-biztalk-server-administration-console.md)  
  
-   [使用“组中心”页](../core/using-the-group-hub-page.md)
