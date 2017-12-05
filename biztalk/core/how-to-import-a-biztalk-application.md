---
title: "如何导入 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, planning
- planning, importing
- importing, applications
- applications, planning
- planning, deploying
- applications, importing
- importing, planning
ms.assetid: 51169f35-d572-4612-9104-a59908e24874
caps.latest.revision: "70"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65a2e29be82cb55b0c8509eb3adb346f48d5b794
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-import-a-biztalk-application"></a>如何导入 BizTalk 应用程序
本主题介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或命令行，将 BizTalk 应用程序导入到 BizTalk 组。 导入 BizTalk 应用程序时将在 BizTalk 管理数据库中注册项目，并将这些项目的数据写入相应的 BizTalk 数据库。 有关详细信息，请参阅[什么发生时项目导入](../core/what-happens-when-artifacts-are-imported.md)。 在导入某个应用程序时，将不会安装该应用程序。 必须先安装包含基于文件的项目的应用程序，该应用程序才能运行。  
  
 在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台导入应用程序时，您启动导入 MSI 向导的位置决定了在导入项目的同时是否创建新应用程序。 如果通过右键单击 BizTalk 组启动向导，则必须提供应用程序名。 如果您指定的名称是 BizTalk 组中现有应用程序的名称，则文件中的项目将被导入到此应用程序；否则，将创建一个具有指定名称的新应用程序，并将项目导入到该新应用程序。 如果通过右键单击应用程序启动向导，则无法指定应用程序名，项目将被导入到当前应用程序中。  
  
 在使用 BTSTask 命令行工具导入 .msi 文件时，提供应用程序名是可选操作。 如果不提供名称，则文件中的项目将被导入到默认应用程序。  
  
 在导入项目后，您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的应用程序文件夹下的相应文件夹中查看这些项目。 你还可以查看项目的列表应用程序中使用 BTSTask 中, 所述[ListApp 命令](../core/listapp-command.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要导入 BizTalk 应用程序，必须使用作为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的帐户登录。 若要安装 BizTalk 应用程序，还必须具有对本地文件系统的写权限。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="considerations-for-importing-applications"></a>导入应用程序的注意事项  
 在导入应用程序时，应注意以下事项：  
  
-   **从以前版本的 BizTalk Server 导入应用程序**。 如果要从 BizTalk Server 2006 R2 或 BizTalk Server 2009 导入应用程序和应用程序包含 EDI/AS2 方数据，应用程序导入可能会失败，因为中 BizTalk Server 贸易合作伙伴管理模型已显著更改。 您必须改用参与方迁移工具才能从早期的 BizTalk Server 版本迁移参与方数据。 有关工具的详细信息，请参阅[迁移 BizTalk Server 以前版本中的 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
-   **导入的绑定，始终会覆盖现有绑定。** 将包含绑定的 .msi 文件导入到现有应用程序时，现有绑定将被同名的导入绑定覆盖。 即使您没有选择在导入 .msi 文件时覆盖现有项目的选项，现有绑定也将被同名导入绑定覆盖。 如果您不希望用导出的应用程序中的绑定覆盖导入 .msi 文件的应用程序中的绑定，请不要在导出操作中选择将该绑定文件作为资源导出。 有关详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
     由于绑定在导入过程中应用，所以已应用的绑定将被同名的新绑定所覆盖。 换言之，将应用的具有特定名称的最后一个绑定生效。 导入应用程序时，绑定按如下顺序应用：  
  
    1.  由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成的、未通过绑定文件显式添加到应用程序，但用户已经显式选择导出到应用程序 .msi 文件的应用程序绑定。  
  
    2.  已经显式添加但尚未指定目标部署环境的绑定文件。 本组中的绑定可以按任何顺序应用。  
  
    3.  已经显式添加并且具有与为导入应用程序而选的部署环境相匹配的关联目标部署环境的绑定。 本组中的绑定可以按任何顺序应用。  
  
-   **主机组中必须存在。** BizTalk 组中必须存在与在 .msi 文件中包含的应用程序绑定中指定的主机相对应的主机，否则导入操作将失败。 此外，主机的信任级别必须匹配。  
  
-   **你可能需要添加对另一个应用程序的引用。** 如果您要导入应用程序依赖于其他应用程序中的项目，你需要添加到此应用程序的引用。 组中必须存在应用程序和所需的项目。 导入向导可提供此选项。 如果你使用的 BTSTask ImportApp 命令，但是，你必须添加对导入之后, 应用程序的引用中所述[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。 有关背景信息，请参阅[依赖关系和应用程序部署](../core/dependencies-and-application-deployment.md)。 导入向导将这些引用与组中现有应用程序相匹配，并且通过该向导您还可选择添加新引用或更改现有引用。 您应该采用其他步骤来验证引用的应用程序中是否包含所需项目。  
  
-   **如果导入操作超时时，拆分应用程序置于其他.msi 文件。** 如果导入操作的持续时间超过 3600 秒，则该操作超时。 如果在尝试导入 .msi 文件时操作超时，则应通过重新导出该应用程序，并选择要导出的部分项目，将该应用程序的内容分成多个 .msi 文件。 有关详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
> [!IMPORTANT]
>  为安全起见，在导出应用程序的过程中，密码从应用程序绑定中删除。 不过，密码并未从已添加到应用程序的绑定文件中删除。 在导入应用程序后，您需要重新配置密码，以便应用程序可以正常运行。 您可以通过编辑绑定文件或使用管理控制台来完成此操作。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。 有关配置的适配器的安全性的详细信息，请参阅[使用适配器](../core/using-adapters.md)。  
  
> [!NOTE]
>  如果导入失败，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将回滚所有导入操作（自定义脚本执行的所有操作除外）。  
  
> [!NOTE]
>  如果您在一个应用程序中为发送端口创建了筛选器，此应用程序使用另一个应用程序中的属性架构，然后将第一个应用程序导入到新 BizTalk 组中，则您将收到缺少架构的警告，并且在安装和启动该应用程序时筛选功能将无法正常运行。 解决这个问题的方法是：先导入包含该架构的应用程序，然后再安装不包含该架构的应用程序。  
  
## <a name="to-import-a-biztalk-application"></a>若要导入 BizTalk 应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] 和 BizTalk 组，然后执行以下操作之一：  
  
    -   要导入的应用程序和项目.msi 文件中包含到 BizTalk 组，请右键单击**应用程序**，指向**导入**，然后单击**MSI 文件**。  
  
    -   若要导入到现有应用程序的.msi 文件中包含的项目，展开**应用程序**，右键单击应用程序，指向**导入**，然后单击**MSI 文件**.  
  
3.  在导入 MSI 向导页上，欢迎在**MSI 文件以导入**，键入.msi 文件的路径，然后单击**下一步**。 如果有必要，你可以为.msi 文件通过单击浏览**...** 按钮。  
  
4.  在应用程序设置页上，在**应用程序名称**下拉列表中，选择应用程序名称，如果可用。 如果将应用程序导入到 BizTalk 组，则可使用此列表。  
  
    > [!NOTE]
    >  列表中包括 BizTalk 组中当前所有应用程序的名称，以及从其导出 .msi 文件的应用程序的名称。 如果您选择从其导出 .msi 文件的应用程序的名称，但该 BizTalk 组中不存在此应用程序，则导入向导将创建一个新应用程序。 如果选择该组中已存在的应用程序，则导入向导会将 .msi 文件中的项目导入到现有应用程序。  
  
5.  在**可用的应用程序将引用添加到**，选择要向其中添加引用，如果有的话，应用程序，然后单击**下一步**。  
  
6.  如果你.msi 文件导入到现有应用程序，并想要覆盖现有的应用程序中的项目，选择**覆盖资源**。  
  
    > [!NOTE]
    >  如果不选择此选项，并且 .msi 文件中包含的项目已存在于应用程序中，则导入操作将失败并回滚。 BizTalk 应用程序或 BizTalk 组中某些项目类型必须是唯一的。 如果要添加 BizTalk 组中已存在但当前应用程序中不存在的项目，则即使指定了覆盖选项，导入操作也将失败。 有关哪些项目必须唯一，并且在何种方式它们必须是唯一的详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。  
  
7.  在应用程序目标环境设置页上，在**目标过渡环境**下拉列表中，选择目标环境中的为此应用程序，然后单击**下一步**。 此列表包含已为添加到此应用程序的所有绑定文件指定的所有环境。 选择\<默认\>如果你想要应用应用程序除外指定的目标环境中的所有绑定。 如果.msi 文件不包含你想要显式应用的绑定文件，则可以保留\<默认\>选。  
  
    > [!NOTE]
    >  在将绑定文件添加到应用程序时，为这些绑定指定目标环境。 有关背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。 有关添加绑定文件的说明，请参阅[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)。  
  
8.  在导入摘要页面上，确认验证摘要信息是否正确，并依次**导入**。  
  
9. 在导入成功页上，如果你想要在本地计算机上安装应用程序，则选择**运行应用程序安装向导在本地计算机上安装应用程序**复选框。  
  
    > [!NOTE]
    >  除非要以应用程序在本地计算机上当前配置来运行该应用程序，否则不需要安装应用程序。 不过，如果应用程序包含基于文件的项目，则必须先在要运行该应用程序的所有计算机上安装应用程序，然后应用程序才可以正常工作，原因是导入应用程序时只将应用程序添加到 BizTalk 管理数据库。  
  
10. 单击 **“完成”**。  
  
> [!NOTE]
>  如果安装失败（例如，您不具有对本地文件系统的写权限），则将回滚安装操作，但不会回滚导入操作。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1.  如下所示打开命令提示符： 单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2.  键入以下命令，替换为适当的值下, 表中所述：  
  
     **BTSTask ImportApp /Package:** *值*[**/Environment:***值*] [**/ApplicationName:** *值*] [**/覆盖**] [**/Server:***值*] [**/数据库：***值*]  
  
     例如：  
  
     **BTSTask ImportApp /Package:"C:\MSI Files\MyApplication.msi"/Environment:Test /ApplicationName:MyApplication / 覆盖**  
  
    |参数|值|  
    |---------------|-----------|  
    |**/ 包**|.msi 文件的完整路径。 如果该路径包含空格，则必须将其括在引号 (") 中。|  
    |**/ 环境**|绑定文件适用的目标部署环境，如 Test。 此值是将绑定文件添加到应用程序时，指定的目标部署环境的值。|  
    |**/ 应用程序名称**|.msi 文件中的项目将导入到的 BizTalk 应用程序的名称。 如果没有指定 BizTalk 应用程序的名称，则将使用导出 .msi 文件时指定的应用程序的名称。 如果指定的应用程序不存在，则将创建该应用程序。 包含空格的应用程序名必须括在双引号 (") 中。|  
    |**/ 覆盖**|该选项的功能是，如果应用程序中的项目的本地唯一标识符 (LUID) 与 .msi 文件中的项目的本地唯一标识符 (LUID) 相同，则使用后者覆盖前者。 如果未指定此选项，并且应用程序中存在一个或多个项目与 .msi 文件中的项目具有相同的 LUID，则导入失败。 可以通过使用应用程序中查看的项目的 Luid [ListApp 命令](../core/listapp-command.md)。|  
    |**/ 服务器**|BizTalk 管理数据库的宿主 SQL Server 实例的名称，格式为“服务器名称\实例名称,端口”。<br /><br /> 只在实例名称与服务器名称不相同时才需要指定实例名称。 只在 SQL Server 不使用默认端口号 (1433) 时才需要指定端口。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
    |**/ 数据库**|BizTalk 管理数据库的名称。 如果未指定，则使用在本地 SQL Server 实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>另请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportApp 命令](../core/importapp-command.md)