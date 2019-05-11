---
title: 如何安装群集 SSO 和 BizTalk 主机在同一群集组 1 中 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 413cc8f4-f343-4c1c-8b79-3b15cb4c101d
caps.latest.revision: 44
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e8fef44d59a12c42da35d85e0c4357ca7fce5b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342355"
---
# <a name="cluster-sso-and-a-biztalk-host-in-the-same-cluster-group"></a>群集 SSO 和 BizTalk 主机在同一群集组中
使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]您可以在同一 Windows Server 群集上群集一个或多个 BizTalk 主机和企业单一登录 (SSO) 服务。  
  
> [!NOTE]
>  正确实现此策略需要为群集资源在同一群集组中创建任何 BizTalk 主机实例和 SSO 服务。  
  
 将 Windows 群集与一个或多个 BizTalk 主机和 SSO 通常属于以下类别之一：  
  
1. SSO 主密钥服务器和同一群集组中的一个或多个 BizTalk 主机，聚类分析。  
  
    在此方案中，群集的 BizTalk 主机和群集的 SSO 服务之间的依赖关系被维护，因此，如果群集组故障转移，所有资源都移动组。  
  
    如果 SSO 服务配置为群集资源上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，你必须在同一群集组中创建群集的 IIS web 服务。 这必须进行以确保所有独立的主机实例将在运行 SSO 服务的群集节点上运行。 这可确保在独立主机实例中运行的任何适配器将具有为 SSO 服务的访问，因为独立主机实例在 IIS 中运行。  
  
   > [!NOTE]
   >  如果非群集的 BizTalk 主机的实例正在运行群集的 SSO 服务的实例在同一群集节点上，SSO 服务的群集的实例不能被故障转移，除非停止 BizTalk 主机的非群集的实例。 非群集的 BizTalk 主机的实例维护依赖于群集节点上运行的 SSO 服务的群集实例，并阻止故障转移群集的 SSO 服务的实例。 出于此原因，建议您不要创建非群集的 BizTalk 主机，若要运行 SSO 服务的群集的实例在同一群集节点上运行的实例。  
  
2. 群集 SSO 服务 （非主密钥服务器） 和同一群集组中的一个或多个 BizTalk 主机。 此方案要求远程主密钥服务器可用。 在此方案中，因此，如果群集组故障转移，所有资源都移动与组维护群集的 BizTalk 主机和群集的 SSO 服务之间的依赖关系。  
  
    如果 SSO 服务配置为群集资源上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机，你必须在同一群集组中创建群集的 IIS web 服务。 这必须进行以确保所有独立的主机实例将在运行 SSO 服务的群集节点上运行。 这可确保在独立主机实例中运行的任何适配器将具有为 SSO 服务的访问，因为独立主机实例在 IIS 中运行。  
  
   > [!NOTE]
   >  除非停止 BizTalk 主机的非群集的实例，如果非群集的 BizTalk 主机实例运行相同的群集节点上群集的 SSO 服务的实例然后运行 SSO 服务的群集的实例无法故障转移。 BizTalk 主机的非群集实例维护依赖于群集节点上运行的 SSO 服务的群集实例，并阻止 SSO 服务的群集的实例故障转移。 出于此原因，建议您创建的非群集的 BizTalk 主机，若要运行 SSO 服务的群集的实例在同一群集节点上运行的实例。  
  
3. 不群集 SSO 服务的情况下，Windows Server 群集上群集一个或多个 BizTalk 主机。 在此方案中，一个或多个 BizTalk 主机配置为群集资源，但 SSO 服务未配置为群集资源。 这种设计为群集的 BizTalk 主机提供高可用性，但不用于 SSO 服务提供高可用性。 在此方案中，如果一个节点上的 SSO 服务失败然后在该节点依赖于 SSO 的 BizTalk Server 组件也将失败。 有关如何将 BizTalk Server 主机配置为群集资源的详细信息请参阅[将 BizTalk 主机配置为群集资源](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)。  
  
   下面的过程介绍应遵循相同的 Windows Server 群集上群集 BizTalk 主机和 SSO 服务的步骤。  
  
## <a name="cluster-a-biztalk-host-and-the-sso-master-secret-server-on-the-same-windows-server-cluster"></a>在同一 Windows Server 群集上群集 BizTalk 主机和 SSO 主密钥服务器  
  
