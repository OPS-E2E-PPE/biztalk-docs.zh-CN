---
title: 演练：部署基本 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, tutorials
- tutorials, deploying
- tutorials, applications
- applications, tutorials
ms.assetid: 21b67153-0f8c-406a-a224-fc792b16192f
caps.latest.revision: 69
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d3e680e80aa66f1ab7c320d43eb848f0d1b39d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395363"
---
# <a name="walkthrough-deploying-a-basic-biztalk-application"></a>演练：部署基本 BizTalk 应用程序
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括简化的管理和部署 BizTalk 业务解决方案的功能。 它现在提供了 BizTalk 应用程序容器中的业务解决方案，如业务流程、 架构、 映射、 管道、 架构和.NET 程序集的项。 可以管理、 修改、 部署和安装应用程序作为一个单元中的所有项。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 此外包括向导，可帮助自动执行应用程序部署任务。 有关背景信息，请参阅[应用程序部署和管理功能](../core/application-deployment-and-management-features.md)并[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。  

 本演练提供了有关使用的分步说明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署功能，以便可以了解它们如何协同工作。 在本演练中所示的部署过程可能会或可能不反映应用程序部署在你的公司管理的方式。  

 在此演练中，将创建简单的 BizTalk 应用程序，然后将其部署到测试环境的开发环境，并从到过渡和生产环境。 完成此演练后，你将了解如何执行以下任务：  

- 从内部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的开发计算机上，使用部署命令将 BizTalk 程序集部署到的本地实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这将创建 BizTalk 应用程序中已填充的程序集。 BizTalk 程序集包含资源信息，例如业务流程、 管道、 架构和映射若要在 BizTalk 解决方案中使用。  

- 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，添加、 创建、 配置和删除任何项 (称为*项目*) 根据需要创建一个全功能的业务解决方案，例如发送和接收端口、 策略、 程序集，并脚本。  

- 使用导出、 导入和安装向导部署到测试计算机以用于 BizTalk 应用程序功能和系统测试。  

- 使用导出、 导入和安装向导部署到过渡服务器以用于最终配置应用程序和部署到生产服务器。  

## <a name="prerequisites"></a>先决条件  
 可以设置测试环境在本演练中的两个选项：  

- 在本演练中在单台计算机上，可以执行任务。  

- 通过设置不同的计算机以使用开发、 测试、 过渡和生产计算机，来更紧密地模拟实际的部署。 在本演练中的任务都不应该在实际生产环境中，但是。  

  若要在本演练中执行的步骤，请确保你的测试环境满足以下先决条件：  

- 用于部署 BizTalk 程序集的开发计算机了 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]安装。  

- 在本演练中，包括开发计算机中所述的应用程序部署过程中使用的每台计算机具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。  

