---
title: 如何导出 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 50
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6bdab45366e4f1a540e436ee44f6736b04cee08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977510"
---
# <a name="how-to-export-a-biztalk-application"></a>如何导出 BizTalk 应用程序
本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或命令行来导出应用程序。 导出 BizTalk 应用程序会生成一个 Windows Installer (.msi) 文件，该文件包含已选择要导出的应用程序及其任何项目。 默认选项将选择应用程序的所有项目，但您可以选择其中的一个子集。 然后，将 .msi 文件导入到其他 BizTalk 组中，以便将这些项目添加到新组中的现有应用程序、更新现有应用程序中的项目或在包含这些要导入的项目的组中创建新的应用程序。 有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 此外使用.msi 文件将运行它的计算机上安装应用程序，如中所述[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。 如果应用程序包括基于文件的项目，还必须安装这些项目才能让其开始工作。  
  
 导出应用程序时，请切记以下几点：  
  
- **导入绑定将自动覆盖现有绑定。** 如果不希望要导出的应用程序中的绑定覆盖要向其中导入 .msi 文件的应用程序中的绑定，请不要选择绑定文件作为要导出的资源。 在向现有应用程序中导入一个包含绑定文件的 .msi 文件时，即使未选择覆盖现有项目的选项，现有绑定也会被正在导入的绑定所覆盖。  
  
- **用户可能正在更改到的项目时要导出应用程序。** 如果在导出操作正在进行时，某个用户正在修改基于数据库的项目（如虚拟目录、证书或策略），则这些更改不会反映在导出的 .msi 文件中。 因此，我们建议您在用户不可能对这些项目进行更改的时间内计划导出操作。  
  
- **在 Windows Vista 上安装.msi 时，可以显示不正确的错误**。 当使用安装.msi 程序包导出[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可能会收到以下错误，"安装程序遇到意外的错误安装此包。 这可能表示此软件包存在问题。 错误代码为 2869。” 若要纠正此错误，请首先使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 导入该 .msi 包，然后重新导出和安装该包。  
  
- **应用程序可能依赖于另一个应用程序。** 这可能会影响如何部署应用程序。 有关详细信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。  
  
- **您可以在导出前在应用程序中修改资源的目标目录。** 如果你想要更改的目标位置，展开你的应用程序的资源节点，右键单击以更改，然后选择所需的资源**修改**。 在修改资源对话框中，输入新的位置中**目标位置**。  
  
- **如果应用程序包含已从规则引擎数据库中删除的策略，导出将失败。** 时使用规则引擎部署向导从规则引擎数据库中删除策略，它将显示处于"未发布的"状态时，在管理控制台中，您将不能导出该应用程序。 有关规则引擎部署向导的详细信息，请参阅[如何部署和取消部署策略及词汇](../core/how-to-deploy-and-undeploy-policies-and-vocabularies.md)。  
  
> [!IMPORTANT]
>  .Msi 文件可能包含敏感数据。 请务必采取措施来确保文件安全。 有关详细信息，请参阅[安全性和 Windows 安装程序](../core/security-and-windows-installer.md)。  
> 
>  应用程序导出期间不会从应用程序绑定保留密码。 从 .msi 文件安装应用程序后，需要重新配置密码，以便使应用程序可以正常运行。 不过，密码并没有被从添加到应用程序中的任何绑定文件中删除。  
> 
>  如果应用程序包括一个网站还是使用 Web 服务的业务流程，请注意，虚拟目录上的安全设置是生效时的那些应用程序导出期间生成.msi 文件。 如果要部署到生产环境中的应用程序，然后导出该应用程序之前你应验证设置满足安全要求。 如果主机计算机上已存在虚拟目录，其安全设置不会被覆盖，但应用程序中的文件将添加到它。 导入应用程序后，应验证的安全设置。  
> 
>  导出应用程序时，将从文件和文件夹中删除所有随机访问控制列表 (Dacl)。 安装应用程序之后, 必须重新配置文件和文件夹，包括虚拟目录上的所有安全设置。  
> 
> [!NOTE]
>  如果导出操作失败，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将删除所有临时文件以及 .msi 文件（如果创建了 .msi 文件）。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 详细了解权限的详细信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。 此外，必须安装业务规则引擎。 有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。  
  
## <a name="to-export-an-application"></a>导出应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。  
  
3. 右键单击你想要导出，指向应用程序**导出**，然后单击**MSI 文件**。  
  
4. 在欢迎使用导出 MSI 文件向导页上，单击**下一步**。  
  
5. 在选择资源页上，选择要导出到.msi 文件的项目，然后单击**下一步**。  
  
6. 如果系统提示，请在指定 IIS 主机页上，键入承载你想要包括，然后单击虚拟目录的计算机的服务器名称**下一步**。 仅当先前没有将虚拟目录添加到 BizTalk 管理数据库时（比如将虚拟目录添加到应用程序或将其导入应用程序时），系统才会提示你指定服务器。  
  
7. 在依赖项页上，查看应用程序，依赖项，然后单击**下一步**。  
  
8. 在目标页上，在**目标应用程序名**，键入应用程序名称。  
  
9. 在中**MSI 文件以生成**，键入.msi 文件的完整路径，然后单击**导出**。 示例： C:\MSI\Errorhandling.msi  
  
    > [!NOTE]
    >  建议你将 .msi 文件存储在安全的文件夹中。  
  
10. 在摘要页，请记下此操作，日志文件的位置，然后单击**完成**。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 按如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask ExportApp** [**/ApplicationName:**<em>值</em>] **/包：**<em>值</em>[**ResourceSpec:**<em>值</em>[**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。  
  
    例如：  
  
    **BTSTask ExportApp /ApplicationName:MyApplication /Package:C:/MSI/MyApplication.msi /ResourceSpec:"C:\My Files\ResourceSpec.xml"/Server:MySQLServer /Database:BizTalkMgmtDb**  
  
    指定的项目将导出到.msi 文件中指定的位置。  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/ 应用程序名称**|要导出的 BizTalk 应用程序的名称。 如果未指定应用程序名称，则将使用默认 BizTalk 应用程序。 如果名称包含空格，则必须用双引号 （"）。|  
   |**/ 包**|要创建，其文件名包括的.msi 文件的路径。|  
   |**/ ResourceSpec**|资源规范 XML 文件，包括文件名的路径。 可以指定要通过编辑运行 ListApp 时创建的资源规范 XML 文件导出哪些项目命令具有 ResourceSpec 参数，如中所述[ListApp 命令](../core/listapp-command.md)。 您必须手动编辑此文件以添加你想要导出 Web 服务器是否在远程计算机上的虚拟目录的 Internet 信息服务 (IIS) 主机服务器名称。|  
   |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [ExportApp 命令](../core/exportapp-command.md)