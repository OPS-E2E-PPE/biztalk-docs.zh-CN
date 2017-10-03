---
title: "使用基本或自定义配置进行配置 |Microsoft 文档"
description: "执行 BizTalk Server 中，基本或自定义配置和了解如何进行处理每个配置步骤"
ms.custom: 
ms.date: 08/14/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 861a1237-d77a-42db-b563-d83f7930add6
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8989fd322fd9fc34e947a80b510619446a65f71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-biztalk-server"></a>配置 BizTalk Server
使用“基本配置”或“自定义配置”配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。

## <a name="basic-configuration-vs-custom-configuration"></a>基本配置与自定义配置

* 如果配置使用域组，则进行“自定义配置”。
* 如果配置使用自定义组名称而不是默认组名称，则进行“自定义配置”。
* 如果配置使用自定义数据库名称而不是默认数据库名称，则进行“自定义配置”。
* 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 SQL Server 位于单独的计算机上，则需要使用域组。 因此，应进行“自定义配置”。
* 不能使用“基本配置”在 SQL Server 命名实例上配置 BAM 分析。 如果使用命名实例，并且希望配置 BAM 分析，则应进行“自定义配置”。
* 在用户设置运行于一台服务器上的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 SQL Server 的完整安装时，建议使用“基本配置”选项。
* “基本配置”速度更快，因为它会自动使用默认名称来创建本地组和数据库。


