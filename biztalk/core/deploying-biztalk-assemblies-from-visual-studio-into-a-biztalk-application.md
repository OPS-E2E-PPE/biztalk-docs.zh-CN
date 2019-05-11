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
ms.openlocfilehash: c80c4be7e6b647ab7f62d025f867b2e1a808ab2f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389587"
---
# <a name="deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application"></a>部署 BizTalk 程序集从 Visual Studio 到 BizTalk 应用程序
部署和重新部署 BizTalk 程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到 BizTalk 应用程序。 您可能想要执行此操作以测试的程序集，您已开发并将其打包以便提交功能。  

## <a name="overview"></a>概述  
 BizTalk 应用程序提供一种查看和管理的项，称为"项目"构成 BizTalk 业务解决方案的方法。 项目包含 BizTalk 程序集 （包含业务流程、 架构、 映射和管道），您可以部署到这些[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 项目还包括诸如.NET 程序集、 证书、 脚本、 自述文件和策略，您将添加到 BizTalk 应用程序使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台或 BTSTask 命令行工具。 解决方案开发人员或 IT 管理员可以然后查看、 打包、 部署和管理应用程序及其项目作为单个实体。 有关创建，部署和管理 BizTalk 应用程序，请参阅[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。  
  
 生成并部署 BizTalk 程序集之前，必须创建的项目中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，并创建或添加你想要包含在程序集中的项。 可以创建一个解决方案中的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以包含多个项目，然后生成并部署及其整批发送到同一个应用程序或不同的应用程序的程序集。 有关执行这些任务的说明，请参阅[如何创建 BizTalk 项目](../core/how-to-create-biztalk-projects.md)。  
  
 这些任务后，可以生成、 部署和通过执行以下步骤，取消部署 BizTalk 程序集，在本部分中的主题中所述：  
  
- 每个配置强名称程序集密钥文件[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]项目。  
  
- 设置项目，包括配置重新部署即可轻松地重新部署程序集的部署属性。  
  
- 使用中的部署命令[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]生成 BizTalk 程序集包含在解决方案中并将其部署到 BizTalk 应用程序。 或者，您可以使用部署命令生成和部署程序集在单个项目中，尽管我们不建议执行此操作。  
  
- 测试应用程序并进行必要的更改之后, 使用在部署命令[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以重新生成并重新部署程序集。  
  
- 如有必要，将程序集安装在全局程序集缓存 (GAC) 中或从 GAC 中删除该程序集。  
  
- 取消部署程序集。  
  
  部署到 BizTalk 应用程序的一个或多个程序集之后, 可以完成的应用程序的配置，并将其部署到测试和生产环境。 有关详细信息，请参阅[BizTalk 应用程序部署的开发任务](../core/development-tasks-for-biztalk-application-deployment.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [从 Visual Studio 部署程序集时会发生什么情况](../core/what-happens-when-you-deploy-an-assembly-from-visual-studio.md)  
  
-   [GAC 中的程序集安装](../core/assembly-installation-in-the-gac.md)  
  
-   [如何配置强名称程序集密钥文件](../core/how-to-configure-a-strong-name-assembly-key-file.md)  
  
-   [如何在 Visual Studio 中设置部署属性](../core/how-to-set-deployment-properties-in-visual-studio.md)  
  
-   [如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [如何重新部署 BizTalk 程序集从 Visual Studio](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [如何安装或卸载程序集位于 GAC 中](../core/how-to-install-an-assembly-in-the-gac.md)  