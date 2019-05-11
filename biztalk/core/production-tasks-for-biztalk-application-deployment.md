---
title: BizTalk 应用程序部署的生产任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a901028369a0ccde83b4260eacd6dd3784c7b4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396962"
---
# <a name="production-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署的生产任务
以下是部署到生产环境的 BizTalk 应用程序时所涉及的步骤。  
  
> [!IMPORTANT]
>  绝不应该将部署的生产计算机上从 Visual Studio 的程序集。 若要启用重新部署，Visual Studio 可能会取消部署、 取消绑定、 停止和取消登记在相同或不同应用程序中存在的程序集。 虽然这是必要和适当的开发环境中，它可能会导致意外后果导致生产环境中。 此外，为了避免有人尝试部署的生产计算机上的程序集从 Visual Studio 的可能性，建议您不要在生产计算机上安装 Visual Studio。  
  
> [!IMPORTANT]
>  更新应用程序的其他应用程序依赖于在生产环境中，以使不会中断其他正在运行的应用程序时要小心。 有关详细信息，请参阅[更新应用程序的重要注意事项](../core/important-considerations-for-updating-applications.md)。  
  
1.  **将.msi 文件复制到生产环境。** 如中所述[BizTalk 应用程序部署的测试任务](../core/testing-tasks-for-biztalk-application-deployment.md)，当的 BizTalk 应用程序完成过渡并准备好生产，负责过渡配置的 IT 管理员提供的.msi 文件用于生产部署。 可以将此.msi 文件复制到你的生产计算机上，然后下, 一步中所述的 BizTalk 应用程序从.msi 文件导入 BizTalk Server。 此外可以使用该.msi 文件安装到要运行该应用程序的计算机上的应用程序。 完整的 BizTalk 解决方案可以包含一个或多个应用程序，因此可能会收到多个要部署的.msi 文件。  
  
2.  **从.msi 文件导入应用程序。** 导入向导，可从 BizTalk Server 管理控制台中，可用于导入 BizTalk Server 的当前实例上的应用程序的.msi 文件的内容。 有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 如果尚不存在指定的应用程序，导入.msi 文件将创建它。 然后，可以查看应用程序，并修改其配置和管理控制台中的内容。 您可能需要为此，请为例，来配置证书和终结点，例如 Url，以及修改你的生产环境的绑定。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。 如果绑定文件已添加到具有生产环境的相应绑定的应用程序，则可以在导入过程中应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3.  **安装并启动应用程序。** 现在可以在所有将运行该应用程序并在管理控制台中启动应用程序的计算机上安装应用程序。 可以通过双击.msi 文件安装应用程序。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
4.  **导出绑定文件并将它们添加回应用程序 （可选）。** 若要更加轻松地返回到生产环境的应用程序导入在更高版本时，若要部署的更改或添加，可能想要导出应用程序绑定，然后将它们添加回应用程序中，指定的生产目标环境绑定。 当您更高版本应用程序.msi 文件导入回生产环境中的 BizTalk Server 时，可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
5.  **应用程序导出到新的.msi 文件 （可选）。** 如果进行配置更改或添加到应用程序，并希望所做更改会反映在.msi 文件中 （例如应用程序部署到其他 BizTalk 组），您可以导出新的.msi 文件，如中所述[如何导出BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)