---
title: 部署 BizTalk 应用程序的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, deploying
- best practices, applications
- applications, best practices
- deploying, best practices
ms.assetid: 97ebf479-0dc5-4e95-b409-d3b6ad3d60d0
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03221335dcb41e8496c6808a8f20f0da364979ea
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529125"
---
# <a name="best-practices-for-deploying-a-biztalk-application"></a>部署 BizTalk 应用程序的最佳做法
本主题介绍部署 BizTalk 应用程序的最佳做法。  
  
## <a name="group-related-artifacts-together-in-a-single-application"></a>分组在一起的单个应用程序的相关的项目  
 尽可能多地，将相关的项目放在同一 BizTalk 应用程序。 这允许您管理和部署项目作为单个实体，从而更易于管理。 支持同一业务流程的项目或项目，在单个应用程序中执行相似的功能，可以进行分组。  
  
## <a name="deploy-shared-artifacts-in-a-separate-application"></a>部署单独的应用程序中的共享的项目  
 如果项目将两个或多个应用程序共享，将这些共享的项目部署到单独的应用程序。 例如，如果两个应用程序共享一个架构，则将该架构部署在单独的应用程序中。 这是因为只有一个项目具有的相同本地唯一标识符 (LUID)-项目名称和可选的其他属性组成-可以存在于 BizTalk 组。 如果您在一个应用程序中包括了某个项目，然后创建从另一个应用程序对它的引用，可能会遇到问题，例如引用的应用程序不正常时停止应用程序包含该项目。  
  
 此最佳实践适用于所有项目类型，如自述文件和脚本，以添加到应用程序作为文件类型的项目的文件除外。 这是因为可在 BizTalk 组中部署多个文件项目具有相同的名称。 因此，您可以使用两个或多个应用程序中具有相同名称的文件。 停止一个应用程序不会影响其他应用程序。 有关添加文件项目的详细信息，请参阅[如何将文件添加到应用程序](../core/how-to-add-a-file-to-an-application.md)。  
  
 有关共享特定项目类型的最佳实践，请参阅"部署共享的网站，并在单独的应用程序，""部署共享中单独的应用程序策略"和"共享证书部署在单独的应用程序"在本部分中。  
  
## <a name="deploy-a-shared-web-site-in-a-separate-application"></a>部署单独的应用程序中的共享的 Web 站点  
 如果网站将由多个业务解决方案共享，将网站部署在单独的应用程序。 这是因为在卸载 BizTalk 应用程序时，会删除属于该应用程序的任何网站的虚拟目录，即使该网站正在运行。 如果网站上与另一个业务解决方案共享，另一种业务解决方案将不再正常工作结果。  
  
## <a name="deploy-shared-policies-in-a-separate-application"></a>部署单独的应用程序中的共享的策略  
 如果策略由两个或多个应用程序，应将其部署在单独的应用程序，而不是从到另一个应用程序创建的引用。 这是因为当停止应用程序时，会取消部署其策略。 如果停止包括由其他应用程序的策略的应用程序，该策略将在任一应用程序不再起作用。  
  
## <a name="deploy-shared-certificates-in-a-separate-application"></a>部署在单独的应用程序中的共享的证书  
 如果证书由发送端口或接收位置在两个或多个应用程序中，应将不同的应用程序，该证书部署，然后从需要使用证书的应用程序中引用此应用程序。 这是因为只有一个项目具有特定的 LUID 可以存在于 BizTalk 组中，因此你将不能导入两个不同的应用程序中的相同证书。 如果你尝试导入每个使用相同的证书的两个应用程序，第一个导入将成功，并且第二个将不会。 在这种情况下，使用覆盖导入选项未更正问题，如你想要覆盖现有证书包含在另一个应用程序。  
  
## <a name="never-deploy-an-assembly-from-visual-studio-on-a-production-computer"></a>永远不会部署 Visual Studio 中的生产计算机上的程序集  
 在开发过程中，开发人员经常需要重新部署程序集从[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。 若要启用重新部署，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]可能取消部署、 取消绑定、 停止和取消登记项目包含在程序集。 虽然这是必要和适当的开发环境中，它可能会导致意外后果导致生产环境中。 出于此原因，也为了避免有人尝试从部署程序集的可能[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的生产计算机上，我们建议您永远不会安装[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的生产计算机上。  
  
 此外，永远不会引用生产数据库中的运行的计算机[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
## <a name="when-deploying-large-msi-files-you-may-need-to-increase-the-default-transaction-timeout-of-the-com-components-used-by-biztalk-to-deploy-applications"></a>在部署大的 MSI 文件时，可能需要增大 BizTalk 用于部署应用程序的 COM + 组件的默认事务超时值  
 如果要部署的 MSI 文件非常大 (超过 100 MB) 则不会在 BizTalk 应用程序部署期间所使用的 COM + 组件的默认事务超时值内部署应用程序。 如果相关联的事务与这些 COM + 组件超时时间之前完成部署部署将失败。 如果要部署很大的 MSI 文件则应考虑采用其中一种方法，以缓解此问题：  
  
1.  部署多个较小的 MSI 文件，而不是一个大的 MSI 文件。  
  
2.  增加 3000 秒与关联的默认事务超时**Microsoft.BizTalk.ApplicationDeployment.Group**并**Microsoft.BizTalk.Deployment.DeployerComponent**中的组件**组件服务**管理界面。 这些组件属于**Microsoft.BizTalk.ApplicationDeployment.Engine**并**Microsoft.Biztalk.Deployment** COM + 应用程序分别。 有关如何更改事务的详细信息请参阅 COM + 组件的超时值[如何更改用于 MTS 或 COM + 事务超时值](http://go.microsoft.com/fwlink/?LinkId=67691)。  
  
## <a name="see-also"></a>请参阅  
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)