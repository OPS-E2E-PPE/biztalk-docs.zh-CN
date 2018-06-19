---
title: BizTalk 应用程序部署为测试任务，|Microsoft 文档
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
ms.openlocfilehash: bfd4385c4de076c8c89b409177204ee8fce5548b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279709"
---
# <a name="testing-tasks-for-biztalk-application-deployment"></a>BizTalk 应用程序部署为测试任务，
以下是将 BizTalk 应用程序的项目部署到用于测试和调试的测试环境时所涉及的步骤。  
  
1.  **.Msi 文件复制到你的测试环境。** 中所述[BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)，当 BizTalk 应用程序已准备好测试，开发人员将应用程序项目导出到.msi 文件。 一套完整的解决方案可能会包含一个或多个 BizTalk 应用程序，因此您可能会收到多个要测试的 .msi 文件。 您可以将 .msi 文件复制到测试计算机上，然后按照下一步中的说明，将 .msi 文件中的项目导入 BizTalk Server 中。 还要使用 .msi 文件将应用程序安装到要运行这些应用程序的计算机上。  
  
2.  **从.msi 文件导入应用程序。** 可以使用导入向导（可通过 BizTalk Server 管理控制台访问）将 .msi 文件中的项目导入 BizTalk Server 的当前实例上的应用程序中。 有关详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 如果指定的应用程序已不存在，则导入过程将创建该应用程序。 然后，您就可以通过 BizTalk Server 管理控制台查看此应用程序以及修改其配置和内容。 例如，您可能需要修改测试环境的绑定。 有关详细信息，请参阅[创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)。 如果向具有测试环境的相应绑定的应用程序添加了绑定文件，则可以在导入过程中应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
3.  **安装应用程序。** 现在即可将此应用程序安装到要运行此应用程序的服务器上。 如果应用程序包含基于文件的项目，则必须安装它才能使它正常工作。 可以通过双击 .msi 文件来安装此应用程序。 这将在本地计算机上安装并注册此应用程序的项目，以便此应用程序可以运行。 有关详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
4.  **测试应用程序。** 现在可以测试此应用程序。 开发人员修复您发现的所有 bug 并向您提供更新后的 .msi 文件后，您就可以重新执行步骤 1、2 和 3。  
  
5.  **导出绑定文件并将其添加回应用程序 （可选）。** 如果需要测试所作的更改或所添加的内容，则为了以后能更方便地将应用程序导入回测试环境，可能需要导出应用程序绑定，然后将它们添加回应用程序，在此过程中需要指定绑定的测试目标环境。 以后将应用程序的 .msi 文件导入回测试环境中的 BizTalk Server 中时，可以指定应用这些绑定。 有关详细信息，请参阅[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)。  
  
6.  **生成部署到过渡环境的应用程序的.msi**。 测试完 BizTalk 应用程序后，就可以将此应用程序部署到过渡环境。 若要执行此操作，你使用导出向导生成新的.msi 文件，如之前在步骤 2 中所述。 你可以然后转给.msi 文件 IT 管理员，负责过渡部署。 IT 管理员将使用.msi 文件来导入到 BizTalk Server 暂存计算机上的应用程序和运行它时，在计算机上安装应用程序中所述[BizTalk 应用程序部署暂存任务](../core/staging-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>另请参阅  
 [应用程序部署任务](../core/application-deployment-tasks.md)