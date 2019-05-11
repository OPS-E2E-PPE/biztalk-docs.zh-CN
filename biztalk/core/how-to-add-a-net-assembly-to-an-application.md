---
title: 如何将.NET 程序集添加到应用程序 |Microsoft Docs
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
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 861ffca5f4ec8e7205656fb6b701f51f9952a499
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387251"
---
# <a name="how-to-add-a-net-assembly-to-an-application"></a>如何将.NET 程序集添加到应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行添加到 BizTalk 应用程序的 BizTalk 程序集不是.NET 程序集。 当将.NET 程序集添加到应用程序，请记住以下重要事项：  
  
-   如果你想要覆盖应用程序中已存在的程序集，指定覆盖选项。 仅当两个程序集具有相同的 LUID 时，才需要覆盖选项。 如果未指定，且具有相同 LUID 的程序集所添加的应用程序中已存在，则添加操作将失败。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。  
  
-   当您添加.NET 程序集时，可以指定一个或多个程序集安装到全局程序集缓存 (GAC 中) 的以下选项：  
  
    -   **将添加到全局程序集缓存添加资源 (gacutil)。** 在选择此选项，程序集安装在本地计算机上的 GAC 中，该程序集添加到应用程序，由于使用本主题中的过程时。  
  
    -   **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 当选中此选项时，如果应用程序导出到.msi 文件，并且该.msi 文件导入到 BizTalk 组，导入过程的一部分在本地计算机上的 GAC 中安装该程序集。 如果你的应用程序包括一个策略，以及该策略所依赖的程序集，请选择此选项。 您需要这样做是因为策略所依赖的任何程序集导入包含策略的应用程序时，必须在 GAC 中存在。  
  
    -   **添加到全局程序集缓存 (gacutil) 安装 MSI 文件。** 当选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序时，作为安装过程的一部分在本地计算机上的 GAC 中安装该程序集。  
  
    -   **请对 COM 组件可见 (regasm)。** 时选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序，托管的 COM 程序集添加到作为安装过程的一部分在本地计算机上的 Windows 注册表中。 如果指定此选项，还必须指定目标中的文件的位置。  
  
    -   **注册服务组件 (regsvcs)。** 时选择此选项时，如果应用程序导出到.msi 文件，并根据该.msi 文件的计算机上安装应用程序，托管的 COM + 程序集添加到作为安装过程的一部分在本地计算机上的 Windows 注册表中。 如果指定此选项，还必须指定目标中的文件的位置。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-net-assembly-to-an-application"></a>若要向应用程序添加.NET 程序集  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，展开**应用程序**，然后展开你想要添加.NET 程序集的应用程序。  
  
3. 右键单击**资源**文件夹，指向**添加**，然后单击**资源**。  
  
4. 单击**外**，单击该程序集，然后单击**打开**。  
  
5. 在中**文件类型**下拉列表中，选择**system.biztalk: assembly**。  
  
6. 在中**选项**，选择此程序集的部署选项。  
  
7. 在中**目标**，键入该文件从.msi 文件，包括文件名称安装该应用程序时要复制的位置的完整路径。 如果未提供此路径，该文件是期间不会复制到本地文件系统安装。 若要将文件复制到应用程序安装文件夹中，可以在路径中，采用应用程序安装文件夹的值，在安装应用程序使用 %btad_installdir%环境变量。 这样一来，您不需要了解应用程序安装文件夹的路径时指定的目标位置。  
  
    示例： **%BTADInstall_Dir%\Assemblies\Orchestrations.dll**  
  
8. 单击**依赖项**选项卡并查看此程序集所依赖的项目。  
  
9. 如果此程序集所依赖的项目中不存在此应用程序，并且你想要添加它，请单击**将添加到应用程序**，浏览到该项目，然后单击**打开**。  
  
10. 完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述。  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Assembly** [**/overwrite**]**/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Options:GacOnAdd**<em>&#124;</em> **GacOnInstall**<em>&#124;</em>**GacOnImport**&#124;**RegasmOnInstall** &#124; **RegsvcsOnInstall**] [**/Server:**<em>值</em>] [**/database:** <em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Assembly / 覆盖 /Source:"C:\Source Assemblies\MyAssembly.dll"/Destination:"%BTAD_InstallDir%\New Assemblies\MyAssembly.dll"/Options:GacOnAdd、 RegasmOnInstall/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要将程序集添加到 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Type**|**System.biztalk: assembly** （此值不区分大小写。）|  
   |**/Overwrite**|若要更新的现有程序集的选项。 如果未指定，且程序集已经存在具有相同的全名作为要添加的程序集则 AddResource 操作将失败的应用程序中。 全名包括程序集文件的名称、 版本、 区域性和公钥标记。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。|  
   |**/Source**|包括文件名称的程序集文件的完整路径。 如果路径包含空格，必须将其用双引号 （"）。|  
   |**/ 目标**|程序集文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供，该程序集文件不复制到本地文件系统在安装过程。 如果路径包含空格，必须将其用双引号 （"）。 如果指定 RegasmOnInstall 或 RegsvcsOnInstall 选项，则还必须指定 Destination。 **注意：** 可以在路径中使用 %btad_installdir%环境变量。 在安装应用程序需要的应用程序安装文件夹的值。 这样一来，您不需要了解应用程序安装文件夹的路径时指定的目标位置。 示例： %BTAD_InstallDir%\Assemblies\Orchestrations.dll|  
   |**/ 选项**|-   **GacOnAdd**:在 AddResource 操作过程，在本地计算机上安装到全局程序集缓存 (GAC) 程序集。<br />-   **GacOnInstall**:从.msi 文件安装应用程序时，将程序集安装到 GAC。<br />-   **GacOnImport**:导入应用程序.msi 文件时，将程序集安装到 GAC。<br />-   **RegasmOnInstall**:从.msi 文件安装应用程序时，将托管的 COM 程序集添加到 Windows 注册表。 如果指定此选项，则还必须指定 Destination。<br />-   **RegsvcsOnInstall**： 将托管的 COM + 程序集添加到 Windows 注册表中，从.msi 文件安装应用程序。 如果指定此选项，则还必须指定 Destination。<br /><br /> 必须用逗号分隔多个选项。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令：.NET 程序集](../core/addresource-command-net-assembly.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)