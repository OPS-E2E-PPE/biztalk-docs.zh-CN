---
title: "演练： 部署基本 BizTalk 应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, tutorials
- tutorials, deploying
- tutorials, applications
- applications, tutorials
ms.assetid: 21b67153-0f8c-406a-a224-fc792b16192f
caps.latest.revision: "69"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 445dcdf9685d5b4b74f5d1fd9738da838edb5f42
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="walkthrough-deploying-a-basic-biztalk-application"></a>演练： 部署基本 BizTalk 应用程序
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含用于简化 BizTalk 企业解决方案的管理和部署的功能。 它现在为企业解决方案中的各项（例如业务流程、架构、映射、管道和 .NET 程序集等）提供一个 BizTalk 应用程序容器。 你可以管理、 修改、 部署和安装的所有项作为一个整体应用程序中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]此外包括向导来帮助实现自动化应用程序部署任务。 有关背景信息，请参阅[应用程序部署和管理功能](../core/application-deployment-and-management-features.md)和[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。  
  
 本演练提供有关如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署功能的分步说明，以便你可以了解这些功能是如何协同工作的。 本演练中阐述的部署过程不一定反映在你的公司管理应用程序部署的方式。  
  
 在本演练中，你将创建一个简单的 BizTalk 应用程序，然后将它从开发环境部署到测试环境，再从那里部署到过渡环境和生产环境。 在完成本演练后，你将了解如何执行以下任务：  
  
-   从开发计算机上的 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，使用“部署”命令将 BizTalk 程序集部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的本地实例。 这将创建一个用这些程序集填充的 BizTalk 应用程序。 BizTalk 程序集将包含各种资源信息，例如要在 BizTalk 解决方案中使用的业务流程、管道、架构和映射。  
  
-   从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，添加、 创建、 配置和删除任何项 (称为*项目*) 根据需要创建全功能的业务解决方案，如发送和接收端口、 策略、 程序集，并脚本。  
  
-   使用导出、导入和安装向导，将 BizTalk 应用程序部署到某一测试计算机，以用于功能和系统测试。  
  
-   使用导出、导入和安装向导，将应用程序部署到过渡服务器，以用于最终配置和部署到生产服务器。  
  
## <a name="prerequisites"></a>先决条件  
 你可以采用以下两个选项之一来针对本演练设置你的测试环境：  
  
-   你可以在单台计算机上执行本演练中的任务。  
  
-   你可以通过设置不同的计算机以便分别用作部署、测试、过渡和生产计算机，更准确地模拟真实的部署。 但是，本演练中涉及的任何任务都不应在实际生产环境中执行。  
  
 若要执行本演练中的这些步骤，请确保你的测试环境满足以下先决条件：  
  
-   用于部署 BizTalk 程序集的开发计算机安装了 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
-   在本演练中描述的应用程序部署过程中使用的每台计算机（包括开发计算机）都安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
-   每个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 实例都是一个单独的安装；换言之，它具有自己的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库和组。  
  
 除了上述要求之外，你还需要具备包含 BizTalk 程序集的可用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 解决方案或项目。 如果你没有现有的解决方案或项目，则为了进行演练，可以使用在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK 中包含的 ErrorHandling 示例解决方案。 在本演练的后面部分中包括有关使用此示例的说明。  
  
 在用于执行本演练中的任务的计算机上，你的用户帐户还必须是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组以及本地管理员组的成员。  
  
 有关安装和配置详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[什么是新建、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。
  
##  <a name="BKMK_Assumptions"></a>假设  
 本演练假定以下内容：  
  
-   你具备有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的基本知识。 [BizTalk Server 入门](../core/getting-started-with-biztalk-server.md)应该会有所帮助。
  
-   你所使用的 BizTalk 程序集以前未部署到你的测试环境的应用程序中。 如果已部署，则应该取消部署已部署了这些程序集的 BizTalk 应用程序。 有关说明，请参阅[正在取消部署的 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。  
  
-   没有应用程序资源与其他应用程序共享。  
  
##  <a name="BKMK_Audience"></a>受众  
 本演练面向的读者是：  
  
-   **BizTalk 应用程序开发人员。** 开发人员可以了解如何设置项目属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并部署 BizTalk 程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序。 开发人员还要了解如何将项目添加到应用程序、然后将应用程序导出到某一 .msi 文件。 对于开发人员应用程序部署任务有关背景信息，请参阅[BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)。  
  
-   **BizTalk 应用程序测试人员。** 测试人员可以了解如何将.msi 文件导入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为 BizTalk 应用程序中将其注册其测试计算机上运行。 然后，测试人员可以了解如何在测试计算机上安装应用程序以及如何验证安装。 有关用于测试的应用程序部署任务的背景信息，请参阅[测试 BizTalk 应用程序部署的任务](../core/testing-tasks-for-biztalk-application-deployment.md)。  
  
-   **BizTalk Server IT 管理员。** 负责将 BizTalk 应用程序部署到过渡服务器和生产服务器的 IT 管理员可以了解此任务所需的基本步骤。 有关后台 IT 管理员有关应用程序部署任务的信息，请参阅[BizTalk 应用程序部署的暂存任务](../core/staging-tasks-for-biztalk-application-deployment.md)和[BizTalk 应用程序部署生产任务](../core/production-tasks-for-biztalk-application-deployment.md).  
  
##  <a name="BKMK_Overview"></a>本演练的概述  
 本演练的目的是为了在实验室环境中部署一个 BizTalk 应用程序，以便评估在生产环境中部署此程序时这一技术的作用。 本演练中包含的简单方案（在单台计算机上将单个 .msi 文件作为 BizTalk 应用程序部署）将帮助你熟悉在应用程序部署中涉及的基本任务。  
  
> [!NOTE]
>  本演练并不提供应用程序正常运行所需的应用程序配置（例如绑定业务流程、配置端口等）指导。 本演练只是为了介绍新的应用程序部署功能。  
  
 本文中提供的指导涵盖以下任务：  
  
1.  **配置所需的权限。** 在开始本演练之前，你需要确保具有执行各任务的相应权限。  
  
2.  **从 Visual Studio 的部署 BizTalk 程序集。** 此步骤由应用程序开发人员执行。 从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 内部署 BizTalk 程序集将自动生成程序集，并将其内容部署到 BizTalk 应用程序中。 如果该应用程序已不存在，则部署程序集也会创建该应用程序。 该应用程序的项目将被注册，并且其数据存储在 BizTalk 管理数据库中。 此外，默认情况下，这些程序集安装在本地计算机的全局程序集缓存 (GAC) 中。 在创建该应用程序后，你可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内查看和管理其项目。 在管理控制台中，每个应用程序都存储在各自的文件夹中，并且子文件夹中将包含对该应用程序的所有项目的引用。  
  
3.  **配置应用程序。** 此步骤可由应用程序开发人员或 IT 管理员执行，以便添加、创建和配置为使应用程序正常工作所需的任何项目。 从管理控制台中，你可以轻松地添加、创建、配置和删除项目，例如发送和接收端口、脚本和附加程序集。 如果你对包含所需项目的应用程序感到满意并且正确配置了它们，则按下述内容将其导出到某一 .msi 文件中。  
  
4.  **导出应用程序置于.msi 文件。** 此步骤可由开发人员、测试人员或 IT 管理员执行，以便生成可用于将 BizTalk 应用程序部署到不同环境中的 .msi 文件。 例如，开发人员可以将某一 .msi 文件导出，测试人员可使用该 .msi 文件将应用程序部署到测试服务器中。 在测试完成后，IT 管理员可以使用经过测试的 .msi 文件将应用程序部署到过渡或生产服务器中（如下文所述）。 本演练介绍如何使用导出向导（在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中提供）将某一应用程序导出到 .msi 文件中。  
  
5.  **导入从.msi 文件安装应用程序。** 此步骤可由测试人员或 IT 管理员执行，以便将 BizTalk 应用程序部署到过渡或生产服务器。 例如，测试人员可以将应用程序从开发人员提供的 .msi 文件导入测试计算机上的 BizTalk 组，然后从该 .msi 文件安装此应用程序以便对其进行测试。 同样，IT 管理员可以将应用程序从测试人员提供的 .msi 文件部署到过渡或生产服务器上。 本演练介绍如何使用导入向导将该 .msi 文件导入到 BizTalk 组中的应用程序。 与第 2 步中一样，注册该应用程序的项目并且将其数据存储在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库中。 本演练还介绍如何通过使用安装向导或通过双击该 .msi 文件，将该应用程序安装到当前服务器上。 这将允许你在当前服务器上运行该应用程序。  
  
##  <a name="BKMK_Step-by-step"></a>部署 BizTalk 应用程序的分步指南  
 本部分介绍部署 BizTalk 应用程序的分步过程，包括从开发到测试、过渡和生产的所有阶段。 如前所述，你可以在同一台计算机上执行所有这些步骤，但也可以在多台计算机上执行，以便更准确地模拟你的环境。  
  
#### <a name="1-configure-permissions"></a>1.配置权限  
 第一步是要确保你具有执行本演练中各任务的相应权限。 请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，和[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。
  
#### <a name="2-deploy-the-biztalk-assemblies"></a>2.部署 BizTalk 程序集  
 可以从开发计算机上的 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，使用此步骤中的过程将 BizTalk 程序集部署到 BizTalk 应用程序中。  
  
 在开始之前，你必须在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中已具有某一 BizTalk 解决方案。 你可以创建你自己的解决方案或项目，或你可以将 BizTalk Server 附带 ErrorHandling 示例设置。 你可以按如下所示在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中设置 ErrorHandling 示例解决方案：  
  
###### <a name="to-set-up-the-errorhandling-solution"></a>设置 ErrorHandling 解决方案  
  
1.  在开发计算机上，导航到：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Messaging\ErrorHandling\ErrorHandler  
  
2.  双击**ErrorHandler.btproj**。  
  
     将在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中打开 ErrorHandler 解决方案。 此解决方案包含两个项目： ErrorHandler 和 PipelinesAndSchemas。  
  
     ![在解决方案中的 visual Studio 项目](../core/media/errorhandlingprojects.gif "ErrorHandlingProjects")  
  
 接下来，你必须为该解决方案中的每个项目都设置属性。 ErrorHandling 示例解决方案包括两个项目应为其设置属性： ErrorHandler 和 PipeLinesAndSchemas。 配置属性以反映开发计算机的环境。 例如，你指定的 SQL 服务器应该是在开发计算机上运行的实例，并且是本地 BizTalk 管理数据库的宿主。  
  
###### <a name="to-configure-project-properties"></a>若要配置项目属性  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，用鼠标右键单击想要配置属性，，然后单击的项目**属性**。  
  
2.  单击**部署**项目设计器中的选项卡。  
  
     ![Visual Studio 2005 中的部署属性表](../core/media/deploymentproperties.gif "DeploymentProperties")  
  
3.  下表中所述配置项目属性，然后单击**确定**。  
  
    |属性|值|解释|  
    |--------------|-----------|-----------------|  
    |应用程序名称|\<名称\>|用于将此项目中的程序集部署到的 BizTalk 应用程序的名称。 如果该应用程序已存在，则在你部署该项目时这些程序集将添加到该应用程序中。 如果该应用程序不存在，则将创建该应用程序。 如果此字段为空，则这些程序集将部署到当前组中的默认 BizTalk 应用程序（默认情况下为“BizTalk Application 1”）中。 包含空格的名称必须括在双引号 (") 中。|  
    |配置数据库|\<BizTalk 管理数据库名称\>|用于组的 BizTalk 管理数据库的名称，默认情况下为 BizTalkMgmtDb。|  
    |Server|\<服务器名称\>|作为本地计算机上 BizTalk 管理数据库宿主的 SQL Server 实例的名称。 在单台计算机安装中，该名称通常是本地计算机的名称。 **注意：**此 BizTalk 项目移动到另一台计算机时，如果你将需要修改服务器属性，以反映新的计算机名称，然后你将能够部署程序集。|  
    |重新部署|True 或 False|如果将此项设置为 True（默认设置），你将能够在不更改版本号的情况下重新部署 BizTalk 程序集。|  
    |安装到全局程序集缓存|True 或 False|如果将此项设置为 True（默认设置），则可以在部署程序集时将程序集安装到本地计算机上的全局程序集缓存 (GAC) 中。|  
    |重新启动主机实例|True 或 False|如果将此项设置为 True，则可以在重新部署程序集时自动重新启动在本地计算机上运行的所有主机实例。 如果将此项设置为 False（默认设置），则必须在你重新部署某一程序集时手动重新启动这些主机实例。 **注意：**如果要重新部署解决方案级别中的程序集，主机实例将重新启动一次每个项目具有此选项设置为 True。 这样可能导致多次重新启动。 如果计划在解决方案级重新部署，你可能希望针对解决方案中的一个项目将此属性设置 True，以避免多次主机实例重新启动。 此设置应针对将在解决方案中重新部署的最后一个项目进行。 此外，如果在你执行重新部署时，主机实例停止，它将不会被启动。|  
    |启用单元测试|True 或 False|指定是否启用项目的单元测试。|  
  
4.  对于解决方案中的每个项目，重复执行步骤 1、2 和 3。  
  
 部署过程要求程序集是强签名的。 你可以通过将该项目与一个强名称程序集密钥文件相关联，使你的程序集成为强名称程序集。 如果尚未这样做，则使用以下过程生成一个强名称程序集密钥文件。  
  
###### <a name="to-create-a-strong-name-assembly-key-file"></a>创建强名称程序集密钥文件  
  
1.  启动**Visual Studio 命令提示**。  
  
2.  在命令提示符下，从你要存储密钥文件的文件夹，键入以下命令，然后按 Enter 键：  
  
     **sn-k***file_name* **.snk**   
  
     示例： **sn-k ErrorHandling.snk**  
  
     一条确认消息，**密钥对写入到\<**  *file_name***\>.snk** `,`显示命令行上。  
  
 接下来，你需要将解决方案中的每个项目都与密钥文件相关联。  
  
###### <a name="to-associate-your-projects-with-the-key-file"></a>将你的项目与密钥文件相关联  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后单击**属性**。  
  
2.  单击**签名**项目设计器中的选项卡。  
  
3.  在右窗格中，检查**对程序集签名**框。  
  
4.  单击下的下拉列表框中**选择强名称密钥文件**，单击**\<浏览...\>** ，然后浏览到该密钥文件。  
  
5.  单击密钥文件，然后单击**打开**。  
  
6.  对于你的解决方案中的每个项目，重复执行步骤 1 到 5。  
  
 现在，你可以按如下所示通过一步在解决方案中生成和部署所有程序集。  
  
###### <a name="to-deploy-the-assemblies-in-a-solution"></a>在解决方案中部署程序集  
  
-   在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击解决方案，并依次**部署解决方案**。  
  
     生成和部署过程的状态显示在该页的左下角中。 如果你在使用 ErrorHandling 示例解决方案，则在输出窗口中将显示几个警告消息。 就本演练的目的而言，你可以忽略这些警告。 部署完成后，"部署： 2 成功，0 失败，0 被跳过"将显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]输出窗口。  
  
 部署 BizTalk 程序集可将它们作为 BizTalk 管理数据库中指定 BizTalk 应用程序的一部分注册。 它还将填充的数据库的所有项，或*项目*，包含在程序集。 如果该应用程序在部署前已不存在，则此步骤还创建新的应用程序。 你现在可以从开发计算机上的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台查看 BizTalk 应用程序及其项目。  
  
###### <a name="to-view-the-biztalk-application-and-its-artifacts"></a>查看 BizTalk 应用程序和其项目  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  展开你刚部署了程序集的应用程序的文件夹。  
  
4.  单击该应用程序文件夹下的文件夹，以查看其内容。 在相应的文件夹中，你应该看到在部署的程序集中已包含的项目。 如果你部署了 ErrorHandling 示例 BizTalk 解决方案，则应在“业务流程”、“架构”和“资源”文件夹中看到项目。 你可以右键单击项目，然后单击**属性**要查看其配置设置。  
  
5.  展开**资源**文件夹中，右键单击其中一个程序集，并依次**修改**。  
  
6.  在**选项**框中，记下配置程序集的部署选项。  
  
7.  在**目标位置**，请注意安装应用程序时的程序集文件将复制到其中的位置的路径。 默认情况下，该位置是程序集的源位置。  
  
> [!NOTE]
>  如果你的应用程序不会显示，请右键单击**BizTalk 组**单击**刷新**。  
  
 有关部署的程序集的详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  
  
#### <a name="3-configure-the-application"></a>3.配置应用程序  
 从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台，你可以通过创建、添加和配置项目来配置你的应用程序。  
  
 为使应用程序正常运行，必须正确配置该应用程序。 例如，业务流程必须绑定到某一主机，并且必须配置有发送端口和接收位置。 如果你部署了 ErrorHandling 示例解决方案，则请注意，该应用程序没有发送端口、接收端口或接收位置。 这意味着，这些业务流程不能发送或接收消息。 有关配置应用程序的指导已超出了本演练的范围。 不过，如果你想进行配置，最快的方法就是使用“配置应用程序”对话框，你可以通过右键单击应用程序并单击“配置”来访问该对话框。 有关详细信息，请参阅[如何配置应用程序](../core/how-to-configure-an-application.md)。 除了此方法之外，你还可以配置业务流程，以及单独创建、配置和删除发送端口、发送端口组、接收端口和接收位置。 有关详细信息，请参阅中的相应主题[管理项目](../core/managing-artifacts.md)。  
  
 你可能还想要添加到你的应用程序项目中（例如预处理脚本或自述文件），或者想要删除项目。 你可以使用以下过程尝试此功能。 （ErrorHandling 示例并不包括你可以添加的附加项目；但你可以通过添加已在你的环境中存在的项，测试此功能。）  
  
> [!NOTE]
>  你可以使用预处理和后处理脚本，在应用程序导入、安装或卸载之前或之后执行操作。 例如，可能要在卸载后使用预处理脚本从 GAC 卸载程序集。 有关详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  
  
###### <a name="to-add-an-artifact-to-an-application"></a>向应用程序添加项目  
  
1.  打开 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  若要添加以下类型的项目，右键单击 ErrorHandling 应用程序文件夹，并依次**添加**。 请注意，在你添加某一 BizTalk 程序集时，它所包含的项目也会添加到该应用程序的相应文件夹中。  
  
    -   BizTalk 程序集  
  
    -   预处理脚本  
  
    -   后续处理脚本  
  
    -   资源（BizTalk 程序集、.NET 程序集、预处理脚本、后处理脚本、文件、证书、COM 组件。 BAM 项目、绑定文件和虚拟目录）  
  
    -   策略  
  
 你也可以从应用程序中删除项目。  
  
###### <a name="to-remove-an-artifact-from-an-application"></a>若要从应用程序中删除项目  
  
1.  打开 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  展开包含该项目的文件夹，右键单击该项目，然后单击**删除**。  
  
 有关配置你的应用程序的详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。  
  
#### <a name="4-export-the-application"></a>4.导出应用程序  
 在你创建了某一 BizTalk 应用程序并根据需要进行修改后，可以通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的导出 MSI 文件向导导出该应用程序。 这将生成一个 .msi 文件，你以后可将此文件导入到其他 BizTalk 组中，以在新组中重新创建该应用程序。 若要在特定服务器上运行该应用程序，还必须通过 .msi 文件从本地安装它。  
  
###### <a name="to-export-the-application"></a>若要导出应用程序。  
  
1.  打开 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  右键单击 BizTalk 应用程序，指向**导出**，然后单击**MSI 文件**。  
  
4.  上**欢迎使用导出 MSI 文件向导**页上，单击**下一步**。  
  
5.  上**选择资源**页上，选择的资源，以将导出到.msi 文件，然后单击**下一步**。 就本演练而言，你可以接受显示的默认值。  
  
6.  如果系统提示，请在**指定 IIS 主机**页上，键入承载你想要包括，然后单击的虚拟目录的计算机的服务器名称**下一步**。 仅当先前没有将虚拟目录添加到 BizTalk 管理数据库时（比如将虚拟目录添加到应用程序或将其导入应用程序时），系统才会提示你指定服务器。  
  
    > [!NOTE]
    >  在 ErrorHandling 示例解决方案中没有包括任何虚拟目录。  
  
7.  上**依赖关系**页上，查看应用程序的依赖关系，然后单击**下一步**。  
  
8.  上**目标**页上，在**目标应用程序名称**，键入应用程序名称。  
  
9. 在**MSI 文件以生成**，键入.msi 文件的完整路径，然后单击**导出**。 示例： C:\MSI\Errorhandling.msi  
  
    > [!NOTE]
    >  建议你将 .msi 文件存储在安全的文件夹中。  
  
10. 上**摘要**页上，记下此操作，日志文件的位置，然后单击**完成**。  
  
 在文件系统中，确认已在你指定的位置中创建了该 .msi 文件。  
  
> [!NOTE]
>  为安全起见，在导出应用程序的过程中，密码从应用程序绑定中删除。 从 .msi 文件安装应用程序后，需要重新配置密码，以便使应用程序可以正常运行。 不过，密码并没有被从添加到应用程序中的任何绑定文件中删除。  
  
 有关导出应用程序和项目的详细信息，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
#### <a name="5-import-and-install-the-application"></a>5.导入和安装应用程序  
 下一步骤是要将应用程序从你刚生成的 .msi 文件导入某一 BizTalk 组，并且还在本地计算机上安装该应用程序。 你可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的导入 MSI 向导和安装向导执行此操作。  
  
> [!NOTE]
>  该应用程序必须安装在将运行该应用程序的组中的每台计算机上。 你可以双击该 .msi 文件以便将它安装在其他计算机上。  
  
 每次你要将一个应用程序从一个 BizTalk 组迁移到另一个组时（例如，在从开发环境迁移到测试环境时、从测试环境迁移到过渡环境时或从过渡环境迁移到生产环境时），都可以重复该步骤中的任务。  
  
 此时，如果你只使用一台计算机用于本演练，则应从 BizTalk 组中删除该应用程序。 你还应从全局程序集缓存 (GAC) 中删除这些程序集。 这样，在你导入应用程序时，将能够确认它已正确重新创建。 如果你将多台计算机用于本演练，则无需执行这些任务。  
  
###### <a name="to-delete-the-application-from-the-biztalk-group"></a>从 BizTalk 组中删除应用程序  
  
1.  打开 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  右键单击应用程序，然后单击**删除**。  
  
###### <a name="to-delete-assemblies-from-the-gac"></a>从 GAC 中删除程序集  
  
1.  在文件系统中，导航到 %systemdrive%\Windows\assembly。  
  
2.  右键单击你的解决方案已生成每个程序集文件，单击**卸载**，然后单击**是**以确认。 例如，与 ErrorHandling 项目相关联的程序集文件是 ErrorHandling.ErrorHandler 和 ErrorHandling.PipelinesAndSchemas。  
  
     ![删除从 GAC 的程序集](../core/media/deleteassembly.gif "DeleteAssembly")  
  
 现在，你可以将应用程序导入 BizTalk 组中了。 如果你想要将该应用程序导入在其他计算机上运行的某一 BizTalk 组中，则该 .msi 文件必须可从其他计算机访问。  
  
> [!CAUTION]
>  在安装任何应用程序之前，请确保接收的 .msi 文件来自可信来源。 恶意用户可在 .msi 文件中包括代码，可能会对系统或网络造成不良影响。 有关详细信息，请参阅[安全和 Windows Installer](../core/security-and-windows-installer.md)。  
  
###### <a name="to-import-and-install-the-application"></a>若要导入并安装应用程序  
  
1.  为要导入该应用程序的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的实例打开 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。  
  
3.  右键单击**应用程序**，指向**导入**，然后单击**MSI 文件**。  
  
4.  上**欢迎使用导入向导**页上，在**MSI 文件以导入**，键入.msi 文件的完整路径，然后单击**下一步**。 示例： C:\msi\MyApplication.msi  
  
5.  上**应用程序设置**页上，在**可用的应用程序将引用添加到**，选择要添加的引用，，然后单击应用程序**下一步**。 如果你在使用 ErrorHandling 示例解决方案，则可以接受默认值。  
  
     ![将引用添加到应用程序](../core/media/appreferences.gif "AppReferences")  
  
6.  上**应用程序目标环境设置**页上，确认**\<默认\>**已选择，单击**下一步**。  
  
7.  上**导入摘要**页上，确认的摘要信息是否正确，，然后单击**导入**。  
  
8.  在导入 MSI 向导的最后一个屏幕上，选择**运行应用程序安装向导在本地计算机上安装应用程序**，然后单击**完成**。  
  
     ![从导入向导中启动安装](../core/media/startinstallation.gif "StartInstallation")  
  
9. 上**选择安装文件夹**页上，在**文件夹**，键入 BizTalk 应用程序，安装路径，然后单击**下一步**。  
  
10. 单击**下一步**接下来的三页以继续安装上。  
  
     Windows Installer 会将该应用程序安装在本地计算机上。  
  
11. 上**安装完成**页上，单击**关闭**。  
  
 有关导入应用程序的详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 有关安装应用程序的详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
 接下来，你可以通过验证以下内容，确保该应用程序已导入和安装：  
  
-   该应用程序及其所有项目均存在于管理控制台的该应用程序的文件夹中。  
  
-   应用程序的程序集存在于 GAC 中。  
  
-   与该应用程序相关联的文件存在于你安装该应用程序时指定的路径中。  
  
-   该应用程序显示在“添加或删除程序”控制面板中。  
  
-   如果你配置了应用程序，以便它可以正常工作，例如通过指定发送和接收端口，你现在可以通过右键单击它，然后单击来启动应用程序**启动**。 但默认情况下，ErrorHandling 示例应用程序没有设置为可供使用。因此，除非你已手动配置它，否则，将不能启动它。  
  
-   若要从 BizTalk 组和本地计算机中完全删除应用程序，请按照中的说明[正在取消部署的 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。  
  
## <a name="see-also"></a>另请参阅  
[了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)