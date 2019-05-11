---
title: 清单：更新 BizTalk 应用程序中的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, redeploying
- updating, applications
- redeploying
- checklists, applications
- updating, checklists
- updating
- applications, updating
- applications, redeploying
- applications, checklists
- checklists, redeploying
ms.assetid: 07ea4a2b-4ada-4d04-9eec-604b63b77415
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a061b121b8a50f8338a6459baa7b3f7ff379bf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357767"
---
# <a name="checklist-update-the-artifacts-in-a-biztalk-application"></a>清单：更新 BizTalk 应用程序中的项目
按照此清单中的步骤，如果你想要更改或更新已部署的应用程序中的一个或多个项目，然后重新部署应用程序。  
  
|步骤|参考|  
|----------|---------------|  
|查看有关更新的应用程序中的项目的重要注意事项。|[更新应用程序的重要注意事项](../core/important-considerations-for-updating-applications.md)|  
|请确保您具有相应的权限来执行部署。|[部署和管理 BizTalk 应用程序所需的权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)|  
|你在 Visual Studio 中的程序集进行任何必要的更改。 如果要更新在生产环境中运行的程序集，您应始终是递增程序集的版本号。 有关背景信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。 然后，部署到 BizTalk 应用程序开发环境中的程序集从 Visual Studio。|[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)|  
|测试所有新的或已更改的项目，确保可能依赖于新的或更改项目的所有项目也进行都测试。 测试时，务必要考虑可能存在此应用程序和其他应用程序之间的依赖关系。|[BizTalk 应用程序部署的测试任务](../core/testing-tasks-for-biztalk-application-deployment.md)|  
|添加、 删除或重新配置中根据需要应用程序的项目。|[如何创建或添加项目](../core/how-to-create-or-add-an-artifact.md)，[如何从应用程序中删除项目](../core/how-to-remove-an-artifact-from-an-application.md)，[管理项目](../core/managing-artifacts.md)|  
|导出到.msi 文件包含新的或更改项目的应用程序。 您可能会将导出的所有应用程序中的项目或只想要添加或更新的项目。 请注意，可以覆盖文件项目。 如果将导出文件项目，请确保它是你想要在应用程序中使用的版本。|[导出 BizTalk 应用程序、绑定和策略](../core/exporting-biztalk-applications-bindings-and-policies.md)|  
|如果在运行时，更新会干扰应用程序，，停止你想要更新的应用程序。 如果要使用新版本更新程序集，您不需要重新启动该应用程序。 **注意：** 尽管它不需要停止应用程序，以便更新某个项目或安装应用程序，但我们建议你更新项目时始终停止应用程序。|[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|更改或更新项目从.msi 文件导入到你想要更新的应用程序中。 请务必指定覆盖现有项目的选项。|[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)|  
|从.msi 文件到的所有计算机运行该应用程序以及运行应用程序依赖于此应用程序的任何计算机上安装更新的应用程序或项目。 如果要更新的 BizTalk 程序集，验证是运行该程序集的每台计算机上的全局程序集缓存 (GAC) 中安装了程序集的新版本。 否则，将程序集安装在每个 GAC 中。|[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)，[如何将程序集安装到 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)|  
|启动应用程序。|[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|包含业务流程导入程序集后，如果应用程序向其导入它已包含具有相同的名称、 公钥标记和版本的程序集，停止和启动该业务流程将主机的主机实例绑定。 这可确保 BizTalk Server 使用程序集的新版本。|[如何停止主机实例](../core/how-to-stop-a-host-instance.md)，[如何启动主机实例](../core/how-to-start-a-host-instance.md)|  
  
## <a name="see-also"></a>请参阅  
 [BizTalk 应用程序部署和管理清单](../core/biztalk-application-deployment-and-management-checklists.md)   
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)