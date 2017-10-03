---
title: "如何将 COM 组件添加到应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], COM components
- managing [resources], COM components
- applications, COM components
- COM components, applications
ms.assetid: fdda1a9d-96af-41fe-9d94-ee1fbd80a7c9
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e32e05fbc7ba9f08a7bbbd5fd546033806c3ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-com-component-to-an-application"></a>如何将 COM 组件添加到应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加 COM 组件：  
  
 向应用程序中添加 COM 组件时，请切记以下几点：  
  
-   如果要覆盖应用程序中已有的 COM 组件，请指定“Overwrite”选项。 仅当两个项目具有相同的本地唯一标识符 (LUID) 时才需要覆盖选项。 如果未指定覆盖选项，且应用程序中已经存在与要添加的组件具有相同 LUID 的 COM 组件，则添加操作将失败。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。  
  
-   BizTalk Server 不检查 COM 组件的依存关系以验证它们是否存在，因此您应该验证组件依赖的任何项目是否存在。  
  
-   如果添加 64 位的非托管 COM 或 COM+ 组件，并尝试在 32 位的计算机上安装包含 COM 或 COM+ 组件的应用程序，则不会安装该组件。 它将仅在 64 位计算机上安装。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-com-component-to-an-application"></a>向应用程序添加 COM 组件  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开“[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理”、“BizTalk 组”、“应用程序”和要向其中添加 COM 组件的应用程序。  
  
3.  右键单击**资源**文件夹，指向**添加**，然后单击**资源**。  
  
4.  单击**添加**，选择 COM 组件，然后单击**打开**。  
  
5.  在**文件类型**下拉列表中，单击**System.BizTalk:Com**。  
  
6.  在**选项**，选中或清除**注册了目标 (regsvr32) 的文件**根据你是否想要添加到 Windows 注册表中，应用程序时的组件的复选框安装。  
  
7.  在**目标**，键入 COM 组件从包括文件名称的.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供此路径，则在安装过程中，该文件不会复制到本地文件系统。 此路径是必需的如果你选择**注册了目标 (regsvr32) 的文件**上一步中的复选框。  
  
     示例： **%BTAD_InstallDir%\MyComponent.dll**  
  
8.  完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Com** [**/覆盖**] **/Source:***值*[**/Destination:***值*] [**/Options:Regsvr32OnInstall**] [**/Server:***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Com / 覆盖 /Source:"C:\Source Components\COM.dll"/Destination:"C:\New Components\COM.dll"/Options:Regsvr32OnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|向其添加 COM 组件的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:Com** （此值不区分大小写。）|  
    |**/ 覆盖**|更新现有 COM 组件的选项。 如果未指定此选项，且应用程序中已经存在与要添加的 COM 组件具有相同 LUID 的 COM 组件，则 AddResource 操作将失败。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。|  
    |**/ 源**|COM 组件 .dll 文件的完整路径，包含文件名。 如果路径包含空格，必须将它括在双引号 （"）。|  
    |**/ 目标**|从 .msi 文件安装应用程序时，COM 组件 .dll 文件要复制到的位置的完整路径。 如果未提供，则安装期间该文件将不会复制到本地文件系统；因此，在安装期间该组件不会添加到 Windows 注册表中。 如果路径包含空格，必须将它括在双引号 （"）。 如果指定 Regsvr32OnInstallOption，则还必须指定 Destination。|  
    |**/ 选项**|**Regsvr32OnInstall。** 指定从 .msi 文件安装应用程序时将 COM 组件添加到 Windows 注册表中。 如果指定此选项，则还必须指定 Destination。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： COM 组件](../core/addresource-command-com-component.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)