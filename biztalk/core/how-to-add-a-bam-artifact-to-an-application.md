---
title: 如何向应用程序添加 BAM 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, definition files [BAM]
- BAM, applications
- managing [applications], definition files [BAM]
- definition files [BAM], managing
ms.assetid: 86f19030-e510-4527-ba74-10498c361c00
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bcd96105455f0940b4882b1019b777922d86755
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981806"
---
# <a name="how-to-add-a-bam-artifact-to-an-application"></a>如何向应用程序添加 BAM 项目
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加 BAM 项目。 添加 BAM 定义文件不会部署 BAM 定义。 导入应用程序 .msi 文件时会部署 BAM 定义。  
  
 如果要覆盖应用程序中已有的 BAM 项目，请指定覆盖选项。 仅当现有 BAM 项目具有与你想要添加的一个文件同名时，则需要使用覆盖选项。 如果未指定，并且具有与要添加文件同名的应用程序中已存在 BAM 项目，则添加操作将失败。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-bam-artifact-to-an-application"></a>向应用程序添加 BAM 项目  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开“[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]”、“BizTalk 组”、“应用程序”和要向其中添加 BAM 项目文件的应用程序。  
  
3. 右键单击**资源**文件夹，指向**添加**，然后单击**资源**。  
  
4. 单击**外**，选择 BAM 项目文件，然后单击**打开**。  
  
5. 在中**文件类型**下拉列表中，选择**system.biztalk: bam**。  
  
6. 在中**目标**，键入从.msi 文件，包括文件名称安装该应用程序时复制项目文件所在的位置的完整路径。 如果不提供此路径，则在安装过程中，该文件将不会被复制到本地文件系统，但在导入应用程序 .msi 文件时，会部署该文件。  
  
    示例： **C:\My Applications\MyBAMfile.xml**  
  
7. 完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:Bam** [**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:Bam / 覆盖 /Source:"C:\Source BAMfiles\MyBAMfile.xml"/Destination:"%BTADInstallDir%\BAMfiles\MyBAMfile.xml"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 应用程序名称**|向其添加 BAM 项目的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/ 类型**|**System.biztalk: bam** （此值不区分大小写。）|  
   |**/ 覆盖**|覆盖现有 BAM 项目的选项。 如果不指定，且应用程序中已存在与要添加的 BAM 项目同名的 BAM 项目，则 AddResource 操作将失败。|  
   |**/ 源**|BAM 项目文件的完整路径，包含文件名。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/ 目标**|从 .msi 文件安装应用程序时，BAM 项目文件要复制到的位置的完整路径。 如果未提供，该文件是期间不会复制到本地文件系统安装。 如果路径包含空格，则必须将其括在双引号 （"）。 您可以在路径中使用环境变量 %BTADInstallDir% 来指定应用程序安装文件夹。|  
   |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： BAM 项目](../core/addresource-command-bam-artifact.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)   
 [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)