---
title: "如何导出 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, exporting
- exporting, warnings
- exporting, applications
- applications, exporting
- applications, security
- applications, warnings
- exporting, security
ms.assetid: a1d6ffca-3d29-44c7-a811-6cf8b42e23f6
caps.latest.revision: "50"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f1b2becead061ec1bad089bd5ceddbbc076d83f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-export-a-biztalk-application"></a>如何导出 BizTalk 应用程序
本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或命令行来导出应用程序。 导出 BizTalk 应用程序会生成一个 Windows Installer (.msi) 文件，该文件包含已选择要导出的应用程序及其任何项目。 默认选项将选择应用程序的所有项目，但您可以选择其中的一个子集。 然后，将 .msi 文件导入到其他 BizTalk 组中，以便将这些项目添加到新组中的现有应用程序、更新现有应用程序中的项目或在包含这些要导入的项目的组中创建新的应用程序。 有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 你也使用.msi 文件将运行它时，在计算机上安装应用程序中所述[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。 如果应用程序包括基于文件的项目，还必须安装这些项目才能让其开始工作。  
  
 导出应用程序时，请切记以下几点：  
  
-   **导入的绑定会自动重写现有绑定。** 如果不希望要导出的应用程序中的绑定覆盖要向其中导入 .msi 文件的应用程序中的绑定，请不要选择绑定文件作为要导出的资源。 在向现有应用程序中导入一个包含绑定文件的 .msi 文件时，即使未选择覆盖现有项目的选项，现有绑定也会被正在导入的绑定所覆盖。  
  
-   **用户可能进行更改的项目时要导出应用程序。** 如果在导出操作正在进行时，某个用户正在修改基于数据库的项目（如虚拟目录、证书或策略），则这些更改不会反映在导出的 .msi 文件中。 因此，我们建议你在用户不可能将对这些项目进行更改的时间安排导出操作。  
  
-   **在 Windows Vista 上安装一个.msi 时，可以显示不正确的错误**。 当安装.msi 程序包导出使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可能会收到以下不正确的错误，"安装程序遇到意外的错误安装此包。 这可能表示此程序包有问题。 错误代码为 2869。” 若要纠正此错误，请首先使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入该 .msi 包，然后重新导出和安装该包。  
  
-   **应用程序可能存在另一个应用程序依赖关系。** 这可能会影响你部署应用程序的方式。 有关详细信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
-   **您可以在你的应用程序之前，若要导出修改资源的目标目录。** 如果你想要更改的目标位置，展开你的应用程序的资源节点，右键单击你想要更改，然后选择的资源**修改**。 在修改资源对话框中，输入的新位置中**目标位置**。  
  
-   **如果应用程序包含已从规则引擎数据库中删除的策略，导出将会失败。** 当你从规则引擎数据库中移除策略通过使用规则引擎部署向导时，它将显示在处于"未发布"状态，管理控制台，你将不能导出应用程序。 有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略和词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
> [!IMPORTANT]
>  .Msi 文件可能包含敏感数据。 请确保采取措施来确保该文件是安全的。 有关详细信息，请参阅[安全和 Windows Installer](../core/security-and-windows-installer.md)。  
>   
>  应用程序在导出期间，密码会从应用程序绑定。 从 .msi 文件安装应用程序后，需要重新配置密码，以便使应用程序可以正常运行。 不过，密码并没有被从添加到应用程序中的任何绑定文件中删除。  
>   
>  如果应用程序包含网站或业务流程中使用 Web 服务，请注意，虚拟目录上的安全设置那些实际上时应用程序导出期间生成的.msi 文件。 如果要部署到生产环境中的应用程序，然后在导出应用程序之前, 你应验证的设置满足您的安全要求。 如果主机计算机上已存在的虚拟目录，不会覆盖其安全设置，但应用程序中的文件将添加到它。 导入应用程序后，你应验证的安全设置。  
>   
>  导出应用程序时，会从文件和文件夹中删除所有自定义访问控制列表 (Dacl)。 安装应用程序之后, 你必须重新配置上的文件和文件夹，包括虚拟目录的所有安全设置。  
  
> [!NOTE]
>  如果导出操作失败，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将删除所有临时文件以及 .msi 文件（如果创建了 .msi 文件）。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录使用的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。 有关更多详细有关权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。 此外，必须安装对业务规则引擎。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
## <a name="to-export-an-application"></a>若要导出应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。  
  
3.  右键单击你想要导出，指向应用程序**导出**，然后单击**MSI 文件**。  
  
4.  在欢迎使用导出 MSI 文件向导页上，单击**下一步**。  
  
5.  在选择资源页上，选择要将导出到.msi 文件中，项目，然后单击**下一步**。  
  
6.  如果系统提示，请在指定的 IIS 主机页上，键入承载你想要包括，然后单击的虚拟目录的计算机的服务器名称**下一步**。 仅当先前没有将虚拟目录添加到 BizTalk 管理数据库时（比如将虚拟目录添加到应用程序或将其导入应用程序时），系统才会提示你指定服务器。  
  
7.  在依赖关系页上，查看应用程序的依赖关系，然后单击**下一步**。  
  
8.  在目标页上，在**目标应用程序名称**，键入应用程序名称。  
  
9. 在**MSI 文件以生成**，键入.msi 文件的完整路径，然后单击**导出**。 示例： C:\MSI\Errorhandling.msi  
  
    > [!NOTE]
    >  建议你将 .msi 文件存储在安全的文件夹中。  
  
10. 在摘要页面上，记下此操作，日志文件的位置，然后单击**完成**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask ExportApp** [**/ApplicationName:***值*] **/包：***值*[**资源规格:***值*[**/Server:***值*] [**/数据库：***值*]  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
     例如：  
  
     **BTSTask ExportApp /ApplicationName:MyApplication /Package:C:/MSI/MyApplication.msi /ResourceSpec:"C:\My Files\ResourceSpec.xml"/Server:MySQLServer /Database:BizTalkMgmtDb**  
  
     你指定的项目导出到你指定的位置中的.msi 文件。  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 应用程序名称**|要导出的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。 如果名称包含空格，它必须用双引号 （"） 括起来。|  
    |**/ 包**|要创建包括其文件名称的.msi 文件的路径。|  
    |**/ 资源规格**|资源规范 XML 文件，包括文件名的路径。 你可以指定哪些项目通过编辑运行 ListApp 时创建的资源规范 XML 文件导出命令与资源规格参数中所述[ListApp 命令](../core/listapp-command.md)。 你必须手动编辑此文件以添加你想要导出 Web 服务器是否在远程计算机上的虚拟目录的 Internet 信息服务 (IIS) 主机服务器名称。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [ExportApp 命令](../core/exportapp-command.md)