- 每个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]实例是一个单独的安装; 换言之，它具有自己[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和组。  

  除了上述要求，你需要准备[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案或项目可包含 BizTalk 程序集。 如果没有现有的解决方案或项目，则可以使用包含的 ErrorHandling 示例解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK 实现此目的。 稍后在本演练包含有关使用此示例的说明。  

  您还必须具有的成员的用户帐户[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组，以及你将用于执行本演练中的任务的计算机上的本地管理员组。  

  有关安装和配置详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[新增功能、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。

##  <a name="BKMK_Assumptions"></a> 假设  
 本演练的假设条件如下：  

- 你具有的基本知识[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [开始使用 BizTalk Server](../core/getting-started-with-biztalk-server.md)应帮助。

- 向应用程序在测试环境中尚未部署正在使用的 BizTalk 程序集。 如果他们有帐户，应取消部署已部署到的 BizTalk 应用程序。 有关说明，请参阅[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。  

- 没有应用程序资源与其他应用程序共享。  

##  <a name="BKMK_Audience"></a> 受众  
 本演练的受众是：  

- **BizTalk 应用程序开发人员。** 开发人员可以了解如何在中设置项目属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并将其部署 BizTalk 程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序。 开发人员还了解如何将项目添加到应用程序，然后将导出到.msi 文件的应用程序。 有关应用程序部署任务的开发人员背景信息，请参阅[BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)。  

- **BizTalk 应用程序测试人员。** 测试人员可以了解如何将.msi 文件导入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]其测试计算机，将它注册为 BizTalk 应用程序上运行。 然后，测试人员可以了解如何在测试计算机上安装应用程序以及如何验证安装。 用于测试的应用程序部署任务的背景信息，请参阅[BizTalk 应用程序部署的测试任务](../core/testing-tasks-for-biztalk-application-deployment.md)。  

- **BizTalk Server IT 管理员。** 负责 BizTalk 应用程序部署到过渡和生产服务器的 IT 管理员可以了解此任务所需的基本步骤。 有关针对 IT 管理员应用程序部署任务有关背景信息，请参阅[BizTalk 应用程序部署的暂存任务](../core/staging-tasks-for-biztalk-application-deployment.md)和[BizTalk 应用程序部署的生产任务](../core/production-tasks-for-biztalk-application-deployment.md).  

##  <a name="BKMK_Overview"></a> 本演练概述  
 本演练的目的是部署 BizTalk 应用程序在实验室环境来评估在生产环境中部署时，此技术将如何工作。 在本演练-将单个.msi 文件部署为 BizTalk 应用程序在一台计算机 – 将帮助你熟悉与应用程序部署中涉及的基本任务中包含的简单方案。  

> [!NOTE]
>  本演练不提供对于应用程序配置，例如绑定业务流程、 配置端口、 指南和等，这是对函数的应用需要。 本演练的目的只是引入新的应用程序部署功能。  

 本文档中提供的说明涵盖以下任务：  

1. **配置所需的权限。** 在开始本演练之前，需要确保具有适当的权限来执行每个任务。  

2. **部署 BizTalk 程序集从 Visual Studio。** 此步骤均由应用程序开发人员。 部署 BizTalk 程序集内的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]自动生成程序集并将其内容部署到 BizTalk 应用程序。 如果应用程序不存在，部署程序集还会创建应用程序。 注册应用程序的项目，并且其数据存储在 BizTalk 管理数据库。 此外，默认情况下程序集都安装在本地计算机的全局程序集缓存 (GAC) 中。 创建应用程序后，可以查看和管理其项目内[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在管理控制台中，每个应用程序存储在其自己的文件夹，并且子文件夹中包含对所有应用程序的项目引用。  

3. **配置应用程序。** 要添加、 创建和配置所需的应用程序才能正常工作的所有项目的应用程序开发人员或 IT 管理员可以执行此步骤。 从管理控制台中，您可以轻松地添加、 创建、 配置和删除项目，例如发送和接收端口、 脚本和其他程序集。 在后满足应用程序包含所需的项目，并且配置正确，您将其导出到.msi 文件，如下所述。  

4. **正在导出到.msi 文件的应用程序。** 开发人员、 测试人员或 IT 管理员可以执行此步骤中生成可用于部署到不同环境的 BizTalk 应用程序的.msi 文件。 例如，开发人员可以导出测试人员可用于部署到测试服务器上的应用程序的.msi 文件。 测试完成后，IT 管理员然后可以使用经过测试的.msi 文件将应用部署到过渡或生产服务器 （按下文所述）。 本演练介绍如何使用导出向导，可从导出到.msi 文件的应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

5. **正在导入从.msi 文件安装应用程序。** 此步骤可由测试人员或 IT 管理员部署到过渡或生产服务器上的 BizTalk 应用程序。 例如，测试人员可以从入在测试计算机上的 BizTalk 组由开发人员提供的.msi 文件导入应用程序，然后从.msi 文件安装应用程序，以便对其进行测试。 同样，IT 管理员可以部署到过渡或生产服务器上测试人员提供的.msi 文件中的应用程序。 本演练介绍如何使用导入向导将.msi 文件导入 BizTalk 组中的应用程序。 如步骤 2 中所示注册应用程序的项目并且将其数据存储在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 本演练还介绍了如何使用安装向导或通过双击.msi 文件在当前服务器上安装应用程序。 这允许你在当前服务器上运行应用程序。  

##  <a name="BKMK_Step-by-step"></a> 部署 BizTalk 应用程序的分步指南  
 本部分提供了分步操作过程中部署 BizTalk 应用程序的所有阶段，通过从开发到过渡和生产测试。 正如前面提到，可以在同一计算机上执行这些步骤，或如果想要更准确地模拟你的环境，可以使用多台计算机。  

#### <a name="1-configure-permissions"></a>1.配置权限  
 第一步是确保具有适当的权限来执行本演练中的任务。 请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)，并[最低安全权限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)。

#### <a name="2-deploy-the-biztalk-assemblies"></a>2.部署 BizTalk 程序集  
 从 Microsoft 内部[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的开发计算机上，使用过程在此步骤中将部署到 BizTalk 应用程序的 BizTalk 程序集。  

 在开始之前，必须具有在某一 BizTalk 解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 您可以创建自己的解决方案或项目中，或者可以设置与 BizTalk Server 提供的 ErrorHandling 示例。 你可以设置 ErrorHandling 示例解决方案中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如下所示：  

###### <a name="to-set-up-the-errorhandling-solution"></a>若要设置 ErrorHandling 解决方案  

1. 在开发计算机上，导航到：  

    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Messaging\ErrorHandling\ErrorHandler  

2. 双击**ErrorHandler.btproj**。  

    在中打开 ErrorHandler 解决方案[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 此解决方案包含两个项目：ErrorHandler 和 PipelinesAndSchemas。  

    ![在解决方案中的 visual Studio 项目](../core/media/errorhandlingprojects.gif "ErrorHandlingProjects")  

   接下来，必须在解决方案中设置为每个项目的属性。 ErrorHandling 示例解决方案包括两个项目应为其设置属性：ErrorHandler 和 PipeLinesAndSchemas。 配置属性以反映开发计算机的环境。 例如，你指定的 SQL server 应在开发计算机上运行的实例并且这本地的 BizTalk 管理数据库的宿主。  

###### <a name="to-configure-project-properties"></a>若要配置项目属性  

1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击想要配置属性，然后单击的项目的**属性**。  

2. 单击**部署**项目设计器中的选项卡。  

    ![在 Visual Studio 2005 中的部署属性表](../core/media/deploymentproperties.gif "DeploymentProperties")  

3. 下表中所述配置项目属性，然后单击**确定**。  


   |             属性             |                ReplTest1                 |                                                                                                                                                                                                                                                                                                                                                                                               解释                                                                                                                                                                                                                                                                                                                                                                                                |
   |----------------------------------|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |         应用程序名称         |               \<名称\>               |                                                                                                                                                         要将此项目中的程序集部署到 BizTalk 应用程序的名称。 如果应用程序已存在，这些程序集在部署项目将添加到它。 如果应用程序不存在，将创建应用程序。 如果此字段为空，则程序集将部署到默认 BizTalk 应用程序中的当前组中，"BizTalk Application 1"默认情况下。 包含空格的名称必须用双引号引起来 （'） 括起来。                                                                                                                                                         |
   |      配置数据库      | \<BizTalk 管理数据库名称\> |                                                                                                                                                                                                                                                                                                                                                             对于组，默认情况下 BizTalkMgmtDb BizTalk 管理数据库的名称。                                                                                                                                                                                                                                                                                                                                                             |
   |              “服务器”              |           \<服务器名称\>            |                                                                                                                                                                                                          承载在本地计算机上的 BizTalk 管理数据库的 SQL Server 实例的名称。 在单计算机安装中，这通常是本地计算机的名称。 **注意：** 如果将此 BizTalk 项目移到另一台计算机时，将需要修改服务器属性，使之反映新的计算机名称，然后你将能够部署程序集。                                                                                                                                                                                                          |
   |             重新部署             |            True 或 False             |                                                                                                                                                                                                                                                                                                                                          此项设置为 True （默认值），可在不更改版本号的情况下重新部署 BizTalk 程序集。                                                                                                                                                                                                                                                                                                                                          |
   | 安装到全局程序集缓存 |            True 或 False             |                                                                                                                                                                                                                                                                                                                            此项设置为 True （默认值） 时部署程序集无法在本地计算机上安装到全局程序集缓存 (GAC) 程序集。                                                                                                                                                                                                                                                                                                                             |
   |      重新启动主机实例      |            True 或 False             | 此项设置为 True 会自动重新启动时重新部署程序集在本地计算机上运行的所有主机实例。 如果设置为 False （默认值），则必须手动重新启动主机实例时重新部署程序集。 **注意：** 如果要重新部署程序集从解决方案级，主机实例将重新启动一次每个项目，此选项设置为 True。 这可能会导致多次重新启动。 如果您计划在解决方案级重新部署，可能想要将此属性设置为 True 上只有一个项目中的解决方案，以避免多次主机实例重新启动。 此属性应设置将在重新部署解决方案中的最后一个项目。 此外，如果主机实例停止时执行重新部署，它将不会启动。 |
   |       启用单元测试        |            True 或 False             |                                                                                                                                                                                                                                                                                                                                                                        指定是否为项目启用单元测试。                                                                                                                                                                                                                                                                                                                                                                         |


4. 为解决方案中每个项目重复步骤 1、 2 和 3。  

   部署过程要求程序集强签名。 强为程序集签名通过将项目与一个强名称程序集密钥文件相关联。 如果尚未这样做，使用以下过程生成强名称程序集密钥文件。  

###### <a name="to-create-a-strong-name-assembly-key-file"></a>若要创建强名称程序集密钥文件  

1. 启动**Visual Studio 命令提示符**。  

2. 在命令提示符下，从你想要存储密钥文件的文件夹键入以下命令，然后按 ENTER:  

    **sn -k**  *file_name* **.snk**  

    示例： **sn-k ErrorHandling.snk**  

    一条确认消息，**密钥对写入\<**  <em>file_name</em>**\>.snk** `,`显示命令行上。  

   接下来，您需要将解决方案中的每个项目与密钥文件相关联。  

###### <a name="to-associate-your-projects-with-the-key-file"></a>若要将你的项目与密钥文件相关联  

1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击项目，然后单击**属性**。  

2. 单击**签名**项目设计器中的选项卡。  

3. 在右窗格中，检查**为程序集签名**框。  

4. 单击下的下拉列表框**选择强名称密钥文件**，单击**\<浏览...\>** ，然后浏览到该密钥文件。  

5. 单击密钥文件，然后单击**打开**。  

6. 你的解决方案中每个项目重复步骤 1 至 5。  

   现在可以生成并部署所有在一个步骤中，解决方案中的程序集，如下所示。  

###### <a name="to-deploy-the-assemblies-in-a-solution"></a>若要部署一个解决方案中的程序集  

- 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案资源管理器，右键单击解决方案，然后依次**部署解决方案**。  

   生成和部署过程中显示的页面的左下角的状态。 如果您在使用 ErrorHandling 示例解决方案，多个警告消息将显示在输出窗口中。 出于本演练的目的，你可以忽略这些。 部署完成后，"部署：2 成功，0 失败，0 已跳过"中显示[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]输出窗口。  

  部署 BizTalk 程序集注册它们作为 BizTalk 管理数据库中指定的 BizTalk 应用程序的一部分。 它还将填充数据库使用的所有项，或*项目*，包含在程序集。 如果在部署前已不存在该应用程序，此步骤还创建一个新的应用程序。 现在，您可以查看 BizTalk 应用程序和从其项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发计算机上的管理控制台。  

###### <a name="to-view-the-biztalk-application-and-its-artifacts"></a>若要查看 BizTalk 应用程序和其项目  

1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 展开您只需向其部署您的程序集的应用程序的文件夹。  

4. 单击以查看其内容的应用程序文件夹下的文件夹。 在相应的文件夹中，应看到已包含在您部署的程序集的项目。 如果您部署了 ErrorHandling 示例 BizTalk 解决方案，你应看到业务流程、 架构和资源文件夹中的项目。 您可以右键单击项目，然后单击**属性**若要查看其配置设置。  

5. 展开**资源**文件夹中，右键单击某个程序集，然后依次**修改**。  

6. 在中**选项**框中，记下为该程序集配置的部署选项。  

7. 在中**目标位置**，请注意在安装应用程序将复制程序集文件的位置的路径。 这是默认情况下的程序集的源位置。  

> [!NOTE]
>  如果你的应用程序不会显示，请右击**BizTalk 组**然后单击**刷新**。  

 有关部署程序集的详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

#### <a name="3-configure-the-application"></a>3.配置应用程序  
 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您可以通过创建、 添加和配置项目配置你的应用程序。  

 函数为应用程序，它必须正确配置。 例如，业务流程必须绑定到的主机，并且必须具有发送端口和接收位置配置。 如果您部署了 ErrorHandling 示例解决方案，您会注意到，该应用程序没有发送端口、 接收端口或接收位置。 这意味着业务流程不能发送或接收消息。 它是超出了本演练的范围为提供的应用程序配置的说明。 如果你想要执行此操作，但是，最快的方法是使用配置应用程序对话框中，右键单击该应用程序，单击配置访问。 有关详细信息，请参阅[如何配置应用程序](../core/how-to-configure-an-application.md)。 除了此方法时，还可以配置业务流程创建，并配置，并删除发送端口、 发送端口组、 接收端口，并单独接收位置。 有关详细信息，请参阅中的相应主题[管理项目](../core/managing-artifacts.md)。  

 您可能想要添加到你的应用程序项目，例如预处理脚本或自述文件，或删除项目。 您可以试用此功能使用以下过程。 （ErrorHandling 示例不包括其他可以添加的项目; 但是，可以通过在你的环境中添加项可能已存在的测试此功能。）  

> [!NOTE]
>  可以使用预处理和后处理脚本来执行操作之前或之后应用程序导入、 安装或卸载。 例如，你可能想要使用预处理脚本从 GAC 卸载卸载程序集。 有关详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。  

###### <a name="to-add-an-artifact-to-an-application"></a>将项目添加到应用程序  

1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 若要添加以下类型的项目，右键单击 ErrorHandling 应用程序文件夹，然后依次**添加**。 请注意，当添加 BizTalk 程序集时，它包含的项目也会添加到应用程序中的相应文件夹。  

   -   BizTalk 程序集  

   -   预处理脚本  

   -   后续处理脚本  

   -   资源 （BizTalk 程序集、.NET 程序集、 预处理脚本、 后处理脚本、 文件、 证书、 COM 组件。 BAM 项目、 绑定文件和虚拟目录）  

   -   策略  

   您还可以从应用程序中删除项目。  

###### <a name="to-remove-an-artifact-from-an-application"></a>若要从应用程序中删除项目  

1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 展开包含该项目的文件夹，右键单击该项目，然后单击**删除**。  

   有关配置应用程序的详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。  

#### <a name="4-export-the-application"></a>4.导出应用程序  
 创建 BizTalk 应用程序并根据需要进行修改后，你可以使用中的导出 MSI 文件向导导出该应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 这将生成.msi 文件，稍后可以导入另一个 BizTalk 组，以便重新创建新组中的应用程序。 若要在特定服务器上运行应用程序，您还必须安装它本地从.msi 文件。  

###### <a name="to-export-the-application"></a>若要将应用程序导出  

1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。  

3. 右键单击 BizTalk 应用程序，指向**导出**，然后单击**MSI 文件**。  

4. 上**欢迎使用导出 MSI 文件向导**页上，单击**下一步**。  

5. 上**选择资源**页上，选择要导入.msi 文件，然后单击资源**下一步**。 对于本演练中，可以接受默认值。  

6. 如果系统提示，请在**指定 IIS 主机**页上，键入承载你想要包括，然后单击虚拟目录的计算机的服务器名称**下一步**。 系统将提示您指定的服务器，仅当虚拟目录尚未以前添加到 BizTalk 管理数据库，如已添加到应用程序时或其导入应用程序。  

   > [!NOTE]
   >  没有包含在 ErrorHandling 示例解决方案中任何虚拟目录。  

7. 上**依赖项**页上，查看该应用程序的依存关系，然后单击**下一步**。  

8. 上**目标**页上，在**目标应用程序名**，键入应用程序名称。  

9. 在中**MSI 文件以生成**，键入.msi 文件的完整路径，然后单击**导出**。 例如：C:\MSI\Errorhandling.msi  

    > [!NOTE]
    >  我们建议将.msi 文件存储在安全的文件夹。  

10. 上**摘要**页上，记下此操作，日志文件的位置，然后单击**完成**。  

    在文件系统中，验证你指定的位置中已创建的.msi 文件。  

> [!NOTE]
>  出于安全原因，在应用程序导出过程中不会保留密码从应用程序绑定。 从.msi 文件安装应用程序之后, 将需要重新配置密码，以便对函数应用程序。 密码不会删除，但是，从绑定文件添加到应用程序。  

 有关导出应用程序和项目的详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  

#### <a name="5-import-and-install-the-application"></a>5.导入和安装应用程序  
 下一步是从刚刚生成到 BizTalk 组的.msi 文件导入应用程序并还在本地计算机上安装应用程序。 可以使用导入 MSI 向导和中的安装向导[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来执行此操作。  

> [!NOTE]
>  必须将运行该应用程序组中每台计算机上安装应用程序。 可以双击.msi 文件安装在其他计算机上。  

 你想要迁移应用程序从一个 BizTalk 组到另一个，如每个的时间重复此步骤中的任务时从开发环境迁移到测试环境、 过渡环境，测试环境或到过渡环境生产环境。  

 此时，如果只有一台计算机将在本演练中，你应从 BizTalk 组中删除应用程序。 你应从全局程序集缓存 (GAC) 中删除这些程序集。 这样一来，当您导入应用程序，你将能够验证它已重新创建正确。 在本演练中使用多台计算机，如果您不需要执行这些任务。  

###### <a name="to-delete-the-application-from-the-biztalk-group"></a>从 BizTalk 组中删除应用程序  

1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 右键单击该应用程序，然后单击**删除**。  

###### <a name="to-delete-assemblies-from-the-gac"></a>若要从 GAC 删除程序集  

1. 在文件系统中，导航到 systemdrive%\Windows\assembly。  

2. 右键单击你的解决方案生成的每个程序集文件中，单击**卸载**，然后单击**是**以确认。 例如，与 ErrorHandling 项目相关联的程序集文件是 ErrorHandling.ErrorHandler 和 ErrorHandling.PipelinesAndSchemas。  

    ![从 GAC 删除程序集](../core/media/deleteassembly.gif "DeleteAssembly")  

   现在已准备好将应用程序导入 BizTalk 组。 如果你想要将应用程序导入另一台计算机上运行的 BizTalk 组，.msi 文件必须可从另一台计算机进行访问。  

> [!CAUTION]
>  在安装任何应用程序之前，请确保已从受信任的源接收的.msi 文件。 恶意用户可以在可造成不良影响系统或网络上的.msi 文件中包括代码。 有关详细信息，请参阅[安全性和 Windows 安装程序](../core/security-and-windows-installer.md)。  

###### <a name="to-import-and-install-the-application"></a>若要导入和安装应用程序  

1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的实例的管理控制台[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到想要导入应用程序。 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开**BizTalk 组**。  

3. 右键单击**应用程序**，依次指向**导入**，然后单击**MSI 文件**。  

4. 上**欢迎使用导入向导**页上，在**要导入的 MSI 文件**，键入.msi 文件的完整路径，然后单击**下一步**。 例如：C:\msi\MyApplication.msi  

5. 上**应用程序设置**页上，在**可用的应用程序将引用添加到**，选择要添加的引用，并单击应用程序**下一步**。 如果您在使用 ErrorHandling 示例解决方案，你可以接受默认值。  

    ![将引用添加到应用程序](../core/media/appreferences.gif "AppReferences")  

6. 上**应用程序目标环境设置**页上，确认**\<默认\>** 处于选中状态，然后单击**下一步**。  

7. 上**导入摘要**页上，确认摘要信息是否正确，，然后单击**导入**。  

8. 在导入 MSI 向导的最后一个屏幕上，选择**运行应用程序安装向导以在本地计算机上安装应用程序**，然后单击**完成**。  

    ![从导入向导开始安装](../core/media/startinstallation.gif "StartInstallation")  

9. 上**选择安装文件夹**页上，在**文件夹**，键入 BizTalk 应用程序的安装路径，然后单击**下一步**。  

10. 单击**下一步**接下来的三页以继续安装。  

     Windows 安装程序在本地计算机上安装应用程序。  

11. 上**安装完成**页上，单击**关闭**。  

    有关导入应用程序的详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 有关安装应用程序的详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  

    接下来，你可以确保应用程序已导入和通过验证以下安装：  

-   在管理控制台中的应用程序的文件夹中存在该应用程序和所有项目。  

-   应用程序程序集存在于 GAC 中。  

-   在安装应用程序时指定的路径中存在与该应用程序关联的文件。  

-   应用程序将显示在控件面板中添加或删除程序。  

-   如果已配置应用程序，因此它可以工作，例如通过指定发送和接收端口，现在可以通过右键单击它，然后单击启动应用程序**启动**。 ErrorHandling 示例应用程序未设置才能正常默认情况下，但是，因此除非你已手动配置它，您将无法再启动它。  

-   若要从 BizTalk 组和本地计算机中完全删除应用程序，请按照中的说明[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。  

## <a name="see-also"></a>请参阅  
[了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)