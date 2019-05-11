---
title: 清单：部署 BizTalk 应用程序 |Microsoft Docs
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
ms.openlocfilehash: 407dfc59a6d9e8fe6ef3beec341ad5ca75aa4f57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357439"
---
# <a name="checklist-deploy-a-biztalk-application"></a>清单：部署 BizTalk 应用程序

|                                                                                                                                                                                                             步骤                                                                                                                                                                                                             |                                                                                                                                                                                          参考                                                                                                                                                                                          |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                      了解 BizTalk 应用程序部署功能和功能。 您可能还要考虑如何使用绑定文件，使应用程序的部署更快、 更轻松。                                                                                                                      |                                                                           [了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)，[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)                                                                            |
|                                                                                                                                                                           请确保您具有相应的权限来执行部署。                                                                                                                                                                            |                                                                                                                  [部署和管理 BizTalk 应用程序所需的权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)                                                                                                                  |
| 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，BizTalk 解决方案中设置为每个项目的部署属性。 属性包括对于组，数据库服务器和 BizTalk 管理数据库的名称和目标 BizTalk 应用程序的名称。 此外可以启用重新部署，并指定自动重新启动主机实例在重新部署时的选项。 |                                                                                                                                      [如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)                                                                                                                                      |
|                                                                                                                                         部署 BizTalk 程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到目标应用程序。                                                                                                                                          |                                                                                                                                    [如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)                                                                                                                                    |
|                                                                               完成 BizTalk 应用程序，如通过添加.NET 程序集、 自述文件、 特定于环境的绑定文件和脚本;并配置端口和接收位置。 此外添加到主机计算机的任何基础结构，如文件存放位置。                                                                               |                                                                                           [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)，[绑定文件和应用程序部署](../core/binding-files-and-application-deployment.md)                                                                                            |
|                                                                                                                导出到.msi 文件将用于该应用程序导入其他 BizTalk 组，以及安装到将运行它的计算机上的应用程序的 BizTalk 应用程序。                                                                                                                 |                                                                                                                                                    [如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)                                                                                                                                                    |
|                                                                                                      导入目标 BizTalk 组中创建 BizTalk 应用程序的.msi 文件。 如果已将特定于环境的绑定文件添加到应用程序，则可以选择将应用于已导入的绑定。                                                                                                       |                                                                                                                                                    [如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)                                                                                                                                                    |
|                   请对应用程序做任何进一步修改，使其在目标环境，如更改端口配置中运行。 如果进行了任何更改，将导出到.msi 文件将用于将运行它的计算机上安装应用程序的应用程序。 此外可以将应用程序导入你想要将其部署其他 BizTalk 组。                    | [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)，[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md)，[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)，[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md) |
|                                                                                             使用.msi 文件中，在所有将运行它，然后再启动应用程序的计算机上安装应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。                                                                                             |                                                                                                                                                   [如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)                                                                                                                                                   |

## <a name="see-also"></a>请参阅  
 [BizTalk 应用程序的部署和管理清单](../core/biztalk-application-deployment-and-management-checklists.md)