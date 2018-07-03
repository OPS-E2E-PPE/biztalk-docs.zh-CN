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
ms.openlocfilehash: e857aece2911aa9f1b3551f339524d2262cc0bf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979758"
---
# <a name="multiserver-deployment"></a>多服务器部署
本主题讨论在多服务器安装和部署注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器。  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a>在多服务器部署中安装 Windows SharePoint Services 适配器  
 如果选择 Windows SharePoint Services 适配器 Web Services 组件，则会安装 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档所必需的软件。 此 Web Services 必须安装在安装有 Windows SharePoint Services 的服务器上。  
  
 适配器 Web 服务可以处理多个 SharePoint 站点，无论这些站点位于同一 IIS 站点还是位于不同的 IIS 站点。  
  
 Windows SharePoint Services 适配器具有三个组件：  
  
- 运行时组件  
  
- 设计时组件  
  
- 适配器 Web Services  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能将自动安装并配置适配器运行时。 该适配器的设计时组件将与其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能一起安装和配置。 通过使用管理工具、开发人员工具、SDK 或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能附带的工具来创建 Windows SharePoint Services 端口，可以与设计时组件进行交互。 你无法自定义运行时和设计时组件的任何配置选项。 可以自定义仅 Windows SharePoint Services 适配器 Web 服务选项。  
  
  只有 SharePoint Enabled Hosts 组的成员将有权调用该适配器 Web 服务。 有关 Windows SharePoint Services 适配器运行时所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全性部分[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
> [!NOTE]
>  如果选择安装 BAS，系统将自动选择安装 Windows SharePoint Services 适配器 Web Services 组件。  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>安装 Windows SharePoint Services 适配器  
  
1. 安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
2. 上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services 适配器Web 服务**。  
  
> [!NOTE]
>  必须在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时的宿主计算机以及运行 Windows SharePoint Services 的计算机上运行安装和配置。  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a>在多服务器部署中配置 Windows SharePoint Services 适配器 Web Services  
 可以使用 BizTalk Server 配置来配置 Windows SharePoint Services 适配器。 有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。  
  
### <a name="using-a-custom-configuration"></a>使用自定义配置  
 BizTalk Server 配置可以对本地计算机上已安装的功能的配置状态进行高级分析。 使用该工具，可以配置功能、取消对功能的配置、配置安全设置，以及将配置导入和导出计算机。  
  
 使用**Windows SharePoint Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。 下表列出了这些配置选项：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**此计算机上启用 Windows SharePoint Services 适配器**|选择**启用此计算机上 Windows SharePoint Services 适配器**若要启用此计算机上的适配器。|  
|**Windows 组**|**Windows 组**列表提供了 BizTalk SharePoint 适配器启用主机 Windows 组的可编辑视图。|  
|**Windows SharePoint Services 适配器网站**|选择将用作 Windows SharePoint Services 适配器 Web Services 宿主的网站。|  
  
 当使用自定义配置对 Windows SharePoint Services 适配器进行配置时，将出现以下结果：  
  
-   默认情况下，除非指定了其他 Windows 组，否则将创建 SharePoint Enabled Hosts 这一 Windows 组。  
  
-   除非指定其他网站，否则将使用默认网站作为 Windows SharePoint Services 适配器的宿主。  
  
-   创建 BTSSharePointAdapterWSAppPool 应用程序池，并将其配置为使用运行 Windows SharePoint Services 应用程序池所用的同一帐户来运行。  
  
-   创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行  
  
> [!NOTE]
>  如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。 必须删除该虚拟目录，然后重新进行配置。  
  
- BTSharePointAdapterWS 虚拟应用程序包含 Web Services  
  
  有关 BizTalk Server 配置的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a>使用自定义配置对 Windows SharePoint Services 适配器进行配置  
  
1. 在中**BizTalk Server 配置**，选择**SharePoint 适配器**节点。  
  
2. 选择**启用此计算机上 Windows SharePoint Services 适配器**。  
  
3. 下**Windows 组**，选择你将使用适用于 Windows SharePoint Services 适配器的 Windows 组。 默认情况下，将选择 SharePoint Enabled Hosts。  
  
4. 在中**Windows SharePoint Services 适配器网站**下拉列表框中，选择网站将在其中安装适配器组件。 默认情况下，将选择默认网站。  
  
   > [!NOTE]
   >  在未安装任何其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件的远程 SharePoint Server 计算机上安装 Windows SharePoint Services 适配器网站为完全支持配置。  
  
5. 单击“应用配置”。  
  
## <a name="considerations-for-a-multiserver-deployment"></a>多服务器部署的注意事项  
 ![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")  
  
### <a name="general-considerations"></a>常规注意事项  
 在多服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：  
  
- 将 BizTalk 服务帐户添加到每个服务器上的 SharePoint Enabled Hosts 这一 Windows 组中。  
  
- 使用 SharePoint 管理中心工具，将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色中。  
  
- 在 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上，运行 SharePoint 适配器 Web Service 的标识需要具有以下权限：  
  
   **读取**上的权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。 如果使用 Windows 的 64 位版本和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**  
  
   **读取**以下注册表项权限： **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。  
  
   包含 Sharepoint 数据库的 SQL Server 的登录权限。  
  
   成员**公共**并**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。  
  
   成员**公共**并**db 所有者**SharePoint 内容数据库中的角色。  
  
- 必须将 Web Services 安装所在的网站扩展为 SharePoint Services 网站。  
  
- 你可以使用无提示安装方式来安装和配置 Windows SharePoint Services 适配器。 有关详细信息，请参阅[附录 a： 无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。  
  
### <a name="considerations-for-network-load-balancing-nlb"></a>网络负载平衡 (NLB) 的注意事项  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 服务器以及多个 BizTalk server 在同一个组中配置 NLB 群集。 因此，必须按照 SharePoint 文档的建议将 Windows SharePoint Services 安装在 NLB 群集上。  
  
 在具有 NLB 的多服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：  
  
-   通过选择相应的选项，将 Windows SharePoint Services 配置为指向现有 BizTalk 管理数据库。 指向在第一台计算机上创建的 BizTalk 管理数据库。 这将向 Windows SharePoint Services 表明你要设置一个 Web 服务器环境。 通过指向现有内容数据库来扩展网站。  
  
-   你必须在 Web 服务器环境中的每台 Windows SharePoint Services 计算机上扩展同一网站（例如，端口 80 上的默认网站）。  
  
-   必须在每台 NLB 主机上以相同方式安装和配置 BTSharePointAdapterWS。 必须配置以下 NLB 设置：  
  
    -   协议：TCP  
  
    -   端口： 80 （HTTP 端口已在其中安装并配置 Windows SharePoint Services 适配器 Web services 的 IIS Web 站点）  
  
    -   筛选模式： 多个主机  
  
    -   关联：无  
  
> [!NOTE]
>  只有在该站点未配置 HTTPS 时，才能使用此设置。 如果在使用 HTTPS 的站点上安装 BTSharePointAdapterWS Web Services，则必须使用单客户端相似性。  
  
## <a name="see-also"></a>请参阅  
 [Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md)   
 [单服务器部署](../core/single-server-deployment.md)