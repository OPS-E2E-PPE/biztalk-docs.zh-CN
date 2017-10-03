---
title: "如何将一个 BAM 项目添加到应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, definition files [BAM]
- BAM, applications
- managing [applications], definition files [BAM]
- definition files [BAM], managing
ms.assetid: 86f19030-e510-4527-ba74-10498c361c00
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44b4a55141b2e5cfbc527dd386c9f1cbdd464dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-bam-artifact-to-an-application"></a>如何将一个 BAM 项目添加到应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加 BAM 项目。 添加 BAM 定义文件不会部署 BAM 定义。 导入应用程序 .msi 文件时会部署 BAM 定义。  
  
 如果要覆盖应用程序中已有的 BAM 项目，请指定覆盖选项。 仅当现有 BAM 项目具有与你想要添加的一个同名文件时，则需要使用覆盖选项。 如果未指定，并且 BAM 项目已存在相同的文件名与所添加的应用程序中，添加操作将失败。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-bam-artifact-to-an-application"></a>向应用程序添加 BAM 项目  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**Al 程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”、“应用程序”和要向其中添加 BAM 项目文件的应用程序。  
  
3.  右键单击**资源**文件夹，指向**添加**，然后单击**资源**。  
  
4.  单击**添加**，选择 BAM 项目的文件，然后单击**打开**。  
  
5.  在**文件类型**下拉列表中，选择**System.BizTalk:BAM**。  
  
6.  在**目标**，键入项目文件从包括文件名称的.msi 文件安装应用程序时要复制的位置的完整路径。 如果不提供此路径，则在安装过程中，该文件将不会被复制到本地文件系统，但在导入应用程序 .msi 文件时，会部署该文件。  
  
     示例： **C:\My Applications\MyBAMfile.xml**  
  
7.  完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddResource** [**/ApplicationName:***值*] **/Type:System.BizTalk:Bam** [**/覆盖**] **/Source:***值*[**/Destination:***值*] [**/Server:** *值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam / 覆盖 /Source:"C:\Source BAMfiles\MyBAMfile.xml"/Destination:"%BTADInstallDir%\BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|向其添加 BAM 项目的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:Bam** （此值不区分大小写。）|  
    |**/ 覆盖**|覆盖现有 BAM 项目的选项。 如果不指定，且应用程序中已存在与要添加的 BAM 项目同名的 BAM 项目，则 AddResource 操作将失败。|  
    |**/ 源**|BAM 项目文件的完整路径，包含文件名。 如果路径包含空格，必须将它括在双引号 （"）。|  
    |**/ 目标**|从 .msi 文件安装应用程序时，BAM 项目文件要复制到的位置的完整路径。 如果未提供，不复制文件到本地文件系统在安装过程。 如果路径包含空格，必须将它括在双引号 （"）。 您可以在路径中使用环境变量 %BTADInstallDir% 来指定应用程序安装文件夹。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： BAM 项目](../core/addresource-command-bam-artifact.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)