---
title: 绑定文件和应用程序部署 |Microsoft 文档
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
ms.openlocfilehash: dc6908f962cd3bb8f9fdec3fcaab6bc131c889da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234061"
---
# <a name="binding-files-and-application-deployment"></a>绑定文件和应用程序部署
本主题提供概述信息，说明如何使用绑定文件简化 BizTalk 程序集和应用程序的部署。 在下列情况下，您会发现，由于使用绑定文件避免了手动配置绑定，因此可以加速部署过程：  
  
-   将应用程序从一种部署环境移到另一个。  
  
-   更新程序集。  
  
-   将程序集部署到多个 BizTalk 组。  
  
## <a name="what-is-a-binding"></a>什么是绑定？  
 绑定可以在逻辑终结点（如业务流程端口或角色链接）与物理终结点（如发送/接收端口或参与方）之间创建映射。 这样即可在 BizTalk 业务解决方案的不同组件之间进行通信。 使用 BizTalk Server 管理控制台可以创建绑定。  
  
## <a name="what-is-a-binding-file"></a>什么是绑定文件？  
 绑定文件是一个 .xml 文件，其中包含 BizTalk 程序集、应用程序或组范围内的每一 BizTalk 业务流程、管道、映射或架构的绑定信息。 绑定文件描述各个业务流程绑定到的主机、主机信任级别，以及已经配置的每个发送端口、发送端口组、接收端口、接收位置和参与方的设置。 您可以生成绑定文件，然后将其中包含的绑定应用到某个程序集、应用程序或组，以避免在不同的部署环境中手动配置绑定。  
  
## <a name="why-use-binding-files"></a>为什么使用绑定文件？  
 在以下情况下可能需要使用绑定文件。  
  
### <a name="moving-from-one-environment-to-another"></a>转移到不同环境  
 您可以使用绑定文件简化应用程序在不同部署环境之间的转移，比如从开发环境移至测试环境。 这是因为不同的部署环境往往要求重新配置绑定，但通过使用绑定文件，您可以避免重复执行这一手动配置步骤。  
  
 进行此操作的方法之一是创建一个绑定库，在将应用程序部署到新环境时从绑定库中进行选择。 例如，可以为您的测试环境创建一个绑定文件，为生产环境创建另一个绑定文件，然后将它们一同添加到应用程序中。 将该应用程序导入测试环境时，可以选择一个选项来应用测试绑定。 同样，将该应用程序导入生产环境时，也可以选择一个选项来应用生产绑定。 这样可以避免为不同环境手动重新配置绑定。 另一种方法是在将应用程序导入当前环境后，再导入为该环境创建的绑定。 这样可以自动应用绑定。  
  
### <a name="updating-an-assembly"></a>更新程序集  
 在更新应用程序中的一个程序集时，通常会覆盖该程序集的绑定，也有可能该程序集根本未绑定，所以您不得不手动重新配置绑定。 为避免此情况，您可按如下所示使用绑定文件：  
  
-   **正在更新相同版本的程序集。** 如果程序集具有早期绑定端口或动态端口，而您在 BizTalk Server 管理控制台中更改了端口配置，在您使用相同版本号的程序集来更新当前程序集时这些设置将丢失。 您可以导出准备更新的程序集的绑定文件。 更新程序集后，您可以将该程序集导入应用程序，然后导入其绑定文件以重新应用先前的绑定。  
  
-   **更新的较新版本的程序集。** 您可以导出准备更新的程序集的绑定文件，然后编辑该文件以反映新的程序集版本。 将新的程序集版本导入应用程序后，您可以将绑定文件导入应用程序以应用绑定。 有关编辑绑定文件的说明，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。  
  
### <a name="deploying-an-assembly-to-multiple-biztalk-groups"></a>将程序集部署到多个 BizTalk 组  
 将程序集部署到多个 BizTalk 组时，可以将程序集的绑定与该程序集一同传输。 这样可以避免在每个组中为程序集分别配置绑定。 可按如下方式操作：  
  
1.  通过导出程序集绑定为要部署的程序集创建绑定文件。  
  
2.  向应用程序添加程序集及其绑定文件。 如果您要将程序集与其他项目分开部署，则应用程序只能包含程序集及绑定文件。  
  
3.  导出应用程序的 .msi 文件，务必选择一同导出绑定文件。  
  
