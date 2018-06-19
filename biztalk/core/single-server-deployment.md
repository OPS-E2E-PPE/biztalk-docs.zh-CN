---
title: 单服务器部署 |Microsoft 文档
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
ms.openlocfilehash: 6796bbbad4722e959962ea88e9854bce82476be4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975747"
---
# <a name="single-server-deployment"></a>单服务器部署
本主题将介绍对用于 Windows SharePoint Services 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器进行单服务器安装和部署时的注意事项。  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a>在单服务器部署中安装 Windows SharePoint Services 适配器  
 选择 Windows SharePoint Service 适配器 Web 服务组件将安装为 Windows SharePoint Services 适配器来处理传入和传出文档通过 Windows SharePoint Services 所必需的软件。 此 Web Services 必须安装在安装有 Windows SharePoint Services 的服务器上。 适配器 Web 服务可以处理包括托管业务活动服务 (BAS)，而不考虑它们是否在相同的 IIS 站点或不同的 IIS 站点上的 Web 站点的多个 SharePoint 站点。  
  
 Windows SharePoint Services 适配器有三个组件：  
  
-   运行时组件  
  
-   设计时组件  
  
-   适配器 Web Services  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能将自动安装并配置适配器运行时。 安装和配置与其他适配器的设计时组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。 通过使用管理工具、开发人员工具、SDK 或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能附带的工具来创建 Windows SharePoint Services 端口，可以与设计时组件进行交互。 你无法自定义运行时和设计时组件的任何配置选项。 只能自定义 Windows SharePoint Services 适配器 Web Services 选项。  
  
 只有 SharePoint Enabled Hosts 组的成员才具有调用该适配器 Web Services 的权限。 有关由 Windows SharePoint Services 适配器运行所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全部分[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)。  
  
> [!NOTE]
>  如果选择安装 BAS，系统将自动选择安装 Windows SharePoint Services 适配器 Web Services 组件。  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a>安装 Windows SharePoint Services 适配器  
  
1.  安装 BizTalk Server。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
2.  上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services AdapterWeb 服务**。  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a>在单服务器部署中配置 Windows SharePoint Services 适配器 Web Services  
 你可以使用基本配置或自定义配置来配置 Windows SharePoint Services 适配器。 有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。  
  
### <a name="using-a-basic-configuration"></a>使用基本配置  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 允许用户使用默认设置来配置服务器。 服务器的默认配置设置使用的是你在配置向导中输入的数据库服务器名称、用户名和密码。 当使用基本配置对 Windows SharePoint Services 适配器 Web Services 进行配置时，将出现以下结果：  
  
-   创建 SharePoint Enabled Hosts Windows 组。  
  
-   使用默认网站作为 Windows SharePoint Services 适配器的宿主  
  
-   创建并配置为在还用于运行 Windows SharePoint Services 应用程序池的帐户下运行 BTSSharePointAdapterWSAppPool 应用程序池。  
  
-   创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行  
  
> [!NOTE]
>  如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。 你必须删除该虚拟目录，并重新运行配置。  
  
-   BTSharePointAdapterWS 虚拟应用程序包含 Web Services  
  
 有关基本配置的详细信息，请参阅[基本配置](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5)。  
  
### <a name="using-a-custom-configuration"></a>使用自定义配置  
 BizTalk Server 配置可以对本地计算机上已安装的功能的配置状态进行高级分析。 使用该工具，可以配置功能、取消对功能的配置、配置安全设置，以及将配置导入和导出计算机。  
  
 使用**Windows SharePoint Services 适配器 Web 服务**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。 下表列出了这些配置选项：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**在此计算机上启用 Windows SharePoint Services Adapter**|选择**启用这台计算机上 Windows SharePoint Services Adapter**若要启用此计算机上的适配器。|  
|**Windows 组**|**Windows 组**列表提供了你可以编辑 BizTalk SharePoint 适配器启用主机 Windows 组的视图。|  
|**Windows SharePoint Services 适配器网站**|选择将用作 Windows SharePoint Services 适配器 Web Services 的宿主的网站。|  
  
 当配置使用自定义配置的 Windows SharePoint Services 适配器时，将发生下列情况：  
  
-   默认情况下，除非指定了其他 Windows 组，否则将创建 SharePoint Enabled Hosts 这一 Windows 组。  
  
-   除非指定其他网站，否则将使用默认网站作为 Windows SharePoint Services 适配器的宿主。  
  
-   创建 BTSSharePointAdapterWSAppPool 应用程序池，并将其配置为使用运行 Windows SharePoint Services 应用程序池所用的同一帐户来运行。  
  
-   创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行  
  
> [!NOTE]
>  如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。 你必须删除该虚拟目录，并重新运行配置。  
  
-   BTSharePointAdapterWS 虚拟应用程序包含 Web Services  
  
 有关自定义配置管理器的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a>若要使用自定义配置配置的 Windows SharePoint Services 适配器  
  
1.  在**BizTalk Server 配置**，选择**SharePoint 适配器**节点。  
  
2.  选择**启用这台计算机上 Windows SharePoint Services Adapter**。  
  
3.  下**Windows 组**，选择将用于 Windows SharePoint Services 适配器的 Windows 组。 默认情况下，将选择 SharePoint Enabled Hosts。  
  
4.  在**Windows SharePoint Services 适配器网站**下拉列表中，选择网站将在其中安装适配器组件。 默认情况下，将选择默认网站。  
  
5.  单击“应用配置”。  
  
## <a name="considerations-for-a-single-server-deployment"></a>单服务器部署的注意事项  
 在单服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：  
  
-   将 BizTalk 服务帐户添加到该服务器上的 SharePoint Enabled Hosts 这一 Windows 组中。  
  
-   使用 SharePoint 管理中心工具，将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色中。  
  
-   在 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上，运行 SharePoint 适配器 Web Service 的标识需要具有以下权限：  
  
     **读取**权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。 如果使用的 Windows 和 BizTalk Server 的 64 位版本，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**  
  
     **读取**对以下注册表项的权限： **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。  
  
     包含 Sharepoint 数据库的 SQL Server 的登录权限。  
  
     成员**公共**和**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。  
  
     成员**公共**和**db 所有者**SharePoint 内容数据库中的角色。  
  
-   必须将 Web Services 安装所在的网站扩展为 SharePoint Services 网站。  
  
-   你可以安装和配置使用无提示安装的 Windows SharePoint Services 适配器。 有关详细信息，请参阅[附录 a： 无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md)   
 [多服务器部署](../core/multiserver-deployment.md)