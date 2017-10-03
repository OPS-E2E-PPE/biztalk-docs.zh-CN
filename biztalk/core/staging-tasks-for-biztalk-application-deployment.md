---
title: "BizTalk 应用程序部署的暂存任务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, staging
- deploying [applications], staging
- applications, deploying
- deploying [applications], tasks
ms.assetid: de60eddb-da13-412a-94f9-331387b5930e
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f03d0cfd5db587a84a080d5963d6696e123ef2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="staging-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署的暂存任务
以下是将 BizTalk 应用程序部署到过渡环境中时所涉及的步骤。  
  
1.  **.Msi 文件复制到过渡环境。** 中所述[测试 BizTalk 应用程序部署的任务](../core/testing-tasks-for-biztalk-application-deployment.md)，当的 BizTalk 应用程序已完成测试，并且处于准备好临时存储，测试团队提供了一个或多个.msi 文件用于过渡。 （一套完整的解决方案可能会包含一个或多个 BizTalk 应用程序，因此您可能会收到多个要过渡的 .msi 文件。）您可以将此 .msi 文件复制到过渡计算机上，然后按照下一步中的说明，从此 .msi 文件中将 BizTalk 应用程序导入到过渡环境中的 BizTalk 组中。 还可使用此 .msi 文件将此应用程序安装到要运行此应用程序的计算机上。  
  
2.  **从.msi 文件导入应用程序。** 可以使用导入向导（可通过 BizTalk Server 管理控制台访问）将 .msi 文件的内容导入到过渡环境中 BizTalk 组中的应用程序中。 有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 如果指定的应用程序已不存在，则导入 .msi 文件时会创建它。 然后，您就可以通过 BizTalk Server 管理控制台查看此应用程序以及修改其配置和内容。 例如，您可能需要修改过渡环境的绑定。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。 如果向具有过渡环境相应绑定的应用程序添加了绑定文件，则可以在导入过程中应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3.  **导出绑定文件并将其添加回应用程序 （可选）。** 如果对应用程序作了更改或添加，则为了以后能更方便地将应用程序导入回过渡环境，可能需要导出应用程序绑定，然后将它们添加回应用程序，在此过程中需要指定绑定的过渡目标环境。 以后将应用程序的 .msi 文件导入回过渡环境中的 BizTalk Server 中时，可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
4.  **安装应用程序。** 现在即可将此应用程序安装到将运行此应用程序的所有计算机上。 安装此应用程序时可以使用安装向导，或双击 .msi 文件即可。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
5.  **测试应用程序以验证配置和绑定。** 现在可以对应用程序进行测试，以确保它在过渡环境中正常工作。 您或开发人员进行所需的更改后，您可以重新执行步骤 1 到步骤 4。  
  
6.  **生成部署到生产环境的应用程序的.msi**。 为生产环境配置完 BizTalk 应用程序并验证配置后，就可以将此应用程序部署到生产环境。 若要执行此操作，你使用导出向导以生成新的.msi 文件中所述[how to Export BizTalk 应用程序如何](../core/how-to-export-a-biztalk-application.md)。 然后就可以将此 .msi 文件提交给负责生产部署的 IT 管理员。 IT 管理员将使用.msi 文件来在生产计算机上导入 BizTalk Server 的应用程序，以及它的计算机上安装将运行它中, 所述[BizTalk 应用程序部署生产任务](../core/production-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)