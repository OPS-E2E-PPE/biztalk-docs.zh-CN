---
title: 部署应用程序的最佳做法 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53852303-d368-4f9e-b4e2-f5918f65000b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa55a240669ab9369dd7a1862d3fda055f577edd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010702"
---
# <a name="best-practices-for-deploying-an-application"></a>部署应用程序的最佳做法
本主题列出应遵循部署 BizTalk 应用程序的最佳做法。  
  
## <a name="deploying-a-biztalk-application"></a>部署 BizTalk 应用程序  
 **文档应用程序部署过程**  
  
-   请确保，在应用程序部署中使用的所有过程都记录在深度，因此你可以如何部署已执行并且在将知道如何进一步部署或取消部署的记录。 不编写脚本的任何内容应记录详细步骤。 这应包括记录对外部系统和第三方组件的部署的任何更改。  
  
 **脚本应用程序部署**  
  
-   尽可能脚本尽可能多的应用程序部署步骤。 脚本在部署过程中减少人为错误的风险。  
  
## <a name="creating-a-biztalk-application"></a>创建 BizTalk 应用程序  
 **编写 BizTalk 应用程序和.msi 文件创建的脚本**  
  
-   BtsTask.exe 可用来编写 BizTalk 应用程序创建的脚本。 如果应用程序的创建已编写脚本，然后包可以自动生成的生成服务器上使用一个自动化的过程。 有关脚本创建的应用程序的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。
  
## <a name="deploying-a-biztalk-assembly"></a>部署 BizTalk 程序集  
 **永远不会部署在生产计算机上的从 Visual Studio 程序集**  
  
-   在开发过程中，开发人员必须通常重新部署 Visual Studio 中的程序集。 若要启用重新部署，Visual Studio 可能会取消部署、 取消绑定、 停止和中取消包含在程序集的项目。 虽然在部署环境中这样做是必要和适当的，但在生产环境中会产生意外和不需要的结果。 鉴于此原因，以及有关防止任何人都部署在生产计算机上的从 Visual Studio 程序集，我们建议你永远不会在生产计算机上安装 Visual Studio。  
  
-   此外，永远不会对生产数据库从引用运行 Visual Studio 的计算机。  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a>将项目添加到 BizTalk 应用程序  
 **分组在一起在单个应用程序的相关的项目**  
  
-   尽可能将相关项目放在同一个 BizTalk 应用程序中。 这样可以将各个项目作为单一实体进行管理和部署，从而更易于管理。 可以将支持同一业务流程的项目或执行类似功能的项目分组到一个应用程序中。  
  
 **部署在单独的应用程序中的共享的项目**  
  
-   如果某些项目将由两个或多个应用程序共享，则应将这些共享项目部署在一个单独的应用程序中。 例如，如果两个应用程序共享一个架构，应将该架构部署在一个单独的应用程序中。 我们建议这是因为 BizTalk 组中的只有一个项目可以具有单个本地唯一标识符 (LUID)。 LUID 组成的项目名称和可选的其他特性。 如果你在一个应用程序，包括项目，然后创建从另一个应用程序对它的引用，当你停止包含项目的应用程序引用的应用程序可能未正常工作。  
  
     此最佳实践适用于所有项目类型，但文件除外（比如 Readme 文件和脚本，它们是以文件类型的项目添加到应用程序中的）。 这是因为可以在 BizTalk 组中部署具有相同名称的多个文件项目。 因此，您可以在两个或多个应用程序中使用具有相同名称的文件。 在这种情况下，停止一个应用程序不会影响其他应用程序。 有关添加文件项目的详细信息，请参阅[如何将文件添加到应用程序](../core/how-to-add-a-file-to-an-application.md)。  
  
 **部署单独的应用程序中的共享的 Web 站点**  
  
-   如果某个网站将由多个业务解决方案共享，应将该网站部署在一个单独的应用程序中。 这是因为在卸载某个 BizTalk 应用程序时，作为该应用程序一部分的任何网站的虚拟目录也会被删除，尽管该网站正在运行。 如果该网站与另一个业务解决方案共享，则会导致这个业务解决方案不能正常工作。  
  
 **部署在单独的应用程序中的共享的策略**  
  
-   如果某个策略将由两个或多个应用程序使用，应将该策略部署在一个单独的应用程序中，而不是创建从一个应用程序到另一个应用程序的引用。 这是因为当其中一个应用程序停止时，会取消部署其策略。 如果您停止一个应用程序，而该应用程序包含另一个程序所使用的策略，则该策略将不能在另一个应用程序中起作用。  
  
 **部署在单独的应用程序中的共享的证书**  
  
