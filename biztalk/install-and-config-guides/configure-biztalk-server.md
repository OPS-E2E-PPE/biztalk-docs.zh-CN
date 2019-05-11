---
title: 使用基本或自定义配置进行配置 |Microsoft Docs
description: 若要进行 BizTalk Server 的基本或自定义配置并学习与每个配置会发生什么情况的步骤
ms.custom: ''
ms.date: 08/23/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 861a1237-d77a-42db-b563-d83f7930add6
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eba49561488669d3e14d8f3a9afb8a3fc0320ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400025"
---
# <a name="configure-biztalk-server"></a>配置 BizTalk Server
配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用基本配置或自定义配置。

## <a name="basic-configuration-vs-custom-configuration"></a>基本配置与。自定义配置

* 如果你的配置使用域组，请执行自定义配置。
* 如果你的配置使用自定义组名称而不是默认组名称，请执行自定义配置。
* 如果你的配置使用自定义数据库名称而不是默认数据库名称，请执行自定义配置。
* 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SQL Server 在不同计算机上，则需要使用域组。 因此，执行自定义配置。
* 不能在 SQL Server 命名实例使用基本配置来配置 BAM 分析。 如果使用命名的实例，并且希望配置 BAM 分析，进行自定义配置。
* 建议使用基本配置是用户设置的完整安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和一台服务器上运行的 SQL Server。
* 基本配置速度更快，因为它会自动创建本地组和数据库使用的默认名称。


