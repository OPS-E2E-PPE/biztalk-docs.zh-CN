---
title: 部署来自 Visual Studio 的程序集时，会发生什么情况 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 421df529-1ddb-4f49-a40a-c06f2a434ffc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66454d80d702cc6b3ca20708b07fd64cdfcb00d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290165"
---
# <a name="what-happens-when-you-deploy-an-assembly-from-visual-studio"></a>部署来自 Visual Studio 的程序集时，会发生什么情况
本主题介绍将程序集从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上的 BizTalk 应用程序时所发生的情况。  
  
 可以选择逐个部署项目，也可以同时部署某个解决方案中的所有项目。 部署项目前, 单独或作为解决方案的一部分，你指定要将在项目属性中，其程序集部署到应用程序中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中部属项目或解决方案时，这些程序集将自动生成并且部署到指定的应用程序中。 如果本地 BizTalk 组中的现有应用程序与项目属性中指定的应用程序同名，程序集将部署到现有应用程序中；如果不同名，将创建一个具有指定名称的新应用程序，程序集将部署到其中。 在此过程中，程序集连同它所包含的业务流程、管道、架构和映射（称为“项目”）将导入本地 BizTalk 管理数据库，并在该数据库中与指定的应用程序建立关联。  
  
 即便同时部署某解决方案中的各个项目，也可以选择将这些项目部署到相同或不同的 BizTalk 应用程序中。 下图显示了如何将 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的某个 BizTalk 解决方案所含的三个程序集部署到两个不同的 BizTalk 应用程序中。  
  
 ![部署 BizTalk 程序集](../core/media/visualstudiodeploy.gif "VisualStudioDeploy")  
  
 在部署项目或解决方案后，您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台内部或者使用 BTSTask 命令行工具查看和管理程序集及其项目。  
  
## <a name="destination-locations"></a>目标位置  
 从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署程序集时，程序集的目标位置默认为该程序集的源位置。 从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 安装或导出程序集时，如果“源”和“目标”环境不一致，安装将失败。 例如，如果源位置为 D:[路径]/[文件名]，而目标安装计算机没有“D”驱动器，那么安装将失败。  
  
 此行为不同于使用 BizTalk Administrator 组成员身份添加资源，在后一种情况下，默认目标位置为 %BTAD_InstallDir%。 此环境变量将扩展到安装期间指定的安装目录。  
  
 若要解决此问题，请使用以下过程：  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中部署程序集。  
  
2.  部署程序集之后，打开 BizTalk Administrator 组。  
  
3.  按需修改目标位置。 例如，将目标位置改为 %BTAD_InstallDir%。  
  
 一旦修改了目标位置，这一新位置将用作后续重新部署同一程序集时的默认位置。  
  
 有关详细信息，请参阅[如何部署 BizTalk 程序集，从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  
  
## <a name="deploying-solutions-vs-projects"></a>部署解决方案 vs。项目  
 我们强烈建议您始终部署解决方案而不是单个项目。 如果您部署的是单个项目而正在部署的程序集与其他程序集之间存在依存关系，则必须采取若干手动步骤来完成部署。 但如果部署的是解决方案，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将自动采取管理程序集之间的依存关系所需的所有步骤。 有关详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)。  
  
 下图显示了部署解决方案时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 为重新部署具有依存关系的各个程序集而采取的步骤。  
  
 ![部署解决方案中的程序集](../core/media/deployassemblies.gif "DeployAssemblies")  
  
## <a name="see-also"></a>另请参阅  
 [部署到 BizTalk 应用程序从 Visual Studio BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)