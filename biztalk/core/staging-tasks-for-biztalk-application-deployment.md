---
title: BizTalk 应用程序部署的暂存任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, staging
- deploying [applications], staging
- applications, deploying
- deploying [applications], tasks
ms.assetid: de60eddb-da13-412a-94f9-331387b5930e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e221e34b4e493fdb5ba112ad389d298accde2d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398934"
---
# <a name="staging-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署的暂存任务
以下是部署到过渡环境的 BizTalk 应用程序时所涉及的步骤。  
  
1.  **将.msi 文件复制到过渡环境。** 如中所述[BizTalk 应用程序部署的测试任务](../core/testing-tasks-for-biztalk-application-deployment.md)，当的 BizTalk 应用程序完成测试并准备好进行过渡，测试团队提供了一个或多个.msi 文件以便临时存储。 （完整的解决方案可能包含一个或多个 BizTalk 应用程序，因此可能会收到阶段到多个.msi 文件。）可以将此.msi 文件复制到过渡计算机上，然后下, 一步中所述的 BizTalk 应用程序从.msi 文件导入在过渡环境中的 BizTalk 组。 此外可以使用该.msi 文件安装到要运行该应用程序的计算机上的应用程序。  
  
2.  **从.msi 文件导入应用程序。** 导入向导，可从 BizTalk Server 管理控制台中，可用于导入到过渡环境中的 BizTalk 组的应用程序的.msi 文件的内容。 有关详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 如果尚不存在指定的应用程序，导入.msi 文件将创建它。 然后，可以查看应用程序，并修改其配置和内容从 BizTalk Server 管理控制台。 您可能要执行此操作，例如，需要修改过渡环境的绑定。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。 如果绑定文件已添加到具有过渡环境的相应绑定的应用程序，则可以在导入过程中应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3.  **导出绑定文件并将它们添加回应用程序 （可选）。** 若要使应用程序导入回过渡环境在更高版本时如果应用程序所做的更改或添加更容易，可能想要导出应用程序绑定，然后将它们添加回应用程序中，指定临时目标绑定的环境。 当您更高版本的应用程序.msi 文件重新导入 BizTalk Server 在过渡环境中时，可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
4.  **安装应用程序。** 现在可以在所有将运行该应用程序的计算机上安装应用程序。 可以通过使用安装向导或只需双击该.msi 文件安装应用程序。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
5.  **测试应用程序以验证配置和绑定。** 现在可以测试应用程序以确保它按预期在过渡环境中正常运行。 您或开发人员进行任何所需的更改后，你可以再次执行步骤 1 至 4。  
  
6.  **生成一个.msi 以应用程序部署到生产环境**。 一旦完成了配置 BizTalk 应用程序的生产环境并验证配置后，可以将其部署到生产环境中。 若要执行此操作，您使用导出向导来生成新的.msi 文件，如中所述[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。 你可以然后.msi 文件提交给负责生产部署的 IT 管理员。 IT 管理员将使用该.msi 文件将在生产计算机上导入 BizTalk Server 应用程序，以及它的计算机上安装将运行它，如中所述[部署BizTalk应用程序的生产任务](../core/production-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)