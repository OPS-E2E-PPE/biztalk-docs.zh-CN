---
title: 部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: accef4b8-acdf-4043-8fd7-2db9ea752074
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4dcacede998ec0c921a379841e9b31389f2aa20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007182"
---
# <a name="deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application"></a>将 BizTalk 程序集从 Visual Studio 部署到 BizTalk 应用程序
部署和重新部署 BizTalk 程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序。 当您想要测试所开发的程序集的功能并且想要将它们打包以便移交时，可能要进行 BizTalk 程序集的这一部署和重新部署。  

## <a name="overview"></a>概述  
 BizTalk 应用程序提供了查看和管理构成 BizTalk 业务解决方案的项（称为“项目”）的方法。 项目包含 BizTalk 程序集（包含业务流程、架构、映射和管道），您可以将这些程序集从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署到 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 项目还包括诸如 .NET 程序集、证书、脚本、自述文件和策略等项，您可以通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台或 BTSTask 命令行工具将这些项添加到您的 BizTalk 应用程序中。 然后，解决方案开发人员或 IT 管理员可以将该应用程序及其项目作为单个实体查看、打包、部署和管理。 有关创建，部署和管理 BizTalk 应用程序，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。  
  
 在您生成和部署 BizTalk 程序集之前，必须先在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中创建一个项目，并且要创建或添加您要在该程序集中包括的项。 您可以在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中创建一个包含多个项目的解决方案，然后一次性将这些项目的所有程序集都生成并部署到相同或不同的应用程序中。 有关执行这些任务的说明，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。  
  
 在完成这些任务后，您可以通过采用以下步骤（在本部分的各主题中予以介绍），生成、部署和取消部署这些 BizTalk 程序集：  
  
- 为每个 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目配置一个强名称的程序集密钥文件。  
  
- 设置项目的部署属性，包括配置“重新部署”选项以便轻松地重新部署程序集。  
  
- 可以使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的“部署”命令生成解决方案中包含的 BizTalk 程序集，并将它们部署到 BizTalk 应用程序中。 或者，您可以使用“部署”命令在单个项目中生成和部署某一程序集，尽管我们不推荐这样做。  
  
- 在测试应用程序并进行必要的更改后，在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中使用“部署”命令来重新生成和重新部署该程序集。  
  
- 如有必要，在全局程序集缓存 (GAC) 中安装该程序集，或者从 GAC 中删除该程序集。  
  
- 取消部署程序集。  
  
  在将一个或多个程序集部署到某一 BizTalk 应用程序后，您可以完成该应用程序的配置并将它部署到某一测试中，然后部署到生产环境中。 有关详细信息，请参阅[BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [从 Visual Studio 部署程序集时会发生什么情况](../core/what-happens-when-you-deploy-an-assembly-from-visual-studio.md)  
  
-   [GAC 中的程序集安装](../core/assembly-installation-in-the-gac.md)  
  
-   [如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)  
  
-   [如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)  
  
-   [如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [如何安装或卸载程序集位于 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)  