4.  将应用程序的 .msi 文件导入要在其中部署该文件的 BizTalk 组和应用程序。 文件中的绑定将在导入时自动应用到程序集内。  
  
## <a name="how-can-i-generate-and-use-binding-files"></a>如何生成和使用绑定文件？  
 BizTalk 程序集，应用程序，或组，不自动生成一个绑定文件但中所述，你可以通过导出的绑定，生成绑定文件[导出绑定](../core/exporting-bindings6.md)。 你可以然后绑定文件导入的应用程序或组中中, 所述[如何导入到 BizTalk 应用程序的绑定](../core/how-to-import-bindings-into-a-biztalk-application.md)和[如何导入绑定到 BizTalk 组](../core/how-to-import-bindings-into-a-biztalk-group.md)，后者自动将应用自己的绑定。  
  
 或者，向应用程序添加的绑定文件，以便在将应用程序导入另一个组，而不立即应用中所述应用自己的绑定[如何将绑定文件添加到应用程序](../core/how-to-add-a-binding-file-to-an-application2.md). 使用最后一种方法可以向应用程序添加多个绑定文件，而且可以选择分别为每个绑定文件指定目标环境。 当你导入应用程序时，然后，可以选择要将应用，哪些绑定中所述，在目标部署环境中，基于[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。 使用最后一种方法，还可以在应用程序中分别导入不同程序集的绑定文件。  
  
 您可以在生成绑定文件后对其进行编辑，以更改其中的绑定信息。 有关详细信息，请参阅[自定义绑定文件](../core/customizing-binding-files.md)。  
  
## <a name="how-are-bindings-applied"></a>如何应用绑定？  
 将绑定文件导入应用程序或是将应用程序导入新的 BizTalk 组时，将应用绑定。 使用绑定文件时，务须理解项目绑定到主机的方式以及应用绑定的顺序。  
  
### <a name="binding-to-hosts"></a>绑定到主机  
 导出绑定时（单独导出或作为应用程序的一部分导出），主机和信任级别按如下方式存储在绑定文件中：  
  
-   **发送端口。** 与发送处理程序关联的主机的信任级别。  
  
-   **接收位置。** 与接收处理程序关联的主机的信任级别。  
  
-   **业务流程。** 主机的信任级别。  
  
 将绑定导入应用程序或是将应用程序从 .msi 文件导入新的 BizTalk 组时，绑定文件中的主机和信任级别将与应用程序中的主机和信任级别进行匹配，如下所示：  
  
-   **发送端口。** 发送端口会绑定到同名的发送处理程序，并绑定到具有与绑定文件中所存储信任级别相同的信任级别的主机。  
  
-   **接收位置。** 接收位置绑定到同名的接收处理程序，并且绑定到的主机的信任级别与存储在绑定文件中的信任级别相同。  
  
-   **业务流程。** 业务流程绑定到与绑定文件中的主机名称和信任级别相同的主机。  
  
### <a name="order-in-which-bindings-are-applied"></a>绑定的应用顺序  
 导入应用程序时，绑定按如下顺序应用：  
  
1.  由 BizTalk Server 生成的、未通过绑定文件显式添加到应用程序但用户已经显式选择导出到应用程序 .msi 文件的应用程序绑定。  
  
2.  已经添加到应用程序但并未指定目标部署环境的绑定文件中的绑定。 这些绑定可以按任意顺序应用。  
  
3.  已经添加到应用程序、并且具有关联目标部署环境（与为导入应用程序选定的部署环境相匹配）的绑定文件中的绑定。 这些绑定可以按任意顺序应用。  
  
 由于绑定在导入过程中应用，所以已应用的绑定将被同名的新绑定所覆盖。 换言之，将应用的具有特定名称的最后一个绑定生效。  
  
 例如，如果某个现有应用程序包括一个名为 SendPort1 的发送端口，并且应用的绑定文件描述的是同名的发送端口，那么该绑定文件中的设置将覆盖 SendPort1 的现有设置。 又如，如果某个现有应用程序包括一个名为 ErrorHandling.ErrorHandler.ResubmitLogic 的业务流程，并且绑定文件描述了同名的业务流程，那么该绑定文件中的绑定将覆盖该业务流程中的所有现有绑定。  
  
## <a name="see-also"></a>另请参阅  
 [了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)