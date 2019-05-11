---
title: 如何向应用程序添加 COM 组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], COM components
- managing [resources], COM components
- applications, COM components
- COM components, applications
ms.assetid: fdda1a9d-96af-41fe-9d94-ee1fbd80a7c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0860fcd21f6a83dd6ce952976e04c5680613673b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387354"
---
# <a name="how-to-add-a-com-component-to-an-application"></a>如何向应用程序添加 COM 组件
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加 COM 组件：  
  
 当向应用程序添加 COM 组件，请记住以下重要事项：  
  
-   如果你想要覆盖应用程序中已存在的 COM 组件，请指定覆盖选项。 仅当两个项目具有相同的本地唯一标识符 (LUID) 时，则需要使用覆盖选项。 如果未指定，且具有相同 LUID 要添加的应用程序中已经存在 COM 组件，则添加操作将失败。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。  
  
-   BizTalk Server 不检查 COM 组件以验证它们存在，因此您应该验证组件所依赖的所有项目都存在的依赖关系。  
  
-   如果添加 64 位非托管的 COM 或 COM + 组件，并尝试安装包括 32 位计算机上的 COM 或 COM + 组件的应用程序，将不会安装该组件。 它将只能在 64 位计算机上安装。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-com-component-to-an-application"></a>若要向应用程序添加 COM 组件  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开 BizTalk Server 管理、 BizTalk 组、 应用程序，和你想要添加 COM 组件的应用程序。  
  
3. 右键单击**资源**文件夹，指向**添加**，然后单击**资源**。  
  
4. 单击**外**，选择 COM 组件，然后单击**打开**。  
  
5. 在中**文件类型**下拉列表中，单击**system.biztalk: com**。  
  
6. 在中**选项**，选中或清除**注册文件 (regsvr32) 目标处**根据是否想要添加到 Windows 注册表中，当应用程序的组件的复选框安装。  
  
7. 在中**目标**，键入 COM 组件从.msi 文件，包括文件名称安装该应用程序时要复制的位置的完整路径。 如果未提供此路径，该文件是期间不会复制到本地文件系统安装。 如果您选择，则需要此路径**注册文件 (regsvr32) 目标处**上一步中的复选框。  
  
    示例： **%BTAD_InstallDir%\MyComponent.dll**  
  
8. 完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Com** [**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Options:Regsvr32OnInstall**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Com / 覆盖 /Source:"C:\Source Components\COM.dll"/Destination:"C:\New Components\COM.dll"/Options:Regsvr32OnInstall /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要向其中添加 COM 组件的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序组。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Type**|**System.biztalk: com** （此值不区分大小写。）|  
   |**/Overwrite**|若要更新现有 COM 组件的选项。 如果未指定，且 COM 组件已存在具有相同 LUID 为 COM 组件添加，则 AddResource 操作将失败的应用程序中。 可以通过使用应用程序中查看项目的 Luid [ListApp 命令](../core/listapp-command.md)。|  
   |**/Source**|包括文件名称的 COM 组件.dll 文件的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/ 目标**|COM 组件.dll 文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果未提供，该文件是期间不会复制到本地文件系统安装;因此，该组件无法添加到 Windows 注册表在安装过程。 如果路径包含空格，则必须将其括在双引号 （"）。 如果指定 Regsvr32OnInstallOption，则还必须指定 Destination。|  
   |**/ 选项**|**Regsvr32OnInstall.** 指定要将 COM 组件添加到 Windows 注册表中，从.msi 文件安装应用程序。 如果指定此选项，则还必须指定 Destination。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令：COM 组件](../core/addresource-command-com-component.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)