## <a name="before-you-begin"></a>开始之前
* [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以使用 SQL Server 默认实例和命名实例配置。 
* 你被登录帐户必须是本地管理员组的成员，并且 SQL Server 上具有系统管理员 (SA) 权限。
* 如果使用域组，域组必须存在*之前*配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。
* 通过生成的默认帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在中并列出[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置是本地组。 在多服务器环境中，用域组替换本地组。
* 如果配置 BAM Analysis Services，然后你将登录帐户必须为 OLAP 计算机上的 OLAP Administrators 组的成员。
* 安装累积更新 (Cu) 或功能包 (FPs)*后*配置 BizTalk Server。 自定义或每秒帧数中包含某些更新仅限目标配置的项目。 如果安装 Cu 或每秒帧数，在运行配置之前，重新安装的自定义和每秒帧数，在配置之后。 这可确保完成修补和升级所有组件。

## <a name="basic-configuration"></a>基本配置

1. 在开始菜单中，右击选择**BizTalk Server 配置**，然后选择**以管理员身份运行**。 这将打开配置向导。 
2. 选择以下选项： 
    1. 选择**基本配置**。
    2. **数据库服务器名称**自动默认为本地计算机的名称。   
    3. 输入**用户名**并**密码**BizTalk services 将运行方式帐户。 最佳做法是创建一个唯一的帐户。 不要使用个人用户名。  
        ![bts2016BasicConfig](../install-and-config-guides/media/bts2016basicconfig.gif)  
    如果此计算机上输入的用户名具有管理凭据，您将收到一条警告。 这是正常的。 选择**确定**以继续。

3. 选择 **“配置”**。
4. 查看你配置的详细信息，然后选择**下一步**。
5. 配置向导完成后，选择**完成**。

配置日志文件生成于临时文件夹，类似于： `
C:\Users\username\AppData\Local\Temp\ConfigLog(01-12-2017 0h37m59s).log`。

在执行操作时基本配置中，将发生以下情况：

- 自动生成的所有数据库名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。
- 您输入的帐户下运行所有适用数据库的登录信息。 
- 所有 BizTalk 服务会自动都生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。
- 您输入的帐户下运行所有 BizTalk 服务。 配置过程将授予此帐户上的服务器和 SQL Server 中的对象的必需的安全权限。
- 所有功能的都配置均基于在计算机上安装的必备软件。
- 将自动创建使用默认组名称的计算机的本地组。
- 默认网站在 Internet 信息服务 (IIS) 用于需要 IIS 的任何功能。

## <a name="custom-configuration"></a>自定义配置

1. 在开始菜单中，右击选择**BizTalk Server 配置**，然后选择**以管理员身份运行**。 这将打开配置向导。
2. 选择**自定义配置**，然后选择**配置**。

### <a name="configure-enterprise-single-sign-on-sso"></a>配置企业单一登录 (SSO)

* 配置 SSO，则不能重新配置使用 BizTalk Server 配置。 若要重新配置 SSO，请使用 BizTalk Server 管理。
* 配置使用本地帐户 SSO Windows 帐户时，仅输入帐户名称。 请勿输入计算机名称。
* 在使用本地 SQL Server 命名实例用作数据存储区，使用`LocalMachineName\InstanceName`。 不要使用`LocalMachineName\InstanceName, PortNumber`。 

1. 选择**企业 SSO**。
2. 下列配置：


   | 使用此选项 |  执行的操作|
   |---|---|
   | 在此计算机上启用企业单一登录 | 使用 SSO 设置配置此服务器。  |
   |  创建新的 SSO 系统  | 如果这是要配置的第一个 SSO 服务器，则选择此选项。 这将创建和配置 SSO 数据库，创建主密钥 （加密的安全密钥），并安装 SSO 所用的服务。 您还必须在此服务器上备份密钥。<br/><br/>关键详细信息： <br/><ul><li>建议将主密钥服务器配置为独立服务器。</li><li>执行此配置任务时，您必须是 SSO 管理员。</li><li>只有一个主密钥服务器可以与一个 BizTalk 组相关联。 不支持将两个主密钥服务器与同一个 BizTalk 组相关联。</li></ul> |
   | 加入现有 SSO 系统 | 如果要添加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到现有组，则选择此选项。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与其他共享同一 SSO 配置和数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  |
   |  数据存储  |   输入 SSO 服务器的服务器名称。 如果你位于 SSO 服务器，然后选择本地服务器名称。 可以保留**SSODB**作为默认数据库名称，或输入自定义内容。  |
   |   Windows 服务  |  输入用于运行企业单一登录服务的帐户。 如果 SQL Server 位于另一台计算机上，输入域帐户。   |
   |  Windows 帐户  | 可以保留默认设置组名称，或输入自定义内容。 如果 SQL Server 位于另一台计算机上，输入域帐户。  |


3. 选择**企业 SSO 密钥备份**。 此选项可将主密钥保存到加密的备份文件。 
4. 下列配置：  

    |使用此选项|执行的操作|
    | --- | --- |
    |密钥备份密码 | 输入主密钥密码。|
    |确认密码|重新输入主密钥密码。|
    |密码提示|键入您输入的密码提示。 重要-不跳过此步骤。 |
    |备份文件位置|列出备份文件名称和位置。 默认情况下，此文件存储在 \Program Files\Common Files\Enterprise Single sign-on\*文件名*.bak。|

**始终**备份主密钥，并使用另一个 BizTalk 管理员共享密码。

### <a name="configure-groups"></a>配置组

* 在使用本地 SQL Server 命名实例用作数据存储区，使用`LocalMachineName\InstanceName`。 不要使用`LocalMachineName\InstanceName, PortNumber`。

1. 选择**组**。
2. 下列配置：


   |  使用此选项 | 执行的操作 |
   |---|---|
   |  在此计算机上启用 BizTalk Server 组  | 选择此选项可在此服务器上创建新的 BizTalk 组或加入现有组。 |
   |  创建新的 BizTalk 组 | 如果这是第一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的组中，则选择此选项。 使用此选项可创建数据库，并添加的组。 |
   | 加入现有 BizTalk 组 |   如果您要加入此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到现有组，请选择此选项。  |
   | 创建用于跟踪聚合的分析数据库 | 选择此选项以安装 SQL Server Analysis Services，并且你想要跟踪和存储运行状况监视 OLAP 多维数据集。  |
   | 数据存储 | 输入承载 BizTalk 数据库的服务器名称。 如果此服务器具有 BizTalk 和 SQL 同时安装了，则输入本地服务器名称。 如果 SQL Server 位于另一台计算机上，输入 SQL Server 名称。<br/><br/>可以保留默认数据库名称，或输入自定义内容。 |
   |   BizTalk 管理角色 |  可以保留默认设置组名称，或输入自定义内容。 如果 SQL Server 位于另一台计算机上，输入域帐户。   |

### <a name="configure-the-biztalk-runtime"></a>配置 BizTalk 运行时

* 在运行时配置后，则不能重新配置使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。 若要重新配置运行时，使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理。
* 在组中创建的第一个主机必须是进程内主机和主机实例。
* 当在多个配置运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的同一组中，相同的服务帐户不能使用受信任和不受信任的主机应用程序。 为受信任的应用程序，和不受信任的应用程序，必须使用唯一的帐户。 

1. 选择**BizTalk 运行时**。
2. 下列配置：


   |   使用此选项 | 执行的操作  |
   |---|---|
   | 注册[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时组件 |  选择此选项可对此创建主机和主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  |
   |  创建进程内主机和实例  | 在此计算机上创建 BizTalkServerApplication 主机和实例。<br/><br/>其他选项： <ul><li>**受信任的**:提交到 MessageBox 数据库的消息时，将凭据 （SSID 和/或参与方 ID） 传递发件人。 这相当于创建的服务器之间的信任关系。 大多数主机和实例不受信任。</li><li>**仅限 32 位**:某些适配器仅在 32 位进程中运行，但大多数都是 64 位兼容。 此设置可以启用/禁用在 BizTalk 管理在配置 BizTalk 后。 因此，无需强调。</li><li>**主机名**:默认值为 BizTalkServerApplication。 必要时在 BizTalk 管理中创建新的主机和实例，您还可以只使用你的名称，如 TrackingHost 或 ReceivingHost。 因此，保留原样-是。</li></ul> |
   |  创建独立主机和实例  |  独立主机在 IIS 中运行。 在许多环境中，最好保留默认值。<br/><br/>其他选项： <ul><li>**受信任的**:提交到 MessageBox 数据库的消息时，将凭据 （SSID 和/或参与方 ID） 传递发件人。 这相当于创建的服务器之间的信任关系。 大多数主机和实例不受信任。</li><li>**仅限 32 位**:某些适配器仅在 32 位进程中运行，但大多数都是 64 位兼容。 此设置可以启用/禁用在 BizTalk 管理在配置 BizTalk 后。</li><li>**独立主机的名**:BizTalkServerIsolatedHost 是默认值。 保留原样-是。 </li></ul> |
   |   Windows 服务   |  输入用于运行主机实例的帐户。 如果 SQL Server 位于另一台计算机上，输入域帐户。  |
   |   Windows 组  |  可以保留默认设置组名称，或输入自定义内容。 如果 SQL Server 位于另一台计算机上，输入域帐户。  |

### <a name="configure-business-rules-engine-bre"></a>配置业务规则引擎 (BRE)

如果不使用 BRE，则跳过此部分。

- 我们建议你将配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组之前配置业务规则引擎。 如果在配置之前配置 BRE[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置不会添加到规则引擎数据库与组相关的管理角色。

1. 选择**业务规则引擎**。
2. 下列配置：


   |  使用此选项 | 执行的操作  |
   |---|---|
   | 此计算机上启用业务规则引擎 | 如果您使用 BRE [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则选择此选项。  |
   |  数据存储  | 输入承载您规则的数据库的服务器名称。 如果此服务器具有 BizTalk 和 SQL 同时安装了，则输入本地服务器名称。 如果 SQL Server 位于另一台计算机上，输入 SQL Server 名称。<br/><br/>可以保留默认数据库名称，或输入自定义内容。 |
   |   Windows 服务  |  输入用于运行规则更新服务的帐户。 如果 SQL Server 位于另一台计算机上，输入域帐户。  |

### <a name="configure-bam-tools"></a>配置 BAM 工具

如果不使用 BAM 工具，则跳过此部分。

业务活动监视工具包括：

- BAM 外接程序 excel
- BAM 管理器
- BAM 门户


- 配置 BAM 工具需要某些 SQL Server 管理功能，并且必须从安装了 Integration Services 的计算机执行。
- BAM 工具可能会使用多个 BizTalk 组。 取消配置 BAM 工具，将与 BizTalk 组的连接。 但是，BAM SQL Server 基础结构将继续适用于其他 BizTalk 组，指向 BAM 主导入表。
- 使用业务活动监视工具页来重新配置 BAM 数据库上的动态。 例如，BAM 数据库重新配置而无需删除现有配置。 重新配置这些 BAM 数据库将中断任何已部署的 OLAP 视图以及所有警报。 如果有现有的视图和你想要使新配置数据库中保持的警报，然后执行下列任一操作：  
    - 重新配置前，取消部署这些警报和视图，然后将其重新配置后重新部署。 任何已存档的数据不存在的视图中。
    - 如果不使用 BAM 警报，然后备份数据库之前，你重新配置。 重新配置后，将数据库还原到新配置的位置中。
- 如果您在合并[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，应排除 BAM 存档和 BAM 分析数据库。


1. 选择**BAM 工具**。
2. 下列配置：

    |使用此选项|执行的操作|
    | --- | --- |
    |启用业务活动监视工具 | 启用并在此计算机上安装 BAM 工具。 |
    | 为 BAM 聚合启用 Analysis Services | 提供 BAM 警报的跟踪的信息。|
    |数据存储| 输入承载 BAM 数据库的服务器名称。 如果此服务器具有 BizTalk 和 SQL 同时安装了，则输入本地服务器名称。 如果 SQL Server 位于另一台计算机上，输入 SQL Server 名称。<br/><br/>可以保留默认数据库名称，或输入自定义内容。|
    |为此 BizTalk 组中删除业务活动/监视工具 | 卸载并从 BizTalk 组中删除 BAM 工具。 |

   ### <a name="configure-bam-alerts"></a>配置 BAM 警报 

BAM 警报需要 BAM 工具才可用。

1. 选择**BAM 警报**。
2. 下列配置：

    |使用此选项|执行的操作|
    | --- | --- |
    | 启用 BAM 警报 | 如果您使用 BAM 警报，然后选中此选项。 <br/><br/>请记住，您必须已配置 SQL Database Mail 才能使用 BAM 警报。 |
    | Windows 服务 | 输入用于运行 BAM 警报服务的帐户。 如果 SQL Server 位于另一台计算机上，输入域帐户。 |
    | BAM 警报 SMTP 服务器| 输入与 SQL 数据库邮件配置的 SMTP 服务器名称。 |
    | BAM 警报文件位置| 输入用于存储 BAM 警报的网络共享。 <br/><br/>**注意** <br/>BAM 警报才能存储这些文件之前，必须手动创建此共享。|
    | 警报数据库的 SQL Server | 输入承载 Alerts 数据库的 SQL Server 名称。<br/><br/>**注意** <br/>不支持使用 IPv6 地址来指定警报数据库的 NS SQL Server。 但是，可以使用计算机名称和 DNS 转换将会进行查找。|
    |警报数据库名称的前缀| 输入用于警报数据库的前缀。|  

### <a name="configure-the-bam-portal"></a>配置 BAM 门户

1. 选择**BAM 门户**。
2. 下列配置：

    |使用此选项|执行的操作|
    | --- | --- |
    |启用 BAM 门户 | 如果您使用 BAM 门户，则加粗此选项。 | 
    |Web 服务帐户 | 输入用于运行 IIS 服务的帐户。 如果 SQL Server 位于另一台计算机上，输入域帐户。|
    |Windows 组 | 可以保留默认组名称，或输入自定义内容。 如果 SQL Server 位于另一台计算机上，输入域帐户。|
    |BAM 门户网站|选择要承载 BAM 门户的 Web 站点。 在某些环境中，默认网站是配置的唯一网站。 |

### <a name="configure-biztalk-edias2-runtime"></a>配置 BizTalk edi/as2 运行时 

* 在配置 BizTalk EDI/AS2 运行时之前，必须配置企业 SSO、 组和 BizTalk 运行时。 
* 配置 EDI/AS2 运行时状态报告功能前，必须启用 BAM 工具。
* 如果只配置 EDI，则不需要 BAM。

1. 选择**BizTalk EDI/AS2 运行时**。
2. 下列配置：

    |使用此选项|执行的操作|
    | --- | --- |
    |此计算机上启用 BizTalk EDI/AS2 运行时| 如果您将使用 x12、edifact 或 AS2 协议用于企业到企业消息传递，则选择此选项。 |
    |为此 BizTalk 组启用 BizTalk EDI | 如果使用 X12 或 EDIFACT，请选择此选项。 |
    | 为此 BizTalk 组启用 BizTalk AS2 | 如果使用 AS2，请选择此选项。 |
    | 为此 BizTalk 组启用 BizTalk EDI/AS2 运行时状态报告 | 启用报表的用户体验，以提供 EDI 交换和确认的状态。 |
    |从此 BizTalk 组中删除 BizTalk edi、as2 和状态报告功能 | 卸载并从组中删除的报告功能。 |

### <a name="configure-windows-sharepoint-services-web-service---biztalk-server-2013-and-r2-only"></a>配置 Windows SharePoint Services web 服务的 BizTalk Server 2013 并仅限 R2 

> [!IMPORTANT] 
> 本部分仅适用于 BizTalk Server 2013 R2 和 BizTalk Server 2013。 如果您不使用 BizTalk Server 2013 R2 或 BizTalk Server 2013，则跳过此部分。

* 此 SharePoint Services web 服务 (SSOM) 已从 BizTalk Server 2016 和 BizTalk Server 2013 R2 中已弃用。 它是替换为与 SharePoint Services 适配器 (CSOM)。 CSOM 选项不显示在 BizTalk 配置。 CSOM 选项会自动随 BizTalk 中，就像文件适配器或 HTTP 适配器自动安装。

1. 选择**Windows SharePoint Services 适配器**。
2. 下列配置：

    |使用此选项|执行的操作|
    | --- | --- |
    | 此计算机上启用 Windows SharePoint Services 适配器 | 选择此选项可以安装 SharePoint Services web 服务。 可以在 BizTalk Server 所在的计算机或单独的计算机在 SharePoint Services 计算机上安装 IIS web 服务。 在大多数环境中，BizTalk Server SharePoint Services 在不同计算机上。|
    |Windows 组|可以保留默认组名称，或输入自定义内容。 |
    |Windows SharePoint Services 适配器网站|选择承载 Windows SharePoint Service 适配器 web 服务的 Web 站点。|


### <a name="apply-your-configuration"></a>应用配置

选择**应用配置**，并继续进行配置。 

1. 在中**摘要**，查看的组件选择，然后选择**下一步**。
2. 完成后，选择**完成**。

完成后，配置日志文件生成于临时文件夹，类似于： `
C:\Users\username\AppData\Local\Temp\ConfigLog(1-12-2017 2h39m30s).log`。

## <a name="iis-application-pools-and-web-sites"></a>IIS 应用程序池和网站
在配置之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以创建以下 Internet 信息服务 (IIS) 应用程序池和虚拟应用程序： 

### <a name="application-pools"></a>应用程序池  

|应用程序池|默认应用程序池标识|Description|  
|---|----|---|  
|BAMAppPool|*用户定义*|BAM 门户的应用程序池。|  
|BTSSharePointAdapterWSAppPool|*用户定义*|Windows SharePoint Service 适配器 Web 服务的应用程序池。|  
|STSWebServiceAppPool|*用户定义*|贸易合作伙伴管理工具的应用程序池。|  
|TpmWSAppPool|*用户定义*|TPM 管理 Web 服务的应用程序池。|  

### <a name="virtual-applications"></a>虚拟应用程序  

|虚拟应用程序|默认应用程序池|Description|  
|---|-----|---|  
|BAM|BAMAppPool|承载 BAM 门户组件 （页面、 图像、 预编译的代码和其他资源） 虚拟应用程序。 此虚拟应用程序调用 BAMManagementService 应用程序，以与 BAM 数据库进行通信。 **注意：** 若要设置 BAM 门户的外观，可以修改此应用程序的内容。|  
|BAMManagementService|BAMAppPool|BAMManagementService web 服务的宿主虚拟应用程序。 BAM 门户应用程序使用此 web 服务进行通信与 BAM 主导入表 (PIT)。 完成与数据库之间的通信使用的模拟凭据存储在配置期间创建的注册表中。 此 web 服务公开的方法自定义客户端可以用于获取视图及其详细信息、 相关的活动和数据透视表布局的任何用户。 它们还可以用于管理数据库中的警报。|  
|BTSharePointAdapterWS|BTSSharePointAdapterWSAppPool|承载 Windows SharePoint Service 适配器 Web 服务虚拟应用程序。 适用于 BizTalk Server 2013 R2 和 2013 仅。|  


## <a name="more-configuration-topics"></a>更多配置主题  

 [在 Azure VM 上配置 BizTalk Server](http://msdn.microsoft.com/library/azure/jj248689.aspx)  

[在群集中配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)

[用于优化环境的配置后步骤](../install-and-config-guides/post-configuration-steps-to-optimize-your-environment.md)

 [保护 BizTalk Server 部署](../install-and-config-guides/securing-your-biztalk-server-deployment.md)  
