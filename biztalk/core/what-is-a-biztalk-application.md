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
ms.openlocfilehash: 35a6457911e17c11c1ce09ff9c76a42f72b7bc2c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023851"
---
# <a name="what-is-a-biztalk-application"></a>什么是 BizTalk 应用程序？
BizTalk 应用程序是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一个功能，可使您更快、更轻松地对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务解决方案进行部署、管理和故障排除。 BizTalk 应用程序是 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务解决方案中使用的项（称为“项目”）的逻辑分组。 本主题后面的部分对项目进行了详细介绍。  
  
 新设计的管理和监视 BizTalk Server 工具充分利用这一新概念，以便可以管理和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务解决方案应用程序级别而不只是在各项目级别。 通过创建应用程序并向其添加项目，您可以将解决方案中的一组项目作为单个实体进行查看、打包、部署和管理。 因此，随着复杂应用程序的数量在增加，您仍然可以用简单而直观的方式分别管理它们。  
  
 有几种工具可用于创建和管理应用程序中所述[应用程序部署和管理工具](../core/application-deployment-and-management-tools.md)。  
  
 下图描述了两个 BizTalk 应用程序及其包含的项目。  
  
 ![BizTalk 应用程序和项目](../core/media/biztalkapplication.gif "BizTalkApplication")  
  
## <a name="artifacts"></a>项目  
 项目包括以下组成部分：  
  
- BizTalk 程序集及其包含的特定于 BizTalk 的资源：业务流程、管道、架构和映射  
  
- 不包括特定于 BizTalk 的资源的 .NET 程序集  
  
- 策略  
  
- 发送端口、发送端口组、接收位置和接收端口  
  
- 解决方案使用的其他项，如证书、COM 组件和脚本  
  
  有关每种类型的项目的背景信息，请参阅[运行时体系结构](../core/runtime-architecture.md)。 有关添加详细信息，删除和配置项目，请参阅[管理项目](../core/managing-artifacts.md)。  
  
  应用程序可包含一个业务解决方案中使用的所有项目，也可以只包含其中的一部分。 根据您希望部署项目的方式，您可能需要将它们放在单个应用程序中，或放在两个或更多应用程序中。 有关确定如何项目分组的详细信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。  
  
## <a name="the-default-application"></a>默认应用程序  
 安装后配置 BizTalk Server 后，将自动创建名为 BizTalk 应用程序 1 的默认应用程序。 有关最佳实践的项目分组到不同的应用程序的信息，请参阅[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md)。 您还可以更改默认应用程序或重命名默认应用程序。  
  
 在以下情况下，项目自动添加到默认应用程序：  
  
- 将程序集从 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时未指定应用程序名。 有关详细信息，请参阅[如何部署 BizTalk 程序集从 Visual Studio](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)。  
  
- 使用 BTSTask 将项目添加到应用程序时不指定应用程序名。 有关详细信息，请参阅[AddResource 命令](../core/addresource-command.md)。  
  
- 使用 BTSTask 导入应用程序 .msi 文件时不指定应用程序名。 有关详细信息，请参阅[ImportApp 命令](../core/importapp-command.md)。  
  
## <a name="the-biztalksystem-application"></a>BizTalk.System 应用程序  
 如果 BizTalk Server，配置以下安装名为 BizTalk.System 的应用程序自动创建并填充所有 BizTalk 应用程序，如默认架构和管道都使用的常见项目。 BizTalk.System 及其项目是只读的。 您不能删除或重命名 BizTalk.System，也不能删除、重命名或移动它包含的任何项目。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的每个应用程序都自动包含对 BizTalk.System 应用程序的引用。 这是因为 BizTalk.System 中的项目会被每一个 BizTalk 应用程序使用。 绝不能删除对 BizTalk.System 应用程序的引用。 如果删除了，则应用程序无法正常运行。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)