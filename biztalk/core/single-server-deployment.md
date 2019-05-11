---
title: 单服务器部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, deploying
- configuring [Windows SharePoint Services adapters], customizing
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
- Windows SharePoint Services adapters, configuring
- configuring [Windows SharePoint Services adapters], single-server deployment
- Windows SharePoint Services adapters, single-server deployment
ms.assetid: 94ba8241-9a30-46ca-b962-721e2d00f420
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bfd875796613087ba0eda23b539a744f9367050
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392967"
---
# <a name="single-server-deployment"></a>单服务器部署
本主题讨论的单服务器安装程序和部署注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器。  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a>在单服务器部署中安装 Windows SharePoint Services 适配器  
 选择 Windows SharePoint Service 适配器 Web 服务组件将安装必需的软件的 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档。 必须安装 Windows SharePoint Services 的服务器上安装此 Web 服务。 适配器 Web 服务可以处理多个 SharePoint 站点，包括承载业务活动服务 (BAS)，而不考虑它们是否相同的 IIS 站点上或在不同的 IIS 站点上的网站。  
  
 Windows SharePoint Services 适配器具有三个组件：  
  
- 运行时组件  
  
- 设计时组件  
  
- 适配器 Web 服务  
  
  适配器运行时已安装并配置自动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。 适配器设计时组件安装和配置与其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。 通过创建 Windows SharePoint Services 端口通过管理工具、 开发人员工具和 SDK 中包含的工具与设计时组件交互或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。 您不能自定义运行时的任何配置选项和设计时组件。 可以自定义仅 Windows SharePoint Service 适配器 Web 服务选项。  
  
  只有 SharePoint Enabled Hosts 组的成员有权调用该适配器 Web 服务。 有关 Windows SharePoint Services 适配器运行时所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全性部分[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
> [!NOTE]
>  如果您选择安装 BAS，将自动选择 Windows SharePoint Services 适配器 Web 服务组件。  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>若要安装的 Windows SharePoint Services 适配器  
  
1.  安装 BizTalk Server。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
2.  上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services 适配器Web 服务**。  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a>在单服务器部署中配置 Windows SharePoint Services 适配器 Web services  
 可以配置 Windows SharePoint Services 适配器使用基本配置或自定义配置。 有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。  
  
### <a name="using-a-basic-configuration"></a>使用基本配置  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以使用默认设置来配置服务器。 使用数据库服务器名称、 用户名称和密码输入到配置向导配置服务器的默认设置。 在配置 Windows SharePoint Services 适配器 Web services 使用基本配置时，会发生以下情况：  
  
-   创建 SharePoint 启用主机 Windows 组。  
  
-   默认网站用于承载 Windows SharePoint Services 适配器  
  
-   创建 BTSSharePointAdapterWSAppPool 应用程序池并将其配置为还用于运行 Windows SharePoint Services 应用程序池的帐户下运行。  
  
-   创建 BTSharePointAdapterWS 虚拟应用程序并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行  
  
> [!NOTE]
>  如果此虚拟目录已存在，配置不会更新元数据库中的属性。 必须删除该虚拟目录，并重新进行配置。  
  
- BTSharePointAdapterWS 虚拟应用程序包含 Web 服务  
  
  有关基本配置的详细信息，请参阅[基本配置](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5)。  
  
### <a name="using-a-custom-configuration"></a>使用自定义配置  
 BizTalk Server 配置可提供已在本地计算机安装的功能的配置状态的高级分析。 该工具，可配置和取消对功能、 配置安全设置，并导入和导出配置，从其他计算机。  
  
 使用**Windows SharePoint Services 适配器 Web Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。 下表列出了配置选项。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**此计算机上启用 Windows SharePoint Services 适配器**|选择**启用此计算机上 Windows SharePoint Services 适配器**若要启用此计算机上的适配器。|  
|**Windows 组**|**Windows 组**列表提供了 BizTalk SharePoint 适配器启用主机 Windows 组的可编辑视图。|  
|**Windows SharePoint Services 适配器网站**|选择将承载 Windows SharePoint Service 适配器 Web 服务的 Web 站点。|  
  
 在配置使用自定义配置的 Windows SharePoint Services 适配器时，会发生以下情况：  
  
-   默认情况下创建 SharePoint 启用主机 Windows 组，除非指定另一个 Windows 组  
  
-   默认网站用于承载 Windows SharePoint Services 适配器，除非指定其他网站  
  
-   创建 BTSSharePointAdapterWSAppPool 应用程序池并将其配置还用于运行 Windows SharePoint Services 应用程序池帐户下运行  
  
-   创建 BTSharePointAdapterWS 虚拟应用程序并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行  
  
> [!NOTE]
>  如果此虚拟目录已存在，配置不会更新元数据库中的属性。 必须删除该虚拟目录，并重新进行配置。  
  
- BTSharePointAdapterWS 虚拟应用程序包含 Web 服务  
  
  有关自定义配置管理器的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a>若要通过使用自定义配置来配置 Windows SharePoint Services 适配器  
  
1.  在中**BizTalk Server 配置**，选择**SharePoint 适配器**节点。  
  
2.  选择**启用此计算机上 Windows SharePoint Services 适配器**。  
  
3.  下**Windows 组**，选择你将使用适用于 Windows SharePoint Services 适配器的 Windows 组。 默认情况下，这是 SharePoint Enabled Hosts。  
  
4.  在中**Windows SharePoint Services 适配器网站**下拉列表框中，选择网站将在其中安装适配器组件。 默认情况下，这是默认 Web 站点。  
  
5.  单击**应用配置**。  
  
## <a name="considerations-for-a-single-server-deployment"></a>单服务器部署的注意事项  
 当您设置和部署在单服务器环境中的 Windows SharePoint Services 适配器时，考虑以下方面：  
  
- BizTalk 服务帐户添加到该服务器上的 SharePoint 启用主机 Windows 组。  
  
- 将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色使用 SharePoint 管理中心工具。  
  
- 在[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，SharePoint 适配器 Web 服务来运行的标识需要以下权限：  
  
   **读取**上的权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。 如果使用的 Windows 和 BizTalk Server 的 64 位版，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**  
  
   **读取**以下注册表项权限：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。  
  
   包含 Sharepoint 数据库的 SQL 服务器上的登录权限。  
  
   成员**公共**并**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。  
  
   成员**公共**并**db 所有者**SharePoint 内容数据库中的角色。  
  
- 在安装 Web 服务的网站必须扩展为 SharePoint Services 网站。  
  
- 你可以安装和配置 Windows SharePoint Services 适配器使用无提示安装。 有关详细信息，请参阅[附录 a:无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。  
  
## <a name="see-also"></a>请参阅  
 [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)   
 [多服务器部署](../core/multiserver-deployment.md)