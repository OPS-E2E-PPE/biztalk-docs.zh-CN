---
title: 绑定文件和应用程序部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bindings
- deploying [applications], binding files
- assemblies, binding files
- bindings, applying
- groups, assemblies
- applications, binding files
- binding files, applications
- bindings, hosts
- deploying, assemblies
- updating, assemblies
- assemblies, updating
- hosts, bindings
- binding files, assemblies
- applications, moving
- assemblies, deploying
- binding files, about binding files
- bindings, about bindings
- groups, deploying
- binding files, deploying
- bindings, binding files
ms.assetid: 396ad021-8001-4ed8-8b28-85b72f981fae
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53037b44001d22f3f1f2b1463cd2f6d057d41355
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358366"
---
# <a name="binding-files-and-application-deployment"></a>绑定文件和应用程序部署
本主题提供有关使用绑定文件简化 BizTalk 程序集和应用程序部署的概述信息。 您可能会发现绑定文件避免了手动配置绑定在以下方案中加快部署速度：  
  
-   在一个部署环境之间移动应用程序。  
  
-   更新的程序集。  
  
-   将程序集部署到多个 BizTalk 组。  
  
## <a name="what-is-a-binding"></a>什么是绑定？  
 一个绑定和之间创建映射逻辑终结点，如业务流程端口或角色链接，物理终结点，如发送和接收端口或参与方。 这样，BizTalk 业务解决方案的不同组件之间的通信。 可以使用 BizTalk Server 管理控制台来创建绑定。  
  
## <a name="what-is-a-binding-file"></a>什么是绑定文件？  
 绑定文件是一个.xml 文件，其中每个 BizTalk 业务流程、 管道、 映射或架构的 BizTalk 程序集、 应用程序或组作用域中的绑定信息。 绑定文件描述每个业务流程绑定到哪些主机和信任级别，以及每个发送端口设置、 发送端口组、 接收端口、 接收位置，且已配置的参与方。 您可以生成绑定文件，并将它们包含的绑定应用到的程序集、 程序或组，以避免在不同的部署环境中手动配置绑定。  
  
## <a name="why-use-binding-files"></a>为什么使用绑定文件？  
 您可能想要使用以下方案中的绑定文件。  
  
### <a name="moving-from-one-environment-to-another"></a>将其从一个环境移到另一个  
 绑定文件可用于轻松地将应用程序在不同部署环境到另一个，如从开发环境到测试环境。 这是因为绑定通常必须重新配置为不同的部署环境，但通过使用绑定文件，可以避免重复执行此手动配置步骤。  
  
 可以执行此操作的一种方法是创建要部署到新环境的应用程序时，选择从中绑定的库。 例如，您可以为你的测试环境，另一个用于生产环境中创建绑定文件，然后将这两个添加到应用程序。 当应用程序导入测试环境时，可以选择一个选项来应用测试绑定。 同样，当应用程序导入生产环境时，可以选择一个选项来应用生产绑定。 这就无需重新配置为不同环境手动绑定。 另一种方法是将应用程序导入其中后，导入当前环境的已创建的绑定。 这会自动应用绑定。  
  
### <a name="updating-an-assembly"></a>更新的程序集  
 更新应用程序中的程序集时，其绑定通常被覆盖，否则该程序集可能未绑定，强制您手动重新配置绑定。 若要避免此问题，可以按如下所示使用绑定文件：  
  
-   **正在更新同一版本的程序集。** 如果程序集具有早期绑定端口或动态端口，并更改 BizTalk Server 管理控制台中的端口配置，设置将会丢失时使用的程序集具有相同的版本号更新程序集。 可以为要更新的程序集导出绑定文件。 在更新程序集之后可以导入应用程序的程序集，然后导入其绑定文件以重新应用以前的绑定。  
  
-   **使用更新的版本更新的程序集。** 可以为要更新，然后编辑它以反映新的程序集版本的程序集导出绑定文件。 新的程序集版本导入应用程序后，您可以将绑定文件导入要应用这些绑定的应用程序。 有关编辑绑定文件的说明，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。  
  
### <a name="deploying-an-assembly-to-multiple-biztalk-groups"></a>将程序集部署到多个 BizTalk 组  
 在部署到多个 BizTalk 组程序集时，可以传输以及该程序集的程序集的绑定。 这就无需单独配置每个组中的程序集的绑定。 您可以按如下所示执行此操作：  
  
