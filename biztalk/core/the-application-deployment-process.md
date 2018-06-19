---
title: 应用程序部署过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, deploying
- deploying [applications], how to
ms.assetid: 29486c37-6aa7-46fd-a457-916fd235f448
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd88dbb730b31362042e68b3a25c4ccc66531882
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279733"
---
# <a name="the-application-deployment-process"></a>应用程序部署过程
下图说明了在部署 BizTalk 应用程序时涉及的一般步骤。 有关所涉及的应用程序部署开发、 测试、 过渡和生产阶段的任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。  
  
 ![应用程序部署过程](../core/media/appdeploymentprocess.gif "AppDeploymentProcess")  
  
1.  **从 Visual Studio 部署 BizTalk 解决方案中的程序集。** 这将生成程序集，并且将这些程序集以及它们包含的业务流程、管道、架构和映射（称作“项目”）导入本地 BizTalk 管理数据库中。 部署还将它们与您在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的项目属性内指定的 BizTalk 应用程序相关联。 有关说明，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。 在您部署某一解决方案后，可以从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内或通过使用 BTSTask 命令行工具查看和管理已部署的程序集及其项目。 您可以单独管理项目，也可以在应用程序内将项目组合起来一起管理。  
  
2.  **添加和配置项目。** 你可以向该应用程序使用的管理控制台或 BTSTask 添加项目，比如脚本和自述文件。 您还可以通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置项目，例如发送和接收端口、接收位置和业务流程。 有关详细信息，请参阅[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。 另请参阅[管理项目](../core/managing-artifacts.md)。 如果您希望为要导入应用程序的不同环境应用不同的绑定，还可以生成绑定文件并将它们添加到应用程序中。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3.  **导出应用程序置于.msi 文件。** 您可以使用导出 MSI 文件向导或 BTSTask 将应用程序项目导出到某一 .msi 文件中，您将使用该文件将应用程序导入新的 BizTalk 组以及将应用程序安装到将运行它的计算机上。 有关说明，请参阅[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。  
  
4.  **将应用程序导入另一个 BizTalk 组，然后运行它的计算机上安装应用程序。** 您可以使用导入 MSI 向导或 BTSTask 将 BizTalk 应用程序从在第 3 步中创建的 .msi 文件导入其他 BizTalk 组，以便在新组中创建应用程序及其项目。 然后，使用该 .msi 文件在将运行它的计算机上安装应用程序。 必须进行此操作才能运行应用程序。 如果您准备测试该应用程序，则可以将它导入到测试环境下的 BizTalk 组中，然后安装它。 如果您的应用程序可用于过渡或生产，则可以将它导入这些环境之一，然后安装它。 有关说明，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 另请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
5.  **启动应用程序并验证其正常。** 你可以从应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中中, 所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。 中所述，你随后可以测试该应用程序，[测试 BizTalk 应用程序部署的任务](../core/testing-tasks-for-biztalk-application-deployment.md)。  
  
## <a name="see-also"></a>另请参阅  
 [了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)   
 [BizTalk 应用程序是什么？](../core/what-is-a-biztalk-application.md)