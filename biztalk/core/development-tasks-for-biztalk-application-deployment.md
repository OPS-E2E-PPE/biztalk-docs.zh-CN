---
title: BizTalk 应用程序部署的开发任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, deploying
- deploying [applications], developing
- applications, tasks
- deploying [applications], warnings
- applications, developing
- developing, tasks
ms.assetid: b441d4f4-122e-4caf-8381-723c6142b0b6
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b935f2aee0687a12c7b4519b2f44abf90a75e8e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530870"
---
# <a name="development-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署的开发任务
以下是部署中的 BizTalk 程序集时所涉及的步骤[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序中，完成该应用程序，以及准备将其部署到测试环境。 此部署方案中很常见的开发环境，其中一名程序员是开发和调试特定的 BizTalk 业务解决方案中。  
  
> [!IMPORTANT]
>  永远不应执行本主题中所述，在生产计算机上的任务。 在开发过程中，开发人员经常需要重新部署程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 若要启用重新部署，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]可能取消部署、 取消绑定、 停止和取消登记在相同或不同应用程序中存在的程序集。 虽然这是必要和适当的开发环境中，它可能会导致意外后果导致生产环境中。 此外，为了避免有人尝试从部署程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的生产计算机上，我们建议您不要安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的生产计算机上。  
  
1. **开发和生成 BizTalk 程序集。** 通过创建您的 BizTalk 业务解决方案中开始[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，使用业务流程、 架构、 映射和管道。 在使用该解决方案，则它生成到一个或多个 BizTalk 程序集。 有关详细信息，请参阅[开发 BizTalk Server 应用程序](../core/developing-biztalk-server-applications.md)。 您还开发和生成所需的您的解决方案的任何非 BizTalk.NET 程序集。  
  
2. **设置部署属性。** 当您准备部署 BizTalk 程序集，每个设置部署属性[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案中的项目。 除了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]属性 （服务器、 配置、 数据库、 重新部署、 重新启动主机实例和安装到全局程序集缓存），还可以设置应用程序名称属性。 此属性指定每个程序集部署到的 BizTalk 应用程序。 如果应用程序名称为空，该程序集将部署到默认应用程序。 有关详细信息，请参阅[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 通过将它们添加到 BizTalk 应用程序，必须部署非 BizTalk.NET 程序集。 这是一个单独的步骤，更高版本，在步骤 4 中所述。  
  
3. **将 BizTalk 程序集部署到本地计算机上运行的 BizTalk Server。** 可以通过右键单击部署 BizTalk 程序集，从菜单选项，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]解决方案并选择部署命令。 这将生成解决方案中包含的项目中的 BizTalk 程序集并将它们添加到每个项目的部署属性中定义的 BizTalk 应用程序。 如果应用程序不存在，则创建它。 程序集和其资源 （称为"项目"） 也部署到 BizTalk 管理数据库对于组，并且可以查看和使用管理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或其他工具。 有关此步骤的详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  
  
4. **添加所需的应用程序才能正常工作的项目。** 从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，可以轻松地修改应用程序来完成它，例如通过添加和删除项目，例如发送和接收端口、 脚本、 策略、 非 BizTalk.NET 程序集，等等。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。  
  
5. **将项目分解到多个应用程序。** 在开发过程中，你可能已部署您的程序集到单一应用程序中为方便起见。 由于各种原因，你可能想要部署到生产环境之前，将项目分解到多个应用程序。 有关分解应用程序的最佳实践的详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
6. **在解决方案中创建的所有应用程序的.msi 文件并本地安装它们。** 您可以使用导出向导，可从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 BTSTask 命令行工具来创建包含每个应用程序的项目的.msi 文件。 有关详细信息，请参阅[导出 BizTalk 应用程序、 绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)。 可能需要从.msi 文件安装项目，如果你想要在本地计算机上运行该解决方案并验证按预期方式工作，额外的步骤。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。 验证该解决方案可以按照预期方式。  
  
7. **根据需要重新部署 BizTalk 程序集。** 在过程中开发和调试您的 BizTalk 程序集，可能需要多次重新部署它们。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供用于重新部署一个简单的机制。 有关详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)。  
  
8. **导出绑定文件并将它们添加回应用程序 （可选）。** 若要更加轻松地返回到你的开发环境的应用程序导入在以后要进行更改或添加，则可能需要以导出每个应用程序绑定，然后将它们添加回应用程序中，指定开发目标绑定的环境。 当您更高版本应用程序.msi 文件导入回[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在开发计算机，您可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
9. **生成每个应用程序的.msi 文件移交，关闭到您的测试团队**。 完成开发和调试您的 BizTalk 解决方案后，你可以使用导出向导或 BTSTask 生成应用程序.msi 文件，如之前在步骤 6 中所述。 应在开发环境中将这些文件导入其他 BizTalk 组、 安装它们，而且然后验证解决方案按预期方式。 您可以然后移交给您的测试团队的.msi 文件，它们可用于导入到应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]测试计算机上运行，以及关于安装它们，如中所述[BizTalk 应用程序部署的测试任务](../core/testing-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)