---
title: "部署 BizTalk 应用程序的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, deploying
- best practices, applications
- applications, best practices
- deploying, best practices
ms.assetid: 97ebf479-0dc5-4e95-b409-d3b6ad3d60d0
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b50ff0a6e64633090e562b6ca8e3ae66eb8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-deploying-a-biztalk-application"></a>部署 BizTalk 应用程序的最佳做法
本主题介绍部署 BizTalk 应用程序的最佳实践。  
  
## <a name="group-related-artifacts-together-in-a-single-application"></a>分组在一起在单个应用程序的相关的项目  
 尽可能将相关项目放在同一个 BizTalk 应用程序中。 这样可以将各个项目作为单一实体进行管理和部署，从而更易于管理。 可以将支持同一业务流程的项目或执行类似功能的项目分组到一个应用程序中。  
  
## <a name="deploy-shared-artifacts-in-a-separate-application"></a>部署在单独的应用程序中的共享的项目  
 如果某些项目将由两个或多个应用程序共享，则应将这些共享项目部署在一个单独的应用程序中。 例如，如果两个应用程序共享一个架构，应将该架构部署在一个单独的应用程序中。 这是因为在 BizTalk 组中只能有一个项目具有本地唯一标识符 (LUID) -- 由项目名称和可选的其他属性组成。 如果您在一个应用程序中包括了某个项目，然后在另一个应用程序中创建了对该项目的引用，则当包含该项目的应用程序停止时，您可能会遇到问题（比如进行引用的应用程序不能正常工作）。  
  
 此最佳实践适用于所有项目类型，但文件除外（比如 Readme 文件和脚本，它们是以文件类型的项目添加到应用程序中的）。 这是因为可以在 BizTalk 组中部署具有相同名称的多个文件项目。 因此，您可以在两个或多个应用程序中使用具有相同名称的文件。 停止一个应用程序不会影响另一个应用程序。 有关添加文件项目的详细信息，请参阅[如何将文件添加到应用程序](../core/how-to-add-a-file-to-an-application.md)。  
  
 有关共享特定项目类型的最佳实践，请参阅本部分中的“将共享网站部署在单独的应用程序中”、“将共享策略部署在单独的应用程序中”和“将共享证书部署在单独的应用程序中”。  
  
## <a name="deploy-a-shared-web-site-in-a-separate-application"></a>部署单独的应用程序中的共享的 Web 站点  
 如果某个网站将由多个业务解决方案共享，应将该网站部署在一个单独的应用程序中。 这是因为在卸载某个 BizTalk 应用程序时，作为该应用程序一部分的任何网站的虚拟目录也会被删除，尽管该网站正在运行。 如果该网站与另一个业务解决方案共享，则会导致这个业务解决方案不能正常工作。  
  
## <a name="deploy-shared-policies-in-a-separate-application"></a>部署在单独的应用程序中的共享的策略  
 如果某个策略将由两个或多个应用程序使用，应将该策略部署在一个单独的应用程序中，而不是创建从一个应用程序到另一个应用程序的引用。 这是因为当其中一个应用程序停止时，会取消部署其策略。 如果您停止一个应用程序，而该应用程序包含另一个程序所使用的策略，则该策略将不能在另一个应用程序中起作用。  
  
## <a name="deploy-shared-certificates-in-a-separate-application"></a>部署在单独的应用程序中的共享的证书  
 如果某个证书由两个或多个应用程序的发送端口或接收位置使用，应将该证书部署在一个单独的应用程序中，然后从需要使用该证书的应用程序中引用该程序。 这是因为 BizTalk 组中只能有一个项目具有特定的 LUID，因此您不能将同一个证书导入到两个不同的应用程序中。 如果尝试导入两个使用同一证书的应用程序，则第一个导入将会成功，而第二个导入将会失败。 在这种情况下，使用“覆盖”导入选项并不能解决问题，因为您要覆盖的现有证书包含在另一个应用程序中。  
  
## <a name="never-deploy-an-assembly-from-visual-studio-on-a-production-computer"></a>且勿将 Visual Studio 中的程序集部署在生产计算机上  
 在开发过程中，开发人员经常需要重新部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的程序集。 为了进行重新部署，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 会对程序集中包括的项目取消部署、取消绑定、停止并取消登记。 虽然在部署环境中这样做是必要和适当的，但在生产环境中会产生意外和不需要的结果。 因此，为了避免可能有人尝试在生产计算机上部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的程序集，建议您永远也不要在生产计算机上安装 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
 另外，不要从运行 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的计算机中引用生产数据库。  
  
## <a name="when-deploying-large-msi-files-you-may-need-to-increase-the-default-transaction-timeout-of-the-com-components-used-by-biztalk-to-deploy-applications"></a>部署大的 MSI 文件时，可能需要增大 BizTalk 用于部署应用程序的 COM+ 组件的默认事务超时值。  
 如果要部署的 MSI 文件很大（超过 100 MB），则在应用程序部署过程中，在 BizTalk 所使用的 COM+ 组件的默认事务超时时间内可能无法部署完应用程序。 如果在部署完成之前，与这些 COM+ 组件相关联的事务超时，则部署将失败。 如果要部署很大的 MSI 文件，则应考虑采用以下方法之一以缓解此问题：  
  
1.  部署多个较小的 MSI 文件，而不是部署一个很大的 MSI 文件。  
  
2.  增加 3000 秒与关联的默认事务超时**Microsoft.BizTalk.ApplicationDeployment.Group**和**Microsoft.BizTalk.Deployment.DeployerComponent**中的组件**组件服务**管理界面。 这些组件属于**Microsoft.BizTalk.ApplicationDeployment.Engine**和**Microsoft.Biztalk.Deployment** COM + 应用程序分别。 有关如何更改事务的详细信息请参阅 COM + 组件的超时值[如何更改事务超时值 MTS 或 COM +](http://go.microsoft.com/fwlink/?LinkId=67691)。  
  
## <a name="see-also"></a>另请参阅  
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)