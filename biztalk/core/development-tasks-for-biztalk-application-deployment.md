---
title: "BizTalk 应用程序部署的开发任务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, deploying
- deploying [applications], developing
- applications, tasks
- deploying [applications], warnings
- applications, developing
- developing, tasks
ms.assetid: b441d4f4-122e-4caf-8381-723c6142b0b6
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 237a3f95fa33b8265be9d7af2a55ed14e2bbe408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="development-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署的开发任务
下面的内容介绍将 BizTalk 程序集从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署到 BizTalk 应用程序、完成该应用程序以及准备将其部署到测试环境时所涉及的步骤。 这一部署情况在开发环境中很常见，程序员要在这一环境中开发和调试特定的 BizTalk 业务解决方案。  
  
> [!IMPORTANT]
>  勿在生产计算机上执行本主题中说明的任务。 在开发过程中，开发人员经常需要重新部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的程序集。 若要启用重新部署，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 会对相同或不同应用程序中存在的程序集取消部署、取消绑定、停止并取消登记。 虽然在部署环境中这样做是必要和适当的，但在生产环境中会产生意外和不需要的结果。 另外，为了避免有人尝试在生产计算机上部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的程序集，建议你不要在生产计算机上安装 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
1.  **开发和生成 BizTalk 程序集。** 首先，创建 BizTalk 业务解决方案中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，使用业务流程、 架构、 映射和管道。 在使用该解决方案时，您将它内嵌于一个或多个 BizTalk 程序集中。 有关详细信息，请参阅[开发 BizTalk 服务器应用程序](../core/developing-biztalk-server-applications.md)。 您还开发和生成使您的解决方案生效所需的任何非 BizTalk .NET 程序集。  
  
2.  **设置部署属性。** 当你准备好部署 BizTalk 程序集，设置部署属性上每个[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案中的项目。 除了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 属性（“服务器”、“配置”、“数据库”、“重新部署”、“重新启动主机实例”和“安装到全局程序集缓存”）外，您还可以设置“应用程序名”属性。 该属性指定您将每个程序集部署到的 BizTalk 应用程序。 如果“应用程序名”为空，则程序集将部署到默认的应用程序中。 有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 您必须通过将非 BizTalk .NET 程序集添加到 BizTalk 应用程序，部署这些程序集。 这是一个单独的步骤，在后面的步骤 4 中介绍。  
  
3.  **将 BizTalk 程序集部署到本地计算机上运行的 BizTalk Server。** 你可以通过右键单击部署菜单选项，将 BizTalk 的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案并选择部署命令。 这将在该解决方案中包含的项目中生成 BizTalk 程序集，并且将这些程序集添加到在部署属性中为每个项目定义的 BizTalk 应用程序。 如果尚不存在相应的应用程序，系统将创建它。 这些程序集及其资源（称作“项目”）也部署到组的 BizTalk 管理数据库中，并且可以通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或其他工具查看和管理它们。 有关此步骤的详细信息，请参阅[如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  
  
4.  **添加应用程序才能正常工作所需的项目。** 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，可以轻松地修改应用程序在完成它，例如通过添加和删除的项目，如发送和接收端口、 脚本、 策略、 BizTalk.NET 程序集和等。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。  
  
5.  **分解为多个应用程序项目。** 在开发过程中，出于方便，您可能会将程序集部署到单个应用程序中。 由于许多原因，您可能要将项目分解到多个应用程序中，然后再将它们部署到生产中。 有关将分解应用程序的最佳实践的详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
6.  **解决方案中创建的所有应用程序的.msi 文件并本地安装它们。** 你可以使用导出向导中，可从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 BTSTask 命令行工具创建一个包含每个应用程序的项目的.msi 文件。 有关详细信息，请参阅[导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)。 如果您想要在本地计算机上运行该解决方案并验证该解决方案按预期执行，可以执行另一步骤来通过这些 .msi 文件安装项目。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。 验证该解决方案按预期执行。  
  
7.  **根据需要重新部署 BizTalk 程序集。** 在过程中开发和调试你的 BizTalk 程序集，你可能需要将其重新部署多次。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供简单的机制，用于重新部署。 有关详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)。  
  
8.  **导出绑定文件并将其添加回 （可选） 的应用程序。** 为了在以后更便于将应用程序导入回您的开发环境，以便进行更改或添加，可能需要为每个应用程序都导出绑定，然后将它们添加回应用程序，并且指定绑定的开发目标环境。 以后将应用程序的 .msi 文件导入回开发计算机上的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中时，可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
9. **关闭移交生成每个应用程序的.msi 文件，测试团队**。 完成开发和调试你的 BizTalk 解决方案，可用于导出向导或 BTSTask 生成应用程序的.msi 文件，如之前在步骤 6 中所述。 你应在开发环境中将这些文件导入不同的 BizTalk 组、 安装它们，并验证按预期方式的解决方案正常运行。 你可以然后交给测试团队可用于导入到应用程序的.msi 文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上运行测试，以及关于安装它们中, 所述[BizTalk 应用程序部署测试任务](../core/testing-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)