-   如果某个证书由两个或多个应用程序的发送端口或接收位置使用，应将该证书部署在一个单独的应用程序中，然后从需要使用该证书的应用程序中引用该程序。 这是因为 BizTalk 组中的只有一个项目可以具有单个 LUID，因此你将不能导入两个不同的应用程序中的相同证书。 如果尝试导入两个使用同一证书的应用程序，则第一个导入将会成功，而第二个导入将会失败。 在这种情况下，使用“覆盖”导入选项并不能解决问题，因为您要覆盖的现有证书包含在另一个应用程序中。  
  
## <a name="exporting-and-importing-a-biztalk-application"></a>导出和导入 BizTalk 应用程序  
 **在部署大型.msi 文件时，你可能需要增加 BizTalk Server 用于部署应用程序的 COM + 组件的默认事务超时**  
  
-   如果你尝试部署.msi 文件非常大 (超过 100 MB)，然后应用程序可能不会部署中的 COM + 组件在应用程序部署过程中由 BizTalk Server 使用的默认事务超时时间。 如果事务关联，这些 COM + 组件时扩展之前完成部署，然后部署将失败。 如果你要部署的非常大的.msi 文件，则可以考虑采用其中一种方法，以缓解此问题：  
  
-   部署多个较小的.msi 文件，而不是一个大型的.msi 文件。  
  
    -   增加 3000 秒与 Microsoft.BizTalk.ApplicationDeployment.Group 和中的组件服务管理界面的 Microsoft.BizTalk.Deployment.DeployerComponent 组件相关联的默认事务的超时。 这些组件分别属于 Microsoft.BizTalk.ApplicationDeployment.Engine 和 Microsoft.Biztalk.Deployment COM + 应用程序。 有关详细信息，请参阅 Microsoft 知识库文章 287499，[如何更改事务超时值 MTS 或 COM +](https://support.microsoft.com/help/287499/how-to-change-the-transaction-time-out-value-for-mts-or-com)。  
  
 **防止从被覆盖的绑定**  
  
-   如果您不希望用导出的应用程序中的绑定覆盖导入 .msi 文件的应用程序中的绑定，请不要在导出操作中选择将该绑定文件作为资源导出。  
  
 **确保.msi 文件是安全的**  
  
-   .Msi 文件可能包含敏感数据。 请确保采取措施来帮助确保该文件是安全的。 有关.msi 文件安全性的详细信息，请参阅[安全和 Windows Installer](../core/security-and-windows-installer.md)。  
  
 **确保绑定文件是安全的**  
  
-   绑定文件可能包含敏感数据。 请确保采取措施来帮助确保该文件是安全的。  
  
 **在没有的项目进行更改时，将导出计划**  
  
-   当用户是不可能会对项目进行更改的时间计划导出操作。 这可能很重要，因为如果用户正在修改基于数据库的项目、 虚拟目录、 证书或策略正在某一导出操作时，所做的更改将不会反映在导出的.msi 文件。  
  
## <a name="importing-a-biztalk-application"></a>导入 BizTalk 应用程序  
 **.Msi 文件导入的脚本**  
  
-   BtsTask.exe 可以用于脚本导入现有 BizTalk.msi 文件。 有关脚本.msi 文件导入的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。 
  
    > [!NOTE]  
    >  白皮书也适用于 BizTalk Server。  
  
-   你可以添加脚本以预处理或后续处理脚本运行。 但是，你将需要在你的脚本来检查环境变量，以确定脚本执行中 （导入、 安装或卸载） 的上下文中包括逻辑并进行相应处理。 有关使用前期和后期处理脚本的详细信息，请参阅[使用自定义应用程序部署到的前期和后期处理脚本](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。 
  
 **验证引用的项目存在**  
  
-   当您要导入应用程序具有对另一个应用程序的引用时，BizTalk Server 验证引用的应用程序存在。 但是，它不验证引用的应用程序中包含你的应用程序在其具有依赖关系的项目。 当你导入具有其他应用程序中的项目对依赖关系的应用程序时，我们建议你验证引用的应用程序包含所需的项目。  
  
 **从.msi 文件导入，不能在全局程序集缓存中存储已更改的程序集**  
  
-   若要更新应用程序中的项目，从导入的更改或更新的项目.msi 文件到应用程序。 如果不使用.msi 文件以导入项目，你将需要通过在全局程序集缓存中存储的已更改的程序集更新组中的所有服务器。  
  
 **处理组的主机更新总的服务器的子集**  
  
-   在更新应用程序中的项目时，你通常必须更新 BizTalk 组中的所有服务器。 但是，如果你使用处理组的主机，你仅需要更新的组中的总服务器子集。  
  
 **如果导入操作超时时，拆分应用程序置于其他.msi 文件**  
  
-   导入操作将超时，如果它超过 3,600 秒中持续时间。 如果你尝试导入.msi 文件，并且在操作超时时，你应将应用程序分成多个.msi 文件的内容划分通过重新导出应用程序并选择要导出项目的子集。 有关导出到.msi 文件的应用程序的详细信息，请参阅[导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。