1.  为你想要部署导出的程序集的绑定的程序集创建绑定文件。  
  
2.  将程序集和其绑定文件添加到应用程序。 如果要部署独立于其他项目的程序集，该应用程序可以包含仅将程序集和绑定文件。  
  
3.  导出应用程序，务必选择一同导出绑定文件的.msi 文件。  
  
4.  应用程序.msi 文件导入 BizTalk 组和你想要将其部署的应用程序。 文件中的绑定会自动应用上导入程序集。  
  
## <a name="how-can-i-generate-and-use-binding-files"></a>如何生成和使用绑定文件？  
 BizTalk 程序集、 应用程序或组，不会自动生成绑定文件，但可以生成绑定文件导出的绑定，如中所述[导出绑定](../core/exporting-bindings6.md)。 你可以然后导入绑定文件的应用程序或组，如中所述[如何将绑定导入到 BizTalk 应用程序](../core/how-to-import-bindings-into-a-biztalk-application.md)并[如何将绑定导入到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，它自动应用其中的绑定。  
  
 或者，向应用程序添加绑定文件，以便应用程序导入另一个组，而不是立即应用，如中所述应用其绑定[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md). 使用最后一个方法，可以将多个绑定文件添加到应用程序，并选择性地指定为每个目标部署环境。 当您导入应用程序时，然后，可以选择要应用的绑定基于目标部署环境，如中所述[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。 使用最后一个方法，您可还导入单独的绑定文件不同的程序集在应用程序中。  
  
 生成对其进行更改其绑定信息后，可以编辑绑定文件。 有关详细信息，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。  
  
## <a name="how-are-bindings-applied"></a>如何应用绑定？  
 当绑定文件导入应用程序，或者当应用程序导入到新的 BizTalk 组，则应用绑定。 使用绑定文件时，务必了解项目将如何绑定到主机和应用绑定的顺序。  
  
### <a name="binding-to-hosts"></a>将绑定到主机  
 导出绑定时单独或作为应用程序的一部分，主机和信任级别存储在绑定文件中，如下所示：  
  
- **发送端口。** 与发送处理程序关联的主机的信任级别。  
  
- **接收位置。** 与接收处理程序相关联的主机的信任级别。  
  
- **业务流程。** 主机的信任级别。  
  
  当要将绑定导入应用程序或应用程序从.msi 文件导入新的 BizTalk 组时，主机和绑定文件中的信任级别与匹配主机和在应用程序中的信任级别，如下所示：  
  
- **发送端口。** 发送端口绑定到具有相同名称的发送处理程序并且绑定到具有相同信任级别为存储在绑定文件中的主机。  
  
- **接收位置。** 接收位置绑定到具有相同名称的接收处理程序并且绑定到具有相同信任级别为存储在绑定文件中的主机。  
  
- **业务流程。** 业务流程绑定到绑定文件中的主机具有相同名称和信任级别和的中。  
  
### <a name="order-in-which-bindings-are-applied"></a>绑定的应用顺序  
 导入应用程序时，绑定按以下顺序应用：  
  
1. 应用程序绑定由 BizTalk Server 生成的未显式添加到应用程序通过绑定文件，但已经显式选择导出到应用程序.msi 文件的用户。  
  
2. 绑定的文件的已添加到应用程序，以及哪些没有指定目标部署环境中的绑定。 这些绑定可以按任何特定顺序应用。  
  
3. 导入绑定的文件的已添加到应用程序，并且具有所选应用程序的部署环境相匹配的相关联的目标部署环境中的绑定。 这些绑定可以按任何特定顺序应用。  
  
   当导入过程中应用绑定时，已应用的绑定将覆盖具有相同名称的新绑定。 换而言之，具有特定名称的最后一个绑定，应用将生效。  
  
   例如，如果某个现有的应用程序包括一个名为 SendPort1 的发送端口和绑定文件将应用描述具有相同名称的发送端口，绑定文件中的设置将覆盖 SendPort1 的现有设置。 如果现有应用程序包含名为 ErrorHandling.ErrorHandler.ResubmitLogic，例如，业务流程，绑定文件描述具有相同名称的业务流程，所有现有绑定业务流程将使用进行编写绑定文件中的绑定。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)