## <a name="before-you-begin"></a>开始之前
* 可以使用 SQL Server 默认实例和命名实例来配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 
* 登录所用的帐户必须是本地管理员组的成员，并拥有对 SQL Server 的系统管理员权限 (SA)。
* 如果使用域组，则在配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之前这些域组必须存在。
* [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置中列出的由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成的默认帐户是本地组。 在多服务器环境中，必须用域组替换本地组。
* 如果配置 BAM Analysis Services，登录时所用的帐户必须为 OLAP 计算机中的 OLAP 管理员组的成员。


## <a name="basic-configuration"></a>基本配置

1. 在“开始”菜单中，右击选择“BizTalk Server 配置”，然后选择“以管理员身份运行”。 将打开“配置向导”。 
2. 选择以下选项： 
    1. 选择“基本配置”。
    2. **数据库服务器名称**将自动默认为本地计算机名称。   
    3. 输入运行 BizTalk 服务时所用的帐户的“用户名”和“密码”。 最佳做法是创建一个唯一帐户。 不要使用个人用户名。  
        ![bts2016BasicConfig](../install-and-config-guides/media/bts2016basicconfig.gif)  
    如果输入的用户名具有此计算机的管理凭据，将收到一条警告。 这是正常现象。 选择“确定”继续。
    
3. 选择“配置”。
4. 查看配置详细信息，然后选择“下一步” 。
5. 配置向导完成后，选择“完成”。

会在一个 temp 文件夹中生成一个配置日志文件，如下所示：`
C:\Users\username\AppData\Local\Temp\ConfigLog(01-12-2017 0h37m59s).log`。

在使用基本配置选项时，将发生以下情况：

- 所有数据库名称都将由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 自动生成。
- 所有适用数据库的登录信息都将在输入的帐户下运行。 
- 所有 BizTalk 服务都将由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 自动生成。
- 所有 BizTalk 服务都在输入的帐户下运行。 配置过程将授予此帐户对该服务器以及 SQL Server 中对象的必需安全权限。
- 所有功能的配置均基于该计算机上安装的必备软件。
- 将自动使用默认组名在计算机上创建本地组。
- Internet 信息服务 (IIS) 中的默认网站将用于需要 IIS 的所有功能。

## <a name="custom-configuration"></a>自定义配置
  
1. 在“开始”菜单中，右击选择“BizTalk Server 配置”，然后选择“以管理员身份运行”。 将打开“配置向导”。
2. 选择“自定义配置”，然后选择“配置”。

### <a name="configure-enterprise-single-sign-on-sso"></a>配置企业单一登录 (SSO)

* 配置完 SSO 后，不能使用“BizTalk Server 配置”对其重新进行配置。 若要重新配置 SSO，可使用“BizTalk Server 管理”。
* 使用本地帐户配置 SSO Windows 帐户时，仅输入帐户名。 请勿输入计算机名称。
* 若要使用本地 SQL Server 命名实例作为数据存储，请使用 `LocalMachineName\InstanceName`。 请勿使用 `LocalMachineName\InstanceName, PortNumber`。 

1. 选择“企业 SSO”。
2. 配置下列内容：

    | 使用此项 | 执行的操作 |
    | --- | --- |
    |在此计算机上启用企业单一登录 | 使用 SSO 设置配置此服务器。 |
    |新建 SSO 系统 | 如果这是配置的第一个 SSO 服务器，则选择此选项。 这将创建和配置 SSO 数据库、创建主密钥（加密的安全密钥），并安装 SSO 所用的服务。 此外，您还必须备份此密钥服务器上的密钥。<br/><br/>密钥详细信息： <br/><ul><li>建议将主密钥服务器配置为独立服务器。</li><li>只有 SSO 管理员才能执行此配置任务。</li><li>只能将一个主密钥服务器与一个 BizTalk 组相关联。 不支持将两个主密钥服务器与同一个 BizTalk 组相关联。</li></ul>|
    |加入现有 SSO 系统 | 如果向现有组添加 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则选择此选项。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与组中的其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 共享同一 SSO 配置和数据库。 |
    |数据存储 | 输入 SSO 服务器的服务器名称。 如果位于 SSO 服务器上，则选择本地服务器名称。 可以将 **SSODB** 保留为默认数据库名称，或输入自定义名。|
    |Windows 服务| 输入用于运行企业单一登录服务的帐户。 如果 SQL Server 位于另一台计算机，则输入域帐户。 |
    |Windows 帐户|可以保留默认组名或输入自定义名。 如果 SQL Server 位于另一台计算机，则输入域帐户。 |

3. 选择“企业 SSO 密钥备份”。 此选项可将主密钥保存到加密的备份文件。 
4. 配置下列内容：  

    |使用此项|执行的操作|
    | --- | --- |
    |密钥备份密码 | 输入主密钥密码。|
    |确认密码|再次输入主密钥密码。|
    |密码提示|为输入的密码键入提示。 重要 - 不跳过此步骤。 |
    |备份文件位置|列出备份文件名称和位置。 默认情况下，该文件存储位置为：\Program Files\Common Files\Enterprise Single Sign-On\ FileName.bak。|

**始终**备份主密钥，并与另一个 BizTalk 管理员共享密码。
    
### <a name="configure-groups"></a>配置组

* 若要使用本地 SQL Server 命名实例作为数据存储，请使用 `LocalMachineName\InstanceName`。 请勿使用 `LocalMachineName\InstanceName, PortNumber`。

1. 选择“组”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    |在此计算机上启用 BizTalk Server 组|选择此选项可在此服务器上新建 BizTalk 组或加入现有组。 |
    |新建 BizTalk 组| 如果这是组中的第一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则选择此选项。 使用此选项可以创建数据库，并添加组。|
    |加入现有 BizTalk 组| 如果将此 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 加入现有组，则选择此选项。|
    |为跟踪聚合创建分析数据库|若要安装 SQL Server Analysis Services，并且想要跟踪和存储运行状况监视 OLAP 多维数据集，则选择此选项。|
    |数据存储| 输入承载 BizTalk 数据库的服务器名称。 如果此服务器同时安装了 BizTalk 和 SQL，则输入本地服务器名称。 如果 SQL Server 位于另一台计算机，则输入 SQL Server 名称。<br/><br/>可以保留默认数据库名称或输入自定义内容。|
    |BizTalk 管理角色|可以保留默认组名或输入自定义名。 如果 SQL Server 位于另一台计算机，则输入域帐户。|

### <a name="configure-the-biztalk-runtime"></a>配置 BizTalk 运行时

* 配置完运行时后，不能使用“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置”对其重新进行配置。 若要重新配置运行时，请使用“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理”。
* 在组中创建的第一台主机必须是进程内主机和主机实例。
* 在同一组中的多个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上配置运行时时，不能为受信任的和不受信任的主机应用程序使用同一服务帐户。 必须分别为受信任的应用程序和不受信任的应用程序使用一个唯一帐户。 

1. 选择“BizTalk 运行时”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    | 注册 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时组件 | 选择此选项可在此 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上创建主机和主机实例。 |
    | 创建进程内主机和实例 | 在此计算机上创建 BizTalkServerApplication 主机和实例。<br/><br/>其他选项： <ul><li>**受信任**：提交消息时将发件人的凭据（SSID 和/或参与方 ID）传递到 MessageBox 数据库。 这相当于在服务器之间创建信任关系。 大多数主机和实例不受信任。</li><li>**仅限 32 位**：某些适配器仅在 32 位进程中运行，但大多数都可兼容 64 位进程。 配置 BizTalk 后，可在“BizTalk 管理”中启用/禁用此设置。 因此，无需强调。</li><li>**主机名**BizTalkServerApplication 是默认值。 如果在“BizTalk 管理”中新建主机和实例，可以是特定于名称的，如 TrackingHost 或 ReceivingHost。 因此，将其保留原样。</li></ul>|
    | 创建独立主机和实例| 独立主机在 IIS 中运行。 在许多环境中，最好保留默认值。<br/><br/>其他选项： <ul><li>**受信任**：提交消息时将发件人的凭据（SSID 和/或参与方 ID）传递到 MessageBox 数据库。 这相当于在服务器之间创建信任关系。 大多数主机和实例不受信任。</li><li>**仅限 32 位**：某些适配器仅在 32 位进程中运行，但大多数都可兼容 64 位进程。 配置 BizTalk 后，可在“BizTalk 管理”中启用/禁用此设置。</li><li>**独立主机名**：BizTalkServerIsolatedHost 是默认值。 保留原样。 </li></ul>|
    |Windows 服务| 输入用于运行主机实例的帐户。 如果 SQL Server 位于另一台计算机，则输入域帐户。 |
    |Windows 组|可以保留默认组名或输入自定义名。 如果 SQL Server 位于另一台计算机，则输入域帐户。 |


### <a name="configure-business-rules-engine-bre"></a>配置业务规则引擎 (BRE)

如果不使用 BRE，则跳过本部分。

- 建议在配置业务规则引擎之前配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组。 如果在配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组之前先配置 BRE，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置不会将与组相关的管理角色添加到规则引擎数据库中。

1. 选择“业务规则引擎”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    |在此计算机上启用业务规则引擎 | 如果在此 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上使用 BRE，则选择此选项。 |
    |数据存储| 输入承载“规则”数据库的服务器名称。 如果此服务器同时安装了 BizTalk 和 SQL，则输入本地服务器名称。 如果 SQL Server 位于另一台计算机，则输入 SQL Server 名称。<br/><br/>可以保留默认数据库名称或输入自定义名。|
    |Windows 服务| 输入用于运行规则更新服务的帐户。 如果 SQL Server 位于另一台计算机，则输入域帐户。 |


### <a name="configure-bam-tools"></a>配置 BAM 工具

如果不使用 BAM 工具，则跳过本部分。

业务活动监视工具包括：

- 用于 Excel 的 BAM 加载项
- BAM 管理器
- BAM 门户


- 配置 BAM 工具需要某些 SQL Server 管理功能，并且必须从已安装 Integration Services 的计算机执行该操作。
- BAM 工具可能由多个 BizTalk 组使用。 取消配置 BAM 工具时，会删除与该 BizTalk 组的连接。 但是，BAM SQL Server 基础结构将继续对其他指向 BAM 主导入表的 BizTalk 组发挥作用。
- 使用“业务活动监视工具”页，可快速重新配置 BAM 数据库。 例如，再次配置 BAM 数据库而无需删除现有配置。 重新配置这些 BAM 数据库将中断所有已部署的 OLAP 视图以及所有警报。 如果希望将某些现有视图和警报存于新配置的数据库中，请执行以下操作之一：  
    - 在重新配置前，取消部署这些警报和视图，然后在重新配置后，对其进行重新部署。 这些视图中不显示任何已存档的数据。
    - 如果不使用 BAM 警报，则应在重新配置前备份数据库。 在重新配置后，将该数据库还原到新配置的位置。
- 如果合并 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库，应排除 BAM 存档和 BAM Analysis 数据库。


1. 选择“BAM 工具”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    |启用业务活动监视工具 | 在此计算机上启用并安装 BAM 工具。 |
    | 为 BAM 聚合启用 Analysis Services | 提供 BAM 警报的跟踪信息。|
    |数据存储| 输入承载 BAM 数据库的服务器名称。 如果此服务器同时安装了 BizTalk 和 SQL，则输入本地服务器名称。 如果 SQL Server 位于另一台计算机，则输入 SQL Server 名称。<br/><br/>可以保留默认数据库名称或输入自定义名。|
    |删除此 BizTalk 组的业务活动/监视工具 | 从 BizTalk 组中卸载并删除 BAM 工具。 |
    
 ### <a name="configure-bam-alerts"></a>配置 BAM 警报 

BAM 警报需要启用 BAM 工具。

1. 选择“BAM 警报”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    | 启用 BAM 警报 | 如果使用 BAM 警报，则勾选此选项。 <br/><br/>请记住，必须已配置 SQL Database Mail 才能使用 BAM 警报。 |
    | Windows 服务 | 输入用于运行 BAM 警报服务的帐户。 如果 SQL Server 位于另一台计算机，则输入域帐户。 |
    | BAM 警报 SMTP 服务器| 输入与 SQL Database Mail 一起配置的 SMTP 服务器名称。 |
    | BAM 警报文件位置| 输入网络共享，以存储 BAM 警报。 <br/><br/>**注意** <br/>您必须先手动创建此共享位置，BAM 警报才能存储这些文件。|
    | 警报数据库的 SQL Server | 输入承载 Alerts 数据库的 SQL Server 名称。<br/><br/>**注意** <br/>不支持使用 IPv6 地址来指定警报数据库的 NS SQL Server。 但是，您可以使用计算机名称，这样，DNS 转换将会进行查找。|
    |警报数据库名称的前缀| 输入用于 Alerts 数据库的前缀。|  

### <a name="configure-the-bam-portal"></a>配置 BAM 门户

1. 选择“BAM 门户”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    |启用 BAM 门户 | 如果使用 BAM 门户，则加粗此选项。 | 
    |Web Services 帐户 | 输入用于运行 IIS 服务的帐户。 如果 SQL Server 位于另一台计算机，则输入域帐户。|
    |Windows 组 | 可以保留默认组名或输入自定义内容。 如果 SQL Server 位于另一台计算机，则输入域帐户。|
    |BAM 门户网站|选择网站，以承载 BAM 门户。 在某些环境中，默认网站是配置的唯一网站。 |

### <a name="configure-biztalk-edias2-runtime"></a>配置 BizTalk EDI/AS2 运行时 

* 必须先配置企业 SSO、组和 BizTalk 运行时，才能配置 BizTalk EDI/AS2 运行时。 
* 必须先配置 BAM 工具，才能配置 EDI/AS2 运行时状态报告功能。
* 如果您只配置 EDI，那么将不需要 BAM。

1. 选择“BizTalk EDI/AS2 运行时”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    |在此计算机上启用 BizTalk EDI/AS2 运行时| 如果要将 X12、EDIFACT 或 AS2 协议用于企业到企业消息传递，则选择此选项。 |
    |为此 BizTalk 组启用 BizTalk EDI | 如果使用 X12 或 EDIFACT，则选择此选项。 |
    | 为此 BizTalk 组启用 BizTalk AS2 | 如果使用 AS2，则选择此选项。 |
    | 为此 BizTalk 组启用 BizTalk EDI/AS2 运行时状态报告 | 启用报告用户体验，以提供 EDI 交换和确认状态。 |
    |从此 BizTalk 组中删除 BizTalk EDI、AS2 和状态报告功能。 | 从组中卸载并删除报表功能。 |

### <a name="configure-windows-sharepoint-services-web-service---biztalk-server-2013-and-r2-only"></a>配置 Windows SharePoint Services Web 服务 - 仅限 BizTalk Server 2013 和 R2 

> [!IMPORTANT] 
> 本部分仅适用于 BizTalk Server 2013 R2 和 BizTalk Server 2013。 如果不使用 BizTalk Server 2013 R2 或 BizTalk Server 2013，则跳过此部分。

* 从 BizTalk Server 2016 开始，已删除此 SharePoint Services Web 服务 (SSOM)，不推荐在 BizTalk Server 2013 R2 中使用。 它将替换为 SharePoint Services 适配器 (CSOM)。 BizTalk 配置中不显示 CSOM 选项。 CSOM 选项会随 BizTalk 自动安装，就像文件适配器或 HTTP 适配器自动安装的方式一样。

1. 选择“Windows SharePoint Services 适配器”。
2. 配置下列内容：

    |使用此项|执行的操作|
    | --- | --- |
    | 在此计算机上启用 Windows SharePoint Services 适配器 | 选择以安装 SharePoint Services Web 服务。 IIS Web Services 安装在 SharePoint Services 计算机上，既可以和 BizTalk Server 在同一计算机上，也可以在单独的计算机上。 在大多数环境中，BizTalk Server 和 SharePoint Services 都位于单独的计算机上。|
    |Windows 组|可以保留默认组名或输入自定义内容。 |
    |Windows SharePoint Services 适配器网站|选择承载 Windows SharePoint Services 适配器 Web 服务的网站。|
    
    
### <a name="apply-your-configuration"></a>应用配置

选择“应用配置”，然后继续进行该配置。 

1. 在“摘要”中查看所选组件，并单击“下一步”。
2. 完成时，选择“完成”。

配置完成后，会在一个 temp 文件夹中生成一个配置日志文件，如下所示：`
C:\Users\username\AppData\Local\Temp\ConfigLog(1-12-2017 2h39m30s).log`。

## <a name="iis-application-pools-and-web-sites"></a>IIS 应用程序池和网站
在配置之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可能会创建以下 Internet 信息服务 (IIS) 应用程序池和虚拟应用程序： 
  
### <a name="application-pools"></a>应用程序池  
  
|应用程序池|默认应用程序池标识|Description|  
|----------------------|---------------------------------------|-----------------|  
|BAMAppPool|*用户定义*|BAM 门户的应用程序池。|  
|BTSSharePointAdapterWSAppPool|*用户定义*|Windows SharePoint Services 适配器 Web Services 的应用程序池。|  
|STSWebServiceAppPool|*用户定义*|贸易合作伙伴管理工具的应用程序池。|  
|TpmWSAppPool|*用户定义*|TPM 管理 Web Services 的应用程序池。|  
  
### <a name="virtual-applications"></a>虚拟应用程序  
  
|虚拟应用程序|默认应用程序池|Description|  
|-------------------------|------------------------------|-----------------|  
|BAM|BAMAppPool|BAM 门户组件（页面、图像、预编译的代码和其他资源）的宿主虚拟应用程序。 此虚拟应用程序调用 BAMManagementService 应用程序，以与 BAM 数据库进行通信。 **注意：**要设置外观 BAM 门户，你可以修改此应用程序的内容。|  
|BAMManagementService|BAMAppPool|BAMManagementService Web Services 的宿主虚拟应用程序。 BAM 门户应用程序可使用此 Web Services 与 BAM 主导入表 (PIT) 进行通信。 使用配置期间创建的注册表中存储的模拟凭据可以完成与数据库的通信。 自定义客户端可以使用由 Web Services 公开的这个方法以获取任何用户的视图及其详细信息、相关活动和数据透视表布局。 还可以将其用于管理数据库中的警报。|  
|BTSharePointAdapterWS|BTSSharePointAdapterWSAppPool|Windows SharePoint Services 适配器 Web Services 的宿主虚拟应用程序。 适用于 BizTalk Server 2013 R2 和仅 2013年。|  

 
## <a name="more-configuration-topics"></a>更多配置主题  
  
 [在 Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
[在群集中配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

 [确保 BizTalk Server 部署的安全](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
  
 