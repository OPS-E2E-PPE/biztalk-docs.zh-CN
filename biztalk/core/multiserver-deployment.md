---
title: 多服务器部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], multi-server deployment
- planning, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, deploying
- Windows SharePoint Services adapters, multi-server deployment
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
ms.assetid: 0c6e2aa0-e873-461b-8101-9b0988019597
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a767c0edd8c174919979ece2d42cf21b1b6bb7bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323752"
---
# <a name="multiserver-deployment"></a>多服务器部署
本主题讨论在多服务器安装和部署注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器。  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a>在多服务器部署中安装 Windows SharePoint Services 适配器  
 选择 Windows SharePoint Services 适配器 Web Services 组件将安装必需的软件的 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档。 必须安装 Windows SharePoint Services 的服务器上安装此 Web 服务。  
  
 适配器 Web 服务可以处理多个 SharePoint 站点，无论它们是相同的 IIS 站点上或位于不同的 IIS 站点。  
  
 Windows SharePoint Services 适配器具有三个组件：  
  
- 运行时组件  
  
- 设计时组件  
  
- 适配器 Web 服务  
  
  适配器运行时已安装并配置自动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。 适配器设计时组件安装和配置与其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。 通过创建 Windows SharePoint Services 端口通过管理工具、 开发人员工具和 SDK 中包含的工具与设计时组件交互或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。 您不能自定义运行时的任何配置选项和设计时组件。 可以自定义仅 Windows SharePoint Services 适配器 Web 服务选项。  
  
  只有 SharePoint Enabled Hosts 组的成员将有权调用该适配器 Web 服务。 有关 Windows SharePoint Services 适配器运行时所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全性部分[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
> [!NOTE]
>  如果您选择安装 BAS，将自动选择 Windows SharePoint Services 适配器 Web 服务组件。  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>若要安装的 Windows SharePoint Services 适配器  
  
1. 安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
2. 上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services 适配器Web 服务**。  
  
> [!NOTE]
>  您必须安装和配置在计算机上运行该主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时和计算机正在运行 Windows SharePoint Services。  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a>在多服务器部署中配置 Windows SharePoint Services 适配器 Web services  
 配置 Windows SharePoint Services 适配器使用 BizTalk Server 配置。 有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。  
  
### <a name="using-a-custom-configuration"></a>使用自定义配置  
 BizTalk Server 配置可提供已在本地计算机安装的功能的配置状态的高级分析。 该工具，可配置和取消对功能、 配置安全设置，并导入和导出配置，从其他计算机。  
  
 使用**Windows SharePoint Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。 下表列出了配置选项。  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**此计算机上启用 Windows SharePoint Services 适配器**|选择**启用此计算机上 Windows SharePoint Services 适配器**若要启用此计算机上的适配器。|  
|**Windows 组**|**Windows 组**列表提供了 BizTalk SharePoint 适配器启用主机 Windows 组的可编辑视图。|  
|**Windows SharePoint Services 适配器网站**|选择将承载 Windows SharePoint Services 适配器 Web services 的 Web 站点。|  
  
 在配置使用自定义配置的 Windows SharePoint Services 适配器时，会发生以下情况：  
  
-   默认情况下创建 SharePoint 启用主机 Windows 组，除非指定另一个 Windows 组  
  
-   默认网站用于承载 Windows SharePoint Services 适配器，除非指定其他网站  
  
-   创建 BTSSharePointAdapterWSAppPool 应用程序池并将其配置还用于运行 Windows SharePoint Services 应用程序池帐户下运行  
  
-   创建 BTSharePointAdapterWS 虚拟应用程序并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行  
  
> [!NOTE]
>  如果此虚拟目录已存在，配置不会更新元数据库中的属性。 必须删除该虚拟目录，并重新进行配置。  
  
- BTSharePointAdapterWS 虚拟应用程序包含 Web 服务  
  
  有关 BizTalk Server 配置的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a>若要通过使用自定义配置来配置 Windows SharePoint Services 适配器  
  
1. 在中**BizTalk Server 配置**，选择**SharePoint 适配器**节点。  
  
2. 选择**启用此计算机上 Windows SharePoint Services 适配器**。  
  
3. 下**Windows 组**，选择你将使用适用于 Windows SharePoint Services 适配器的 Windows 组。 默认情况下，这是 SharePoint Enabled Hosts。  
  
4. 在中**Windows SharePoint Services 适配器网站**下拉列表框中，选择网站将在其中安装适配器组件。 默认情况下，这是默认 Web 站点。  
  
   > [!NOTE]
   >  不具有任何其他远程 SharePoint Server 计算机上的 Windows SharePoint Services 适配器 Web 站点安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装的组件是完全受支持的配置。  
  
5. 单击**应用配置**。  
  
## <a name="considerations-for-a-multiserver-deployment"></a>多服务器部署的注意事项  
 ![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")  
  
### <a name="general-considerations"></a>一般注意事项  
 当您设置和部署多服务器环境中的 Windows SharePoint Services 适配器时，考虑以下方面：  
  
- BizTalk 服务帐户添加到每个服务器上的 SharePoint 启用主机 Windows 组。  
  
- 将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色使用 SharePoint 管理中心工具。  
  
- 在[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，SharePoint 适配器 Web 服务来运行的标识需要以下权限：  
  
   **读取**上的权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。 如果使用 Windows 的 64 位版本和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**  
  
   **读取**以下注册表项权限：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。  
  
   包含 Sharepoint 数据库的 SQL 服务器上的登录权限。  
  
   成员**公共**并**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。  
  
   成员**公共**并**db 所有者**SharePoint 内容数据库中的角色。  
  
- 在安装 Web 服务的网站必须扩展为 SharePoint Services 网站。  
  
- 你可以安装和配置 Windows SharePoint Services 适配器使用无提示安装。 有关详细信息，请参阅[附录 a:无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。  
  
### <a name="considerations-for-network-load-balancing-nlb"></a>考虑网络负载平衡 (NLB)  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 服务器以及多个 BizTalk server 在同一个组中配置 NLB 群集。 为此，Windows SharePoint Services 必须安装在 NLB 群集上按照 SharePoint 文档的建议。  
  
 当你设置和部署 Windows SharePoint Services 适配器使用 NLB 的多服务器环境中时，考虑以下方面：  
  
-   通过选择指向现有 BizTalk 管理数据库的选项来配置 Windows SharePoint Services。 指向第一台计算机上创建的 BizTalk 管理数据库。 这向 Windows SharePoint Services 表明，你要将 Web 服务器环境。 通过指向现有内容数据库中扩展 Web 站点。  
  
-   您必须扩展 Web 服务器环境中每个 Windows SharePoint Services 计算机上的相同 Web 站点 （例如，端口 80 上默认 Web 站点）。  
  
-   必须安装并配置每台 NLB 主机上的相同方式 BTSharePointAdapterWS。 必须配置下列 NLB 设置：  
  
    -   协议：TCP  
  
    -   端口：80 （HTTP 端口已在其中安装并配置 Windows SharePoint Services 适配器 Web services 的 IIS Web 站点）  
  
    -   筛选模式：多个主机  
  
    -   关联：None  
  
> [!NOTE]
>  仅当该站点未配置为支持 HTTPS，可以使用此设置。 如果在使用 HTTPS 的站点上安装 BTSharePointAdapterWS Web 服务，则必须使用单客户端相关性。  
  
## <a name="see-also"></a>请参阅  
 [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)   
 [单服务器部署](../core/single-server-deployment.md)