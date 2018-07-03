---
title: 清单： 部署 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- checklists, deploying
- applications, deploying
- deploying [applications], checklists
- checklists, applications
- applications, checklists
ms.assetid: 0f936475-eea7-49b0-a4ea-9488b4ce3847
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c52644743a418a65abf3815f97a510b94773fca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009990"
---
# <a name="checklist-deploy-a-biztalk-application"></a>清单： 部署 BizTalk 应用程序

|                                                                                                                                                                                                             步骤                                                                                                                                                                                                             |                                                                                                                                                                                          参考                                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                      了解 BizTalk 应用程序部署的特性和功能。 您可能还需要考虑如何更快和更方便地使用绑定文件来进行应用程序部署。                                                                                                                      |                                                                           [了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)，[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)                                                                            |
|                                                                                                                                                                           请确保您具有相应的权限来执行部署。                                                                                                                                                                            |                                                                                                                  [部署和管理 BizTalk 应用程序所需的权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)                                                                                                                  |
| 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，BizTalk 解决方案中设置为每个项目的部署属性。 属性包括数据库服务器的名称和该组的 BizTalk 管理数据库，以及目标 BizTalk 应用程序的名称。 您还可以启用重新部署，并指定选项以在重新部署时自动重新启动主机实例。 |                                                                                                                                      [如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)                                                                                                                                      |
|                                                                                                                                         将 BizTalk 程序集从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署到目标应用程序。                                                                                                                                          |                                                                                                                                    [如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)                                                                                                                                    |
|                                                                               完成 BizTalk 应用程序，如通过添加 .NET 程序集、自述文件、特定于环境的绑定文件和脚本，以及配置端口和接收位置。 另外，向主机计算机添加任何基础结构，如文件存放位置。                                                                               |                                                                                           [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)，[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)                                                                                            |
|                                                                                                                将 BizTalk 应用程序导出到 .msi 文件（您将使用该 .msi 文件将应用程序导入到其他 BizTalk 组），并将应用程序安装到将要运行它的计算机中。                                                                                                                 |                                                                                                                                                    [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)                                                                                                                                                    |
|                                                                                                      导入 .msi 文件以在目标 BizTalk 组中创建 BizTalk 应用程序。 如果您已将特定于环境的绑定文件添加到该应用程序中，则可以选择导入时要应用的绑定。                                                                                                       |                                                                                                                                                    [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)                                                                                                                                                    |
|                   对该应用程序进行任何附加修改，以便它可以在目标环境中运行，如更改端口配置。 如果您已经进行了任何更改，请将应用程序导出至 .msi 文件，您将使用该 .msi 文件将应用程序安装到要运行它的计算机中。 您还可以将应用程序导入到要部署该应用程序的其他 BizTalk 组。                    | [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)，[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)，[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)，[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md) |
|                                                                                             使用 .msi 文件将该应用程序安装到要运行它的所有计算机中，然后从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台启动该应用程序。                                                                                             |                                                                                                                                                   [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)                                                                                                                                                   |

## <a name="see-also"></a>请参阅  
 [BizTalk 应用程序的部署和管理清单](../core/biztalk-application-deployment-and-management-checklists.md)