---
title: 应用程序部署过程 |Microsoft Docs
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
ms.openlocfilehash: 63f7861a75c091ac5a5203b888df5a1d75654f08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298985"
---
# <a name="the-application-deployment-process"></a>应用程序部署过程
下图描绘了在部署 BizTalk 应用程序所涉及的常规步骤。 有关在应用程序部署的开发、 测试、 过渡和生产阶段所涉及的任务的详细信息，请参阅[应用程序部署任务](../core/application-deployment-tasks.md)。  
  
 ![应用程序部署过程](../core/media/appdeploymentprocess.gif "AppDeploymentProcess")  
  
1. **从 Visual Studio 部署 BizTalk 解决方案中的程序集。** 此软件生成程序集和导入这些，以及业务流程、 管道、 架构和映射到本地 BizTalk 管理数据库包含 （称作"项目"）。 部署还将它们与关联的 BizTalk 应用程序项目属性内指定[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 有关说明，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。 部署解决方案后，可以查看并管理已部署的程序集及其项目内[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或通过使用 BTSTask 命令行工具。 你可以管理的项目单独或一起，在应用程序中进行分组。  
  
2. **添加和配置项目。** 可以将项目，如脚本和自述文件添加到应用程序通过使用管理控制台或 BTSTask。 你还可以配置项目，例如发送和接收端口、 接收位置和业务流程使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关详细信息，请参阅[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)。 另请参阅[管理项目](../core/managing-artifacts.md)。 您还可以生成绑定文件并将其添加到应用程序中，如果你想要应用于不同的环境可能会在其中导入应用程序不同的绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3. **导出到.msi 文件的应用程序。** 可以使用导出 MSI 文件向导或 BTSTask 将导出到.msi 文件将用于该应用程序导入新的 BizTalk 组，以及将运行它的计算机上安装应用程序的应用程序项目。 有关说明，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
4. **将应用程序导入其他 BizTalk 组，并将运行它的计算机上安装应用程序。** 可以使用导入 MSI 向导或 BTSTask 从步骤 3 中创建到其他 BizTalk 组，以便在新组中创建应用程序及其项目的.msi 文件导入 BizTalk 应用程序。 然后使用该.msi 文件将运行它的计算机上安装应用程序。 应用程序可以运行之前必须执行此操作。 如果你已准备好测试应用程序，可以将其导入在测试环境中的 BizTalk 组，并安装它。 如果应用程序是用于过渡或生产准备就绪，可以将其导入其中一个环境并安装它。 有关说明，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 另请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
5. **启动应用程序并验证它正常。** 你可以开始从应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，如中所述[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。 你随后可以测试该应用程序，如中所述[BizTalk 应用程序部署的测试任务](../core/testing-tasks-for-biztalk-application-deployment.md)。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)   
 [BizTalk 应用程序概述](../core/what-is-a-biztalk-application.md)