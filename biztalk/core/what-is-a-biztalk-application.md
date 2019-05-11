---
title: 什么是 BizTalk 应用程序？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk.System application, about BizTalk.System application
- applications, default
- BizTalk.System application
- artifacts, about artifacts
- applications
- applications, about applications
- applications, warnings
- applications, BizTalk.System
- what's new, applications
- BizTalk.System application, warnings
ms.assetid: 68b5527c-d5e1-453b-a51b-3fc1a1d5dce2
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf72f7508444e456d938c4157e25cc9869e93e36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395187"
---
# <a name="what-is-a-biztalk-application"></a>什么是 BizTalk 应用程序？
BizTalk 应用程序是一项功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]更快、 更轻松地部署、 管理和故障排除变得[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案。 BizTalk 应用程序是项，称为"项目"中使用的逻辑分组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案。 本主题后面的更详细地对项目进行了。  
  
 新设计的管理和监视 BizTalk Server 工具充分利用这一新概念，以便可以管理和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案应用程序级别而不只是在各项目级别。 通过创建应用程序并向其添加项目，可以查看、 打包、 部署和管理一组作为单个实体的解决方案中的项目。 因此，随着复杂应用程序数量的增加您仍可以管理它们单独中以简单且直观的方式。  
  
 有几种工具可用于创建和管理应用程序中所述[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。  
  
 下图描绘了两个 BizTalk 应用程序和它们所包含的项目。  
  
 ![BizTalk 应用程序和项目](../core/media/biztalkapplication.gif "BizTalkApplication")  
  
## <a name="artifacts"></a>项目  
 项目包括：  
  
- BizTalk 程序集和特定于 BizTalk 的资源，它们包含 – 业务流程、 管道、 架构和映射  
  
- .NET 程序集不包含特定于 BizTalk 的资源  
  
- 策略  
  
- 发送端口、 发送端口组、 接收位置和接收端口  
  
- 使用该解决方案，如证书、 COM 组件和脚本的其他项  
  
  有关每种类型的项目的背景信息，请参阅[运行时体系结构](../core/runtime-architecture.md)。 有关添加详细信息，删除和配置项目，请参阅[管理项目](../core/managing-artifacts.md)。  
  
  应用程序可以包含的所有项目的业务解决方案或仅在部分中使用。 具体取决于如何，你想要部署项目，你可能想要将其放置到单个应用程序或两个或多个应用程序。 有关确定如何项目分组的详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
## <a name="the-default-application"></a>默认应用程序  
 安装后配置 BizTalk Server 后，将自动创建名为 BizTalk 应用程序 1 的默认应用程序。 有关最佳实践的项目分组到不同的应用程序的信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。 此外可以更改默认应用程序或重命名默认应用程序。  
  
 在以下情况下，项目会自动添加到默认应用程序：  
  
- 当部署中的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而无需指定应用程序名称。 有关详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  
  
- 当您使用 BTSTask 将项目添加到应用程序，而无需指定应用程序名称。 有关详细信息，请参阅[AddResource 命令](../core/addresource-command.md)。  
  
- 当您使用 BTSTask 将应用程序.msi 文件导入而无需指定应用程序名称。 有关详细信息，请参阅[ImportApp 命令](../core/importapp-command.md)。  
  
## <a name="the-biztalksystem-application"></a>BizTalk.System 应用程序  
 如果 BizTalk Server，配置以下安装名为 BizTalk.System 的应用程序自动创建并填充所有 BizTalk 应用程序，如默认架构和管道都使用的常见项目。 BizTalk.System 及其项目是只读的。 不能删除或重命名 BizTalk.System，也可以在删除、 重命名或移动的任何项目，它包含。  
  
> [!IMPORTANT]
>  在每个应用程序[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动包含对 BizTalk.System 应用程序的引用。 这是因为 BizTalk.System 中的项目使用的每个 BizTalk 应用程序。 您应永远不会删除对 BizTalk.System 应用程序的引用。 如果这样做，你的应用程序可能无法正常运行。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)