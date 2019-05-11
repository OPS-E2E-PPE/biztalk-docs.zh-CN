---
title: 在部署 Visual Studio 中的程序集时，会发生什么情况 |Microsoft Docs
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
ms.openlocfilehash: 1721f519313eb9d2d6aaeba8e1d03e3f7b85d0cf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394807"
---
# <a name="what-happens-when-you-deploy-an-assembly-from-visual-studio"></a>在部署 Visual Studio 中的程序集时，会发生什么情况
本主题介绍在部署中的程序集时，会发生什么情况[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]上的 BizTalk 应用程序到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 可以单独部署项目或解决方案中项目的所有部署在同一时间。 部署一个项目之前, 单独或作为解决方案的一部分指定要将在项目属性中，其程序集部署到其中的应用程序中所述[如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)。 部署项目或解决方案时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，程序集是自动生成并部署到指定的应用程序。 如果本地 BizTalk 组中的现有应用程序具有与项目属性中指定的应用程序相同的名称，该程序集部署到现有应用程序;否则为创建具有指定的名称的新应用程序和程序集部署到其中。 作为此过程的一部分，以及业务流程、 管道、 架构和映射，它包含 （称为"项目"） 的程序集是导入本地 BizTalk 管理数据库，数据库中与指定的应用程序相关联。  
  
 即使在同一时间部署解决方案中的项目，你可以部署到同一个 BizTalk 应用程序或不同的 BizTalk 应用程序，在解决方案中的项目。 下图说明了部署中的 BizTalk 解决方案中包含的三个程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到两个不同的 BizTalk 应用程序。  
  
 ![部署 BizTalk 程序集](../core/media/visualstudiodeploy.gif "VisualStudioDeploy")  
  
 在部署项目或解决方案后，可以查看和管理中的程序集及其项目[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或通过使用 BTSTask 命令行工具。  
  
## <a name="destination-locations"></a>目标位置  
 部署中的程序集时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，程序集的目标位置默认为程序集的源位置。 安装或导出中的程序集时[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如果"from"和"目标"环境是不相同，则安装将失败。 例如，如果源位置为 d: [路径] / [文件名] 和目标安装计算机不具有"D"驱动器，则安装将失败。  
  
 添加使用 BizTalk 管理器资源与此行为在这种情况下，默认目标位置为 %btad_installdir%。 此环境变量将扩展安装期间指定的安装目录。  
  
 若要解决此问题，请使用以下过程：  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，部署程序集。  
  
2. 部署程序集后，打开 BizTalk Administrator 组。  
  
3. 修改相应的目标位置。 例如，更改目标位置为 %btad_installdir%。  
  
   后修改目标位置，将同一程序集的后续重新部署作为默认使用此新位置。  
  
   有关详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  
  
## <a name="deploying-solutions-vs-projects"></a>部署解决方案 vs。项目  
 我们强烈建议您始终部署解决方案而不是单个项目。 如果有要部署的程序集与另一个程序集之间的依赖项部署单个项目，必须执行一系列手动步骤来完成部署。 但是，部署解决方案时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动采取所有步骤才能管理程序集之间的依赖项。 有关详细信息，请参阅[如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)。  
  
 下图说明的步骤，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所需重新部署时部署解决方案有依赖关系的程序集。  
  
 ![部署解决方案中的程序集](../core/media/deployassemblies.gif "DeployAssemblies")  
  
## <a name="see-also"></a>请参阅  
 [将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)