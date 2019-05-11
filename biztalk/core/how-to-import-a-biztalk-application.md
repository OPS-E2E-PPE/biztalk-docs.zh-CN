---
title: 如何导入 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 70
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eb247964aa25edc83171ef16bbc4f97afd930d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384998"
---
# <a name="how-to-import-a-biztalk-application"></a>如何导入 BizTalk 应用程序
本主题介绍如何使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或命令行导入 BizTalk 组的 BizTalk 应用程序。 导入 BizTalk 应用程序的 BizTalk 管理数据库中注册项目并将这些项目的数据写入相应的 BizTalk 数据库。 有关详细信息，请参阅[什么发生时导入项目](../core/what-happens-when-artifacts-are-imported.md)。 导入应用程序不会安装该应用程序。 必须安装包含基于文件的项目，然后才能运行的应用程序。  
  
 当你使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来导入应用程序，启动导入 MSI 向导的位置确定是否可以导入项目的同时创建新的应用程序。 如果通过右键单击 BizTalk 组启动向导，则必须提供应用程序名称。 如果 BizTalk 组中的现有应用程序具有您指定的名称，该文件中的项目导入此应用程序否则为创建具有指定的名称的新应用程序，并向其导入项目。 如果通过右键单击应用程序启动向导，不能指定一个应用程序的名称，并导入到当前应用程序项目。  
  
 当您使用 BTSTask 命令行工具导入的.msi 文件时，提供应用程序名称是可选的。 如果未提供一个名称，其项目是导入到默认应用程序。  
  
 在导入项目之后, 您可以查看它们中的应用程序的文件夹下的相应文件夹中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 您还可以查看的项目列表的应用程序中使用 BTSTask，如中所述[ListApp 命令](../core/listapp-command.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要导入 BizTalk 应用程序，您必须登录的成员帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 若要安装 BizTalk 应用程序，您必须具有本地文件系统上的写入权限。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="considerations-for-importing-applications"></a>有关导入应用程序的注意事项  
 在导入应用程序，可能适用以下注意事项：  
  
- **从早期版本的 BizTalk Server 导入应用程序**。 如果从 BizTalk Server 2006 R2 或 BizTalk Server 2009 导入应用程序和应用程序包含 EDI/AS2 参与方数据，应用程序导入可能会失败，因为在 BizTalk Server 贸易合作伙伴管理模型发生了显著。 而是必须使用参与方迁移工具将从 BizTalk Server 早期版本迁移参与方数据。 有关工具的详细信息，请参阅[从以前版本的 BizTalk Server 迁移 EDI 项目](http://msdn.microsoft.com/library/b956a97e-03d0-47ea-a2ce-c07a339c0f2c)。  
  
- **导入绑定将始终覆盖现有绑定。** 导入一个包含绑定到现有应用程序的.msi 文件时，将被导入具有相同名称的绑定覆盖现有绑定。 这是这种情况，即使你未选择覆盖现有项目时导入.msi 文件的选项。 如果不希望要导出到其中导入.msi 文件的应用程序中的绑定覆盖应用程序中的绑定，然后应作为资源导出导出操作期间不选择绑定文件。 有关详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
   当导入过程中应用绑定时，已应用的绑定将覆盖具有相同名称的新绑定。 换而言之，具有特定名称的最后一个绑定，应用将生效。 导入应用程序时，绑定按以下顺序应用：  
  
  1. 生成的应用程序绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未显式添加到应用程序通过绑定文件，但已经显式选择导出到应用程序.msi 文件的用户。  
  
  2. 已显式添加，并且没有指定目标部署环境的绑定文件。 在此集中的绑定可以按任何特定顺序应用。  
  
  3. 绑定已显式添加的且具有相关联的目标部署环境为应用程序导入选择的部署环境相匹配。 在此集中的绑定可以按任何特定顺序应用。  
  
- **主机组中必须存在。** 主机相对应的.msi 文件中包含的应用程序绑定中指定的主机必须已存在于 BizTalk 组或导入操作将失败。 此外，主机的信任级别必须与匹配。  
  
- **您可能需要添加对另一个应用程序的引用。** 如果您要导入的应用程序依赖于另一个应用程序中的某个项目，您需要添加对此应用程序的引用。 应用程序和所需的项目必须已存在的组中。 导入向导提供了此选项。 如果使用 BTSTask 的 ImportApp 命令，但是，您必须添加对导入之后，应用程序的引用中所述[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。 有关背景信息，请参阅[依赖项和应用程序部署](../core/dependencies-and-application-deployment.md)。 导入向导匹配对组中的现有应用程序的引用，并可选择要添加新引用或更改现有引用。 应执行验证引用的应用程序包含所需的项目的额外的步骤。  
  
- **如果导入操作超时时，拆分到多个.msi 文件的应用程序。** 导入操作将超时，如果超过 3600 秒的持续时间。 如果你尝试导入.msi 文件，并在操作超时，应通过重新导出该应用程序，并选择要导出项目的一个子集来划分到多个.msi 文件的应用程序的内容。 有关详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
> [!IMPORTANT]
>  出于安全原因，在应用程序导出过程中不会保留密码从应用程序绑定。 它们不会但是，删除从绑定文件已添加到应用程序中。 在导入应用程序之后, 将需要重新配置密码，以便对函数应用程序。 可以通过编辑绑定文件或使用管理控制台执行此操作。 有关编辑绑定文件的详细信息，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。 有关配置适配器的安全性的详细信息，请参阅[使用适配器](../core/using-adapters.md)。  
> 
> [!NOTE]
>  如果导入失败，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将回滚所有导入操作除外自定义脚本执行的任何操作。  
> 
> [!NOTE]
>  如果一个应用程序在另一个应用程序中使用的属性架构中创建的发送端口的筛选器，然后将第一个应用程序导入新的 BizTalk 组，不会收到的警告，该架构缺少，并且筛选功能将不正常时安装和启动应用程序。 可以通过导入包含架构，然后再安装不包含架构的应用程序的应用程序来更正此问题。  
  
## <a name="to-import-a-biztalk-application"></a>若要导入 BizTalk 应用程序  
  
#### <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开 BizTalk 组，然后执行下列操作之一：  
  
   -   若要导入的应用程序和项目的.msi 文件中包含的 BizTalk 组，请右键单击**应用程序**，依次指向**导入**，然后单击**MSI 文件**。  
  
   -   若要导入到现有应用程序的.msi 文件中包含的项目，展开**应用程序**，右键单击该应用程序，指向**导入**，然后单击**的MSI文件**.  
  
3. 在导入 MSI 向导页上，欢迎在**MSI 文件导入**，键入.msi 文件的路径，然后单击**下一步**。 如果有必要，则可以浏览.msi 文件通过单击 **...** 按钮。  
  
4. 在应用程序设置页上，在**应用程序名称**下拉列表中，选择的应用程序名称，如果可用。 如果要导入 BizTalk 组应用程序提供了的列表。  
  
   > [!NOTE]
   >  该列表包含当前 BizTalk 组，以及从其导出.msi 文件的应用程序中的所有应用程序的名称。 如果您选择后一种应用程序的名称，并且该应用程序尚不存在此 BizTalk 组中，导入向导将创建新的应用程序。 如果组中选择的应用程序已存在，导入向导项目从.msi 文件导入现有的应用程序。  
  
5. 在中**可用的应用程序将引用添加到**，选择要添加的引用，如果有的话，应用程序，然后单击**下一步**。  
  
6. 如果你将.msi 文件导入到现有应用程序，并想要覆盖现有应用程序中的项目，选择**覆盖资源**。  
  
   > [!NOTE]
   >  如果不选择此选项，并且该.msi 文件中包含应用程序中已存在的项目，导入操作将失败并回滚。 某些类型的 BizTalk 应用程序或组中的项目必须是唯一的。 如果在 BizTalk 组中，但不是在当前应用程序，要添加的项目的已存在，导入操作将失败，即使指定覆盖选项。 有关哪些项目必须是唯一的以及以何种方式它们必须是唯一的详细信息，请参阅[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)。  
  
7. 在应用程序目标环境设置页上，在**目标过渡环境**下拉列表中，选择目标环境以便将此应用程序，然后单击**下一步**。 此列表包含所有已添加到此应用程序的绑定文件指定的所有环境。 选择\<默认\>如果你想要应用除已指定目标环境的应用程序中的所有绑定。 如果.msi 文件不包含你想要显式应用的绑定文件，则可以保留\<默认\>选定。  
  
   > [!NOTE]
   >  将绑定文件添加到应用程序时指定绑定的目标环境。 有关背景信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。 有关添加绑定文件的说明，请参阅[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)。  
  
8. 在导入摘要页面上，确认的摘要信息是否正确，然后依次**导入**。  
  
9. 在导入成功页上，如果你想要在本地计算机上安装应用程序，则选择**运行应用程序安装向导以在本地计算机上安装应用程序**复选框。  
  
    > [!NOTE]
    >  除非你需要按当前配置本地计算机上运行应用程序，您不需要安装它。 如果应用程序包含基于文件的项目，但是，必须在所有将运行它，才能开始正常运行的计算机上安装应用程序，原因是导入应用程序仅将其添加到 BizTalk 管理数据库。  
  
10. 单击 **“完成”**。  
  
> [!NOTE]
>  如果安装失败，例如因为不在本地文件系统上具有写权限，安装将回滚，但不是导入操作。  
  
#### <a name="using-the-command-line"></a>使用命令行  
  
1. 打开命令提示符，如下所示：单击**启动**，单击**运行**，类型`cmd`，然后单击**确定**。  
  
2. 键入以下命令，替换适当的值下, 表中所述：  
  
    **BTSTask 的 ImportApp /Package:** *值*[**/Environment:**<em>值</em>] [**/ApplicationName:** <em>值</em>] [**/overwrite**] [**/Server:**<em>值</em>] [**/database:**<em>值</em>]  
  
    例如：  
  
    **BTSTask ImportApp /Package:"C:\MSI Files\MyApplication.msi"  /Environment:Test /ApplicationName:MyApplication /Overwrite**  
  
   |参数|ReplTest1|  
   |---------------|-----------|  
   |**/Package**|将.msi 文件的完整路径。 如果路径包含空格，则必须将其括在引号 （"）。|  
   |**/ 环境**|要将应用，例如测试的绑定文件的目标部署环境。 这是绑定文件添加到应用程序时为目标部署环境指定的值。|  
   |**/ApplicationName**|.Msi 文件中的项目导入到 BizTalk 应用程序的名称。 如果未指定，是应用程序名称指定使用导出.msi 文件时。 如果指定的应用程序不存在，将创建它。 包含空格的应用程序名必须括在双引号 （"）。|  
   |**/Overwrite**|若要使用具有相同的本地唯一标识符 (LUID) 与.msi 文件中的项目覆盖应用程序中的项目的选项。 如果未指定此选项，并且有一个或多个项目中具有相同 LUID 的应用程序.msi 文件，导入中的项目将失败。 可以通过使用应用程序中查看的项目的 Luid [ListApp 命令](../core/listapp-command.md)。|  
   |**/Server**|承载 BizTalk 管理数据库，在窗体 ServerName\InstanceName，端口中的 SQL Server 实例的名称。<br /><br /> 实例名称仅是所需的实例名称不同于服务器名称时。 端口是仅在 SQL Server 使用的端口号而不是默认 (1433) 时所需。<br /><br /> 示例：<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 如果未提供，则使用本地计算机上运行的 SQL Server 实例的名称。|  
   |**/Database**|BizTalk 管理数据库的名称。 如果未指定，使用 SQL Server 的本地实例中运行的 BizTalk 管理数据库。|  
  
## <a name="see-also"></a>请参阅  
 [导入 BizTalk 应用程序、 绑定和策略](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [ImportApp 命令](../core/importapp-command.md)