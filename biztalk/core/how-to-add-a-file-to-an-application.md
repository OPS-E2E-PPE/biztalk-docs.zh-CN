---
title: "如何将文件添加到应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], adding files
- files, adding to applications
- managing [resources], adding files
ms.assetid: 6665b946-113a-4026-a0a3-6b67ede4b689
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4493eafe2bba4e1203a230180024e0e5a8a2ce08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-file-to-an-application"></a>如何将文件添加到应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加文件。 在安装应用程序时，添加到该应用程序中的文件将复制到安装文件夹。 还可以将文件导出到应用程序的 .msi 文件，以及随应用程序移到不同部署环境中。  
  
> [!NOTE]
>  有关添加一个自述文件的说明，请参阅[如何链接到一个自述文件](../core/how-to-link-to-a-readme-file.md)。  
  
 如果要覆盖应用程序中已有的文件，请指定“Overwrite”选项。 只有两个文件同名时，“Overwrite”选项才生效。 如果未指定“Overwrite”选项，且应用程序中已经存在与要添加的文件名称相同的文件，则添加操作将失败。  
  
> [!NOTE]
>  与某些其他类型的项目不同，BizTalk 组中的多个文件可具有相同的文件名。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-file-to-an-application"></a>若要将文件添加到应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开要向其添加文件的应用程序所在的 BizTalk 组。  
  
3.  展开“应用程序”，然后展开要向其添加文件的应用程序。  
  
4.  右键单击**资源**文件夹，指向**添加**，然后单击**资源**。  
  
5.  单击**添加**，选择的文件，然后单击**打开**。  
  
6.  在**文件类型**下拉列表中，选择**System.BizTalk:File**。  
  
7.  在**目标**，键入该文件包含的文件名称的.msi 文件从安装应用程序时要复制的位置的完整路径。 默认位置为 %BTAD_InstallDir%，即应用程序安装文件夹。 如果未提供此路径，则在安装过程中，该文件不会复制到本地文件系统。  
  
8.  完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:File** [**/覆盖**] **/Source:***值*[**/Destination:***值*] [**/Server:** *值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:File / 覆盖 /Source:"C:\Source Files\File.txt"/Destination:"C:\New Files\File.txt"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|要将文件添加到 BizTalk 应用程序的名称。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:File** （此值不区分大小写。）|  
    |**/ 覆盖**|若要更新现有文件的选项。 如果没有指定，并在文件中的应用程序与正在添加的文件具有相同的名称已存在，则 AddResource 操作将失败。|  
    |**/ 源**|包括文件名称的文件的完整路径。 如果路径包含空格，必须将它括在双引号 （"）。|  
    |**/ 目标**|为文件所在的.msi 文件从安装应用程序时要复制的位置的完整路径。 如果路径包含空格，必须将它括在双引号 （"）。 如果未提供，不复制文件到本地文件系统在安装过程。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： 文件](../core/addresource-command-file.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)