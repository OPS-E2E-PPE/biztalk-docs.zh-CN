---
title: 如何将文件添加到应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding files
- files, adding to applications
- managing [resources], adding files
ms.assetid: 6665b946-113a-4026-a0a3-6b67ede4b689
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3723cd1b3a5e936220bb36268adfd592130a529f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343817"
---
# <a name="how-to-add-a-file-to-an-application"></a>如何将文件添加到应用程序
本主题介绍如何使用 BizTalk Server 管理控制台或命令行向 BizTalk 应用程序添加文件。 您将添加到你的应用程序的文件复制到安装文件夹安装应用程序。 可以还可以导出到应用程序的.msi 文件和文件移动到不同的部署环境与应用程序。  
  
> [!NOTE]
>  添加自述文件的说明，请参阅[自述文件链接如何](../core/how-to-link-to-a-readme-file.md)。  
  
 如果你想要覆盖应用程序中已存在的文件，指定覆盖选项。 这两个文件具有相同的文件名称，则只适用于覆盖选项。 如果未指定，且具有与要添加文件同名的应用程序中已经存在文件，则添加操作将失败。  
  
> [!NOTE]
>  与某些其他类型的项目，您可以在 BizTalk 组中具有相同的文件名称的多个文件。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="to-add-a-file-to-an-application"></a>若要将文件添加到应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]和包含你想要将文件添加该应用的程序的 BizTalk 组。  
  
3. 展开应用程序和你想要将文件添加应用程序。  
  
4. 右键单击**资源**文件夹，指向**添加**，然后单击**资源**。  
  
5. 单击**外**，选择的文件，然后单击**打开**。  
  
6. 在中**文件类型**下拉列表中，选择**system.biztalk: file**。  
  
7. 在中**目标**，键入该文件从.msi 文件，包括文件名称安装该应用程序时要复制的位置的完整路径。 默认值为 %btad_installdir%，应用程序安装文件夹。 如果未提供此路径，该文件是期间不会复制到本地文件系统安装。  
  
8. 完成后，单击 **“确定”**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask AddResource** [**/ApplicationName:**<em>值</em>] **/Type:System.BizTalk:File** [**/overwrite**] **/Source:**<em>值</em>[**/Destination:**<em>值</em>] [**/Server:** <em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:File / 覆盖 /Source:"C:\Source Files\File.txt"/Destination:"C:\New Files\File.txt"/Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ApplicationName**|要将文件添加到 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用默认 BizTalk 应用程序。 如果名称包含空格，则必须将其括在双引号 （"）。|  
   |**/Type**|**System.biztalk: file** （此值不区分大小写。）|  
   |**/Overwrite**|若要更新现有文件的选项。 如果未指定，且文件与要添加的文件具有相同名称的应用程序中已经存在，则 AddResource 操作将失败。|  
   |**/Source**|该文件，其中包括文件名的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。|  
   |**/ 目标**|将文件从.msi 文件安装应用程序时要复制的位置的完整路径。 如果路径包含空格，则必须将其括在双引号 （"）。 如果未提供，该文件是期间不会复制到本地文件系统安装。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令：文件](../core/addresource-command-file.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)