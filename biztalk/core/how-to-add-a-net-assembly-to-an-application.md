---
title: 如何将.NET 程序集添加到应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [.NET assemblies], adding to applications
- managing [applications], .NET assemblies
- managing [.NET assemblies], applications
- applications, .NET assemblies
- .NET assemblies, adding to applications
ms.assetid: 75dc3303-a622-40df-881e-3109cbc81c91
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b455dfb8f84580e3a8a4f5b6e2322c4f4e1d1b7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-add-a-net-assembly-to-an-application"></a>如何向应用程序中添加 .NET 程序集
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 a BizTalk 应用程序添加并非 BizTalk 程序集的 .NET 程序集。 向应用程序中添加 .NET 程序集时，请切记以下几点：  
  
-   如果要覆盖应用程序中已有的程序集，请指定“Overwrite”选项。 只有在两个程序集具有相同的 LUID 时，才需要“Overwrite”选项。 如果未指定，且应用程序中已存在与要添加的程序集具有相同 LUID 的程序集，则添加操作将失败。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。  
  
-   在添加某一 .NET 程序集时，可以指定以下一个或多个选项，以便将该程序集安装到全局程序集缓存 (GAC) 中：  
  
    -   **将添加到全局程序集缓存在添加资源 (gacutil)。** 如果您选择了此选项，则在按照本主题中介绍的过程将程序集添加到某一应用程序时，该程序集就会安装到本地计算机上的 GAC 中。  
  
    -   **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后该 .msi 文件导入到 BizTalk 组时，程序集将作为导入过程的一部分安装到本地计算机上的 GAC 中。 在应用程序包括某一策略以及该策略所依赖的程序集时，选择此选项。 您需要这样做的原因在于：在您导入包含某一策略的应用程序时，该策略所依赖的任何程序集都必须在 GAC 中存在。  
  
    -   **将添加到 MSI 文件安装 (gacutil) 上的全局程序集缓存。** 如果您选择了此选项，则在应用程序导出到某一 .msi 文件，然后应用程序根据该 .msi 文件安装到某一计算机时，程序集将作为安装过程的一部分安装到本地计算机上的 GAC 中。  
  
    -   **使对 COM 组件 (regasm) 可见。** 在选择此选项时，如果应用程序导出到某一 .msi 文件，并且应用程序根据该 .msi 文件安装到计算机上，则托管的 COM 程序集将作为安装过程的一部分添加到本地计算机上的 Windows 注册表中。 如果您指定该选项，则还必须为目标中的文件指定位置。  
  
    -   **提供服务的注册组件 (regsvcs)。** 在选择此选项时，如果应用程序导出到某一 .msi 文件，并且应用程序根据该 .msi 文件安装到计算机上，则托管的 COM+ 程序集将作为安装过程的一部分添加到本地计算机上的 Windows 注册表中。 如果您指定该选项，则还必须为目标中的文件指定位置。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-net-assembly-to-an-application"></a>向应用程序中添加 .NET 程序集  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击 **启动**, ，单击 **所有程序**, ，单击 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], ，然后单击 **BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开你想要添加的.NET 程序集的应用程序。  
  
3.  右键单击 **资源** 文件夹，指向 **添加**, ，然后单击 **资源**。  
  
4.  单击 **添加**, ，单击该程序集，，然后单击 **打开**。  
  
5.  在 **文件类型** 下拉列表中，选择 **System.BizTalk:Assembly**。  
  
6.  在 **选项**, ，选择此程序集的部署选项。  
  
7.  在 **目标**, ，键入该文件包含的文件名称的.msi 文件从安装应用程序时要复制的位置的完整路径。 如果未提供此路径，则在安装过程中，该文件不会复制到本地文件系统。 若要将该文件复制到应用程序文件夹，您可以在路径中使用 %BTAD_InstallDir% 环境变量，这会在安装应用程序时取应用程序安装文件夹的值。 这样，在您指定目标位置时，无需知道应用程序安装文件夹的路径。  
  
     示例︰ **%BTADInstall_Dir%\Assemblies\Orchestrations.dll**  
  
8.  单击 **依赖关系** 选项卡并查看此程序集所依赖的项目。  
  
9. 如果此程序集所依赖的项目中不存在此应用程序，并且你想要添加它，请单击 **将添加到应用程序**, ，浏览到该项目，然后单击 **打开**。  
  
10. 完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符︰ 单击 **启动**, ，单击 **运行**, ，类型 `cmd`, ，然后单击 **确定**。  
  
2.  键入以下命令，替换适当的值，如下表中所述：  
  
     **BTSTask AddResource** [**/ApplicationName:***value*] **/Type:System.BizTalk:Assembly** [**/Overwrite**] **/Source:***value* [**/Destination:***value*] [**/Options:GacOnAdd***&#124;***GacOnInstall***&#124;***GacOnImport**&#124;**RegasmOnInstall**&#124;**RegsvcsOnInstall**] [**/Server:***value*] [**/Database:***value*]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Assembly / 覆盖 /Source:"C:\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd、 RegasmOnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|“值”|  
    |---------------|-----------|  
    |**/ 应用程序名称**|向其添加程序集的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:Assembly** （此值不区分大小写。）|  
    |**/ 覆盖**|更新现有程序集的选项。 如果未指定，且应用程序中已存在与要添加的程序集具有相同全名的程序集，则 AddResource 操作将失败。 全名包括程序集名称、文件名、版本、区域性和公钥标记。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。|  
    |**/ 源**|程序集文件的完整路径，包含文件名。 如果路径包含空格，则必须将它用双引号 （"）。|  
    |**/ 目标**|从 .msi 文件安装应用程序时，程序集文件要复制到的位置的完整路径。 如果未提供，则安装期间该程序集文件将不会复制到本地文件系统。 如果该路径包含空格，则必须将其括在双引号 (") 中。 如果指定 RegasmOnInstall 或 RegsvcsOnInstall 选项，则还必须指定 Destination。 **注意︰**  可以在路径中使用 %btad_installdir%环境变量。 在安装应用程序时，该变量将取应用程序安装文件夹的值。 这样，在您指定目标位置时，无需知道应用程序安装文件夹的路径。 示例︰ %BTAD_InstallDir%\Assemblies\Orchestrations.dll|  
    |**/ 选项**|-   **GacOnAdd**︰ 在 AddResource 操作过程中在本地计算机上安装到全局程序集缓存 (GAC) 的程序集。<br />-   **GacOnInstall**︰ 从.msi 文件安装应用程序时，将程序集安装到 GAC。<br />-   **GacOnImport**︰ 导入应用程序.msi 文件时，将程序集安装到 GAC。<br />-   **RegasmOnInstall**︰ 将托管的 COM 程序集添加到 Windows 注册表中，从.msi 文件安装应用程序时。 如果指定此选项，则还必须指定 Destination。<br />-   **RegsvcsOnInstall**︰ 将托管的 COM + 程序集添加到 Windows 注册表中，从.msi 文件安装应用程序时。 如果指定此选项，则还必须指定 Destination。<br /><br /> 多个选项之间必须用逗号分开。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令：.NET 程序集](../core/addresource-command-net-assembly.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)