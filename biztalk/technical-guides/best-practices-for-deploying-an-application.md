---
title: 将应用程序部署的最佳实践 |Microsoft Docs
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
ms.openlocfilehash: cb068cc72a053b52d4bd891d87d7059868cbf18d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401248"
---
# <a name="best-practices-for-deploying-an-application"></a>部署应用程序的最佳做法
本主题列出了在部署 BizTalk 应用程序应遵循的最佳做法。  

## <a name="deploying-a-biztalk-application"></a>部署 BizTalk 应用程序  
 **文档应用程序部署过程**  

- 请确保，在应用程序部署中使用的所有过程都记录在深度，因此必须如何部署已执行并且将知道如何进一步部署或取消部署的记录。 不编写脚本的任何内容应记录了详细步骤。 这应包括记录对外部系统和第三方组件的部署的任何更改。  

  **脚本应用程序部署**  

- 脚本尽可能多的应用程序部署步骤。 脚本在部署过程中减少人为错误的风险。  

## <a name="creating-a-biztalk-application"></a>创建 BizTalk 应用程序  
 **编写 BizTalk 应用程序和.msi 文件创建的脚本**  

-   可以使用 BtsTask.exe 编写脚本的 BizTalk 应用程序创建。 如果创建的应用程序编写的脚本，然后包可以自动生成的生成服务器上使用自动化的过程。 有关应用程序的创建脚本的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。

## <a name="deploying-a-biztalk-assembly"></a>部署 BizTalk 程序集  
 **永远不会部署 Visual Studio 中的生产计算机上的程序集**  

-   在开发过程中，开发人员必须经常重新部署程序集从 Visual Studio。 若要启用重新部署，Visual Studio 可能会取消部署、 取消绑定、 停止和取消登记项目包含在程序集。 虽然这是必要和适当的开发环境中，它可能会导致意外后果导致生产环境中。 出于此原因，也并防止任何人都部署 Visual Studio 中的生产计算机上的程序集，我们建议您永远不会在生产计算机上安装 Visual Studio。  

-   此外，永远不会引用生产数据库从运行 Visual Studio 的计算机。  

## <a name="adding-artifacts-to-a-biztalk-application"></a>将项目添加到 BizTalk 应用程序  
 **分组在一起的单个应用程序的相关的项目**  

- 尽可能多地，将相关的项目放在同一 BizTalk 应用程序。 这允许您管理和部署项目作为单个实体，从而更易于管理。 支持同一业务流程的项目或项目，在单个应用程序中执行相似的功能，可以进行分组。  

  **部署单独的应用程序中的共享的项目**  

- 如果项目将两个或多个应用程序共享，将这些共享的项目部署到单独的应用程序。 例如，如果两个应用程序共享一个架构，则将该架构部署在单独的应用程序中。 我们建议这是因为 BizTalk 组中的只能有一个项目只能有单个本地唯一标识符 (LUID)。 LUID 包括的项目名称和可选的其他属性。 如果您在一个应用程序中包括了某个项目，然后创建从另一个应用程序对它的引用，引用的应用程序可能无法正确运行时停止应用程序包含该项目。  

   此最佳实践适用于所有项目类型，如自述文件和脚本，以添加到应用程序作为文件类型的项目的文件除外。 这是因为可在 BizTalk 组中部署多个具有相同名称的文件项目。 因此，您可以使用两个或多个应用程序中具有相同名称的文件。 在这种情况下，停止一个应用程序不会影响其他应用程序。 有关添加文件项目的详细信息，请参阅[如何将文件添加到应用程序](../core/how-to-add-a-file-to-an-application.md)。  

  **部署单独的应用程序中的共享的 Web 站点**  

- 如果网站将由多个业务解决方案共享，将网站部署在单独的应用程序。 这是因为在卸载 BizTalk 应用程序时，会删除属于该应用程序的任何网站的虚拟目录，即使该网站正在运行。 如果网站上与另一个业务解决方案共享，另一种业务解决方案将不再正常工作结果。  

  **部署单独的应用程序中的共享的策略**  

- 如果策略由两个或多个应用程序，应将其部署在单独的应用程序，而不是从到另一个应用程序创建的引用。 这是因为当停止应用程序时，会取消部署其策略。 如果停止包括由其他应用程序的策略的应用程序，该策略将在任一应用程序不再起作用。  

  **部署在单独的应用程序中的共享的证书**  

- 如果证书由发送端口或接收位置在两个或多个应用程序中，应将不同的应用程序，该证书部署，然后从需要使用证书的应用程序中引用此应用程序。 这是因为 BizTalk 组中的只能有一个项目可以有单一的 LUID，因此你将不能导入两个不同的应用程序中的相同证书。 如果你尝试导入每个使用相同的证书的两个应用程序，第一个导入将成功，并且第二个将不会。 在这种情况下，使用覆盖导入选项未更正问题，如你想要覆盖现有证书包含在另一个应用程序。  

