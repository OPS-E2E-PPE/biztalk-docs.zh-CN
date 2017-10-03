---
title: "BizTalk 应用程序部署的生产任务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying [applications], assemblies
- applications, deploying
- assemblies, warnings
- deploying [applications], warnings
- deploying [applications], tasks
- assemblies, deploying
- deploying [applications], production
ms.assetid: e77d8921-42ef-4c51-aab2-66c086aad955
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 260afd4522d28bdd2a485a1a11edc045c7fde880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="production-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署的生产任务
以下是将 BizTalk 应用程序部署到生产环境时所涉及的步骤。  
  
> [!IMPORTANT]
>  切勿将 Visual Studio 中的程序集部署在生产计算机上。 若要启用重新部署，Visual Studio 会对相同或不同应用程序中存在的程序集取消部署、取消绑定、停止并取消登记。 虽然在部署环境中这样做是必要和适当的，但在生产环境中会产生意外和不需要的结果。 另外，为了避免有人尝试在生产计算机上部署 Visual Studio 中的程序集，建议您不要在生产计算机上安装 Visual Studio。  
  
> [!IMPORTANT]
>  在生产环境中更新其他应用程序依赖的应用程序时一定要小心，以免中断其他正在运行的应用程序。 有关详细信息，请参阅[更新应用程序的重要注意事项](../core/important-considerations-for-updating-applications.md)。  
  
1.  **.Msi 文件复制到生产环境。** 中所述[测试 BizTalk 应用程序部署的任务](../core/testing-tasks-for-biztalk-application-deployment.md)，当的 BizTalk 应用程序已完成过渡，并可供生产，IT 管理员，负责暂存配置提供的.msi 文件用于生产部署。 可以将此 .msi 文件复制到生产计算机中，然后按下一步骤所述，从 .msi 文件中将 BizTalk 应用程序导入 BizTalk Server。 还可使用此 .msi 文件将此应用程序安装到要运行此应用程序的计算机上。 一套完整的 BizTalk 解决方案会包含一个或多个应用程序，因此您可能会收到多个要部署的 .msi 文件。  
  
2.  **从.msi 文件导入应用程序。** 可以使用导入向导（可通过 BizTalk Server 管理控制台访问）将 .msi 文件的内容导入 BizTalk Server 当前实例上的某个应用程序中。 有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 如果指定的应用程序已不存在，则导入 .msi 文件时会创建它。 然后，可以通过管理控制台查看此应用程序并修改其配置和内容。 例如，您可能需要执行此操作以配置证书和终结点（如 URL）以及针对生产环境修改绑定。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。 如果已将绑定文件添加到具有适合生产环境的绑定的应用程序，则导入过程中可以应用绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3.  **安装并启动应用程序。** 现在，您可以在所有将运行此应用程序的计算机上安装此应用程序，并在管理控制台中启动此应用程序。 可以通过双击 .msi 文件来安装此应用程序。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
4.  **导出绑定文件并将其添加回应用程序 （可选）。** 为使稍后将应用程序导入回生产环境以部署更改或添加内容的过程更方便，您最好导出应用程序绑定，再将其添加回应用程序，然后为绑定指定一个生产目标环境。 在随后将此应用程序 .msi 文件导入回生产环境中的 BizTalk Server 时，可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
5.  **导出到新的.msi 文件 （可选） 应用程序。** 如果进行配置更改或添加应用程序，并希望所做更改会反映在.msi 文件 （例如将应用部署到其他 BizTalk 组） 中, 所述，你可以导出新的.msi 文件，[如何导出BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)