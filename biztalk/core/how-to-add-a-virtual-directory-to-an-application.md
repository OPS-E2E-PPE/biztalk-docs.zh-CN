---
title: "如何将虚拟目录添加到应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directories
- managing [applications], virtual directories
- applications, virtual directories
- virtual directories, applications
ms.assetid: a5726696-bd65-49d9-8814-a078afe8c067
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26627387a65b19cef8146cee8b91b2a7a0919059
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-virtual-directory-to-an-application"></a>如何向应用程序添加虚拟目录
本主题介绍如何使用 BTSTask 命令行工具向 BizTalk 应用程序添加虚拟目录。 此选项在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中不可用。 如果您编写了一个自定义 Web Services 或创建了一个用于与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 连接的 ASP.NET 网站，可能就需要添加虚拟目录，并且希望通过应用程序部署虚拟目录。  
  
 另一种方法添加到应用程序的虚拟目录是虚拟目录指定的 SOAP 或 HTTP 接收位置，如中所述[如何配置 HTTP 接收位置](../core/how-to-configure-an-http-receive-location.md)。 在所有情况下，虚拟目标都添加到 BizTalk 管理数据库。 通过使用命令行添加虚拟目录，它还会显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在添加到应用程序的资源文件夹和应用程序时使用中的项目的列表中[ListApp 命令](../core/listapp-command.md)。 如果您稍后导出该应用程序，然后又将其导入到另一个 BizTalk 组，则虚拟目录显示在“资源”文件夹中。  
  
 向应用程序中添加虚拟目录时，请切记以下几点：  
  
-   可以通过指定覆盖选项来覆盖应用程序中已有的虚拟目录。 仅当现有的虚拟目录具有与你想要添加的相同名称时，则需要使用覆盖选项。 如果未指定，和虚拟目录已存在与所添加的相同名称的应用程序中，添加操作将失败。  
  
-   使用包含 https 的 URL 添加虚拟目录时，必须在指定的 URL 中使用 http，而不是 https。 如果使用 https，则添加虚拟目录的操作将失败。 即使添加时在 URL 中使用 http，Internet 信息服务元数据库中 URL 的 https 设置仍将有效，而且虚拟目录将正常工作。  
  
-   如果添加的是 64 位版本 Web Services 的虚拟目录，而尝试在 32 位计算机上安装包含该虚拟目录的应用程序，则无法安装该虚拟目录。 64 位计算机上必须安装它。  
  
> [!IMPORTANT]
>  导入包含虚拟目录的应用程序时，虚拟目录的安全设置是在应用程序导出期间生成 .msi 文件时起作用的那些设置。 如果要向生产环境中部署应用程序，则在导出应用程序之前，应验证设置满足安全要求。  
>   
>  不过，如果目标环境中已经存在虚拟目录，现有虚拟目录的安全设置将生效。 它们不会被更改以匹配您部署的虚拟目录的安全设置。 在这种情况下，您应该验证现有虚拟目录的安全设置是否满足您的要求。  
  
> [!CAUTION]
>  如果虚拟目录使用 HTTPS（安全超文本传输协议）协议，则在导出期间不会保留其安全设置，进行导入时，虚拟目录将继承根的安全设置。 您应该验证安全设置是否满足您的要求。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的步骤，你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的帐户身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-virtual-directory-to-an-application"></a>向应用程序添加虚拟目录  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask AddResource** [/**ApplicationName:***值*] **/Type:System.BizTalk:WebDirectory**[**/Overwrite**] **/Source:***值*[**/Destination:***值*] [**/Server:** *值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask AddResource /ApplicationName:MyApplication /Type: System.BizTalk:WebDirectory / 覆盖 /Source:http://Host1:90 / MyVirtualDirectory /Destination:http://Host2:90 / MyVirtualDirectory /Server:MyDatabaseServer /Database:BizTalkMgmtDb**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|虚拟目录要添加到的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则使用组的默认 BizTalk 应用程序。 如果名称包含空格，必须将它括在双引号 （"）。|  
    |**/ 类型**|**System.BizTalk:WebDirectory** （此值不区分大小写。）|  
    |**/ 覆盖**|更新现有虚拟目录的选项。 如果未指定，且应用程序中已经存在与要添加的虚拟目录同名的虚拟目录，则 AddResources 操作将失败。|  
    |**/ 源**|源虚拟目录的 URI。|  
    |**/ 目标**|从 .msi 文件安装应用程序时要分配给该虚拟目录的 URI。 如果未指定此参数，则使用 Source 参数的值，localhost 作为主机。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [管理.NET 程序集、 证书和其他资源](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource 命令： 虚拟目录](../core/addresource-command-virtual-directory.md)   
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)