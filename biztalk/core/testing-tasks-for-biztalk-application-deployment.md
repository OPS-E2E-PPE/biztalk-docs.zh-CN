---
title: BizTalk 应用程序部署的测试任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], testing
- testing, deploying
- testing, tasks
ms.assetid: fb043755-6d01-4ceb-b189-5a5f286c2b37
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1104e2cc1a25d0c0b91f990c6c8ef5969c2e7c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299017"
---
# <a name="testing-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署的测试任务
以下是部署到用于测试和调试测试环境的 BizTalk 应用程序的项目时所涉及的步骤。  
  
1.  **将.msi 文件复制到你的测试环境。** 如中所述[BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)，当 BizTalk 应用程序时，准备好进行测试，开发人员将应用程序项目导出到某一.msi 文件。 完整的解决方案可能会包含一个或多个 BizTalk 应用程序，因此可能会收到多个要测试的.msi 文件。 可以将.msi 文件复制到测试计算机中，然后下, 一步中所述导入项目从.msi 文件到 BizTalk Server。 此外可以使用.msi 文件安装到要运行它们的计算机上的应用程序。  
  
2.  **从.msi 文件导入应用程序。** 导入向导，可从 BizTalk Server 管理控制台中，可用于导入 BizTalk Server 的当前实例上的应用程序的.msi 文件中的项目。 有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 如果尚不存在指定的应用程序，则导入过程将创建它。 然后，可以查看应用程序，并修改其配置和内容从 BizTalk Server 管理控制台。 可能需要执行此操作，例如，将修改你的测试环境的绑定。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。 如果绑定文件已添加到具有您的测试环境的相应绑定的应用程序，则可以在导入过程中应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3.  **安装应用程序。** 现在可以在你想要运行该应用程序的服务器上安装应用程序。 如果应用程序包含基于文件的项目，您必须安装它或它不起作用。 可以通过双击.msi 文件安装应用程序。 这将安装并注册本地计算机上的应用程序的项目，以便可以运行该应用程序。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
4.  **测试应用程序。** 现在可以测试应用程序。 开发人员修复您发现任何 bug，并向您提供更新后的.msi 文件后，您可以再次执行步骤 1、 2 和 3。  
  
5.  **导出绑定文件并将它们添加回应用程序 （可选）。** 若要使应用程序导入回测试环境在更高版本时如果您需要测试的更改或添加更容易，您可能想要导出应用程序绑定，然后将它们添加回应用程序，指定的测试目标环境绑定。 当您更高版本的应用程序.msi 文件重新导入 BizTalk Server 在测试环境中时，可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
6.  **生成一个.msi 以应用程序部署到过渡环境**。 完成测试您的 BizTalk 应用程序后，可以将其部署到过渡环境中。 若要执行此操作，您使用导出向导来生成新的.msi 文件，如之前在步骤 2 中所述。 你可以然后.msi 文件提交给负责过渡部署的 IT 管理员。 IT 管理员将使用该.msi 文件导入到 BizTalk Server 过渡计算机上的应用程序并将运行它的计算机上安装应用程序，如中所述[BizTalk 应用程序部署的暂存任务](../core/staging-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)