## <a name="exporting-and-importing-a-biztalk-application"></a>导出和导入 BizTalk 应用程序  
 **在部署大型.msi 文件时，可能需要增加的 BizTalk Server 用于部署应用程序的 COM + 组件的默认事务超时值**  

- 如果你尝试部署的.msi 文件非常大 (超过 100 MB)，则不可能的 BizTalk Server 在应用程序部署期间使用的 COM + 组件的默认事务超时时间内部署应用程序。 如果在部署完成之前，通过这些 COM + 组件时间扩展相关联的事务，然后部署将失败。 如果要部署的非常大的.msi 文件，则应考虑采用其中一种方法，以缓解此问题：  

- 部署多个较小的.msi 文件，而不是一个大型的.msi 文件。  

  -   增加与 Microsoft.BizTalk.ApplicationDeployment.Group 和 Microsoft.BizTalk.Deployment.DeployerComponent 组件中的组件服务管理接口相关联的 3000 秒的默认事务超时。 这些组件分别属于 Microsoft.BizTalk.ApplicationDeployment.Engine 和 Microsoft.Biztalk.Deployment COM + 应用程序。 有关详细信息，请参阅 Microsoft 知识库文章 287499，[如何更改用于 MTS 或 COM + 事务超时值](https://support.microsoft.com/help/287499/how-to-change-the-transaction-time-out-value-for-mts-or-com)。  

  **防止覆盖绑定**  

- 如果不希望要导出到其中导入.msi 文件的应用程序中的绑定覆盖应用程序中的绑定，然后应作为资源导出导出操作期间不选择绑定文件。  

  **确保安全的.msi 文件**  

- 某一.msi 文件可能包含敏感数据。 请务必采取步骤来帮助确保文件安全。 .Msi 文件安全性的详细信息，请参阅[安全性和 Windows 安装程序](../core/security-and-windows-installer.md)。  

  **确保该绑定文件是安全**  

- 绑定文件可能包含敏感数据。 请务必采取步骤来帮助确保文件安全。  

  **没有人对项目进行更改时，将导出的计划**  

- 在用户不可能对项目进行更改的时间内计划导出操作。 这可以是重要，因为如果某个用户正在修改基于数据库的项目、 虚拟目录、 证书或策略，导出操作正在进行时，所做的更改将不会反映在导出的.msi 文件中。  

## <a name="importing-a-biztalk-application"></a>导入 BizTalk 应用程序  
 **导入的.msi 文件的脚本**  

- 可以使用 BtsTask.exe 编写的现有 BizTalk.msi 文件导入的脚本。 有关脚本导入.msi 文件的详细信息，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。 

  > [!NOTE]  
  >  白皮书也适用于 BizTalk Server。  

- 可以添加要预处理或后处理脚本以运行脚本。 但是，必须在您的脚本，检查环境变量，以确定脚本正在执行中 （导入、 安装或卸载） 的上下文中包含逻辑并相应地处理。 有关使用预处理和后处理脚本的详细信息，请参阅[使用预处理和后处理脚本自定义应用程序部署到](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)。 

  **验证引用的项目存在**  

- 当您要导入的应用程序具有另一个应用程序的引用时，BizTalk Server 将验证引用的应用程序存在。 但是，它不验证引用的应用程序中包含你的应用程序在其具有依赖关系的项目。 导入到项目的依赖项具有另一个应用程序中的应用程序时，我们建议你验证引用的应用程序包含所需的项目。  

  **从.msi 文件导入，不能在全局程序集缓存中存储更改的程序集**  

- 若要更新的应用程序中的项目，从导入的更改或更新项目的.msi 文件到应用程序。 如果不使用某一.msi 文件导入项目，您需要通过将更改的程序集存储在全局程序集缓存中更新组中的所有服务器。  

  **主机组进行处理来更新服务器总数的子集**  

- 当更新应用程序中的项目时，通常情况下必须更新 BizTalk 组中的所有服务器。 但是，如果你使用主机组进行处理，只需要更新组中的服务器总数的子集。  

  **如果导入操作超时，拆分到多个.msi 文件的应用程序**  

- 导入操作将超时，如果超过 3,600 秒的持续时间。 如果你尝试导入的.msi 文件，并且在操作超时，应通过重新导出该应用程序，并选择要导出项目的一个子集来划分到多个.msi 文件的应用程序的内容。 有关导出到.msi 文件的应用程序的详细信息，请参阅[导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。