1. 如果不使用群集分布式事务处理协调器 (MSDTC) 资源配置群集，对 MSDTC 进行群集上的 Windows Server 故障转移群集中的步骤[核对清单：在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/p/?LinkID=129677)(http://go.microsoft.com/fwlink/p/?LinkID=129677)。  
  
2. 安装和配置 Windows Server 群集上的 SSO 服务，按照中的步骤[群集主密钥服务器](how-to-cluster-the-master-secret-server1.md)。 由于在 Windows Server 群集上运行 BizTalk Server，安装所有必需的 BizTalk Server 组件，即使您只配置 SSO 组件这一次也是如此。  
  
3. 按照中所述的步骤在 BizTalk Server 计算机上群集 IIS [Microsoft 知识库文章 970759"配置 IIS 7.0 中 Microsoft Windows Server 2008 故障转移群集"](http://go.microsoft.com/fwlink/p/?LinkId=152793) (<http://go.microsoft.com/fwlink/p/?LinkId=152793>)。 在与群集 SSO 服务相同的群集组中创建群集的 IIS Web 服务。  
  
4. 将包含群集的 SSO 服务到一个群集节点的群集组移并登录到此群集节点上。  
  
5. 启动 BizTalk Server 配置程序，并完成此群集节点上的 BizTalk Server 配置。 由于这是组中的第一个 BizTalk Server 计算机，单击**创建新的 BizTalk 组**配置 BizTalk 组时。  
  
6. 已成功完成 BizTalk Server 配置后，将包含群集的 SSO 服务到另一个群集节点，并登录到此群集节点的群集组。  
  
7. 启动 BizTalk Server 配置程序，并完成此群集节点上的 BizTalk Server 配置。 单击**加入现有 BizTalk 组**此群集节点上，配置 BizTalk 组组件时，指定第一个节点创建的 BizTalk 组。  
  
8. 已成功完成 BizTalk Server 配置后，创建一个或多个群集 BizTalk 主机中的步骤[将 BizTalk 主机配置为群集资源](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)。  
  
   > [!NOTE]
   >  在此方案中，所有 BizTalk 主机都必须都创建为群集 SSO 服务资源所在的群集组中的群集资源。 其中群集 SSO 服务的 Windows Server 群集节点上运行的非群集的 BizTalk 主机实例不是受支持的配置。 这是因为当群集的 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集的 BizTalk 主机实例将失败。  
  
## <a name="cluster-a-biztalk-host-and-sso-non-master-secret-server-on-the-same-windows-server-cluster-when-the-sso-master-secret-server-is-remote"></a>相同的 Windows Server 群集上群集 BizTalk 主机和 SSO （非主密钥服务器），当 SSO 主密钥服务器是远程数据库  
  
1. 如果不使用群集分布式事务处理协调器 (MSDTC) 资源配置群集，对 MSDTC 进行群集上的 Windows Server 故障转移群集中的步骤[核对清单：在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/p/?LinkID=129677)(http://go.microsoft.com/fwlink/p/?LinkID=129677)。  
  
2. 创建域组的名称**SSO Administrators**并**SSO Affiliate Administrators**。 若要创建群集的 SSO 服务的实例，必须创建**SSO Administrators**并**SSO Affiliate Administrators**为域组的组。  
  
3. 创建或指定的成员的域帐户**SSO Administrators**域组。 每个节点上的 SSO 服务将配置为作为此域帐户登录。 此帐户必须具有**作为服务登录**直接在群集中每个节点上。  
  
4. 添加的帐户，您用来登录到域安装和配置流程期间**SSO Administrators**组。  
  
   > [!IMPORTANT]
   >  如果未完成步骤 3 和 4，SSO 服务的配置将失败。  
  
5. 登录到其中一个群集节点并安装 BizTalk Server。 选择选项以启动配置程序时安装已成功完成。  
  
6. 选择**自定义配置**选项并输入相应的值**数据库服务器名称**，**用户名**和**密码**字段。 输入这些值后，单击**配置**按钮以继续。  
  
7. 设置 SSO 功能的以下选项：  
  
   1.  选中的复选框旁边**启用企业单一登录此计算机上**。  
  
   2.  单击选项**加入现有 SSO 系统**。  
  
   3.  输入现有 SSO 数据库服务器名称和数据库名称的值。  
  
   4.  指定要使用企业单一登录服务的帐户时，请输入现有 SSO 服务帐户。  
  
8. 由于这是第一个 BizTalk Server 组中选择的选项**创建新的 BizTalk 组**配置 BizTalk 组组件时。  
  
9. 根据需要指定剩余的配置选项并将 BizTalk Server 配置应用到此节点。  
  
10. 已成功完成 BizTalk Server 配置后的第一个节点上，登录到第二个节点上并安装 BizTalk Server。 选择选项以启动配置程序时安装已成功完成。  
  
11. 选择**自定义配置**选项，然后再输入相应的值**数据库服务器名称**，**用户名**和**密码**字段。 输入这些值后，单击**配置**按钮以继续。  
  
12. 设置 SSO 功能的以下选项：  
  
    1.  选中的复选框旁边**启用企业单一登录此计算机上**。  
  
    2.  单击**加入现有 SSO 系统**。  
  
    3.  输入现有 SSO 数据库服务器名称和数据库名称的值。  
  
    4.  指定要使用企业单一登录服务的帐户时，请输入现有 SSO 服务帐户。  
  
13. 选择选项**加入现有 BizTalk 组**此群集节点上，配置 BizTalk 组组件时，指定第一个节点创建的 BizTalk 组。  
  
14. 根据需要指定剩余的配置选项并将 BizTalk Server 配置应用到此节点。  
  
15. 已成功完成 BizTalk Server 配置后，请执行以下步骤群集 SSO 服务：  
  
    1.  通过键入以下命令从命令停止每个群集节点上的 SSO 服务：  
  
        ```  
        net stop entsso  
        ```  
  
    2.  在故障转移群集管理中，将所有群集组都移到一个节点，并登录到此节点上。  
  
    3.  在左侧窗格中，单击以选择群集的服务或应用程序中包含的 IP 地址和网络名称资源。 此群集的服务或应用程序将包含群集的 SSO 服务和群集的 BizTalk 主机。  
  
        > [!NOTE]
        >  群集的 SSO 服务不会明确要求使用同一组中的群集物理磁盘资源。  
  
    4.  右键单击群集的服务或应用程序，指向**将资源添加**，然后单击**通用服务**以显示**新建资源向导**对话框。  
  
    5.  上**选择服务**页**新建资源向导**，选择**企业单一登录服务**，然后单击**下一步**。  
  
    6.  上**确认**页上，单击**下一步**。  
  
    7.  上**摘要**页上，单击**完成**。 企业单一登录服务的群集的实例将显示在下面**信息的其他资源**中的中心窗格**故障转移群集管理**接口。  
  
    8.  右键单击企业单一登录服务的群集的实例，然后选择**属性**以显示**企业单一登录服务属性**对话框。  
  
    9. 单击**依赖项**选项卡的属性对话框中，单击**插入**。  
  
    10. 单击下的下拉**资源**，选择**名称：** 资源，然后单击**确定**。  
  
        > [!IMPORTANT]
        >  如果不添加到依赖项**名称：** 资源，在尝试联系 SSO 服务的此群集的实例时，SSO 客户端计算机将生成类似于以下的错误：  
        >   
        >  检索主密钥失败。  
        >   
        >  验证主密钥服务器名称正确以及可用。 密钥服务器名称：ENTSSO 错误代码：0x800706D9，提供的终结点映射程序有没有更多的终结点。  
  
16. 按照中所述的步骤在 BizTalk Server 计算机上群集 IIS [Microsoft 知识库文章 970759"配置 IIS 7.0 中 Microsoft Windows Server 2008 故障转移群集"](http://go.microsoft.com/fwlink/p/?LinkId=152793) (<http://go.microsoft.com/fwlink/p/?LinkId=152793>)。 在与群集 SSO 服务相同的群集组中创建群集的 IIS web 服务。  
  
17. 在故障转移群集管理中，右键单击群集的服务或包含群集的企业单一登录服务的应用程序，然后单击**使此服务或应用程序联机**以启动所有中的资源群集的服务或应用程序。  
  
18. 右键单击群集的服务或应用程序，指向**将此服务或应用程序到另一个节点移动**，然后单击第二个节点。 此步骤将群集的服务或包含群集的企业单一登录服务从第一个节点到第二个节点的应用程序。  
  
19. 右键单击群集的企业单一登录服务，然后单击**使此服务或应用程序脱机**，然后右键单击 SSO 服务的群集的实例，并单击**使此服务或应用程序联机**。  
  
20. 将所有用户的 SSO 服务器名称设置为群集 SSO 服务使用 ssomanage 命令行实用工具。 此命令应在组中每个 BizTalk server 上运行的 SSO 安装文件夹。 例如，下面的命令行将设置为群集 SSO 服务的所有用户的 SSO 服务器名称：  
  
    ```  
    ssomanage -serverall SSOCLUSTER  
    ```  
  
    > [!NOTE]
    >  *SSOCLUSTER*是在包含群集的 SSO 服务的群集组中创建的实际网络名称资源的占位符。  
  
21. 更新可在中访问的 SSO 服务器名称**BizTalk 组属性**页后，可以引用群集的 SSO 服务。 打开**BizTalk Server 管理**，右键单击 BizTalk 组，选择**属性**菜单项，更新 SSO 服务器名称的条目，然后单击**确定**。  
  
22. 按照中的步骤[将 BizTalk 主机配置为群集资源](how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)在创建群集的 SSO 服务的同一群集组中创建一个或多个群集的 BizTalk 主机实例。  
  
    > [!NOTE]
    >  在此方案中，所有 BizTalk 主机都必须都创建为群集 SSO 服务资源所在的群集组中的群集资源。 其中群集 SSO 服务的 Windows Server 群集节点上运行非群集的 BizTalk 主机实例不是受支持的配置。 这是因为当群集的 SSO 服务故障转移到另一个节点上的 SSO 服务的 BizTalk 主机实例的依赖性时，非群集的 BizTalk 主机实例将失败。
