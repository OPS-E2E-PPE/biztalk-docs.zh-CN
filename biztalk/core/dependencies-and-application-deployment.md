---
title: 依赖关系和应用程序部署 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying [applications], dependencies
- assemblies, dependencies
- artifacts, dependencies
- applications, dependencies
ms.assetid: b78c5a0d-b042-4862-bce7-59469365b369
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cc7e4b44a09da04e62062d90cd99da0354cca34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22242205"
---
# <a name="dependencies-and-application-deployment"></a>依存关系和应用程序部署
本主题介绍两个或多个 BizTalk 应用程序中各项目之间的依存关系如何影响应用程序的部署和维护。  
  
 当一个项目需要使用另一个项目才能正常运行时，它称为*依赖*另一个项目。 例如，在业务流程需要使用特定架构进行消息解析时，或者需要使用特定管道以便正确传输消息时，便是此类依存关系。 在上述这两种情况中，业务流程依赖于其他项目。  
  
 在您可以更新应用程序中的某一项目之前，必须首先取消对该项目以及依赖于该项目的所有项目的部署。 在具有依存关系的多个项目存在于同一应用程序中时，BizTalk Server 自动处理更新的和依赖的项目的取消部署和重新部署任务。 但在具有依存关系的项目存在于不同应用程序时，就无法自动完成上述任务了。 您必须首先执行手动步骤来取消对具有依存关系的项目的部署，然后才可以更新它们所依赖的项目。 之后，您必须手动重新部署依赖的项目。  
  
 为了在更新其他项目所依赖的项目时无需执行这些手动步骤，您可以尝试将具有依存关系的所有项目一起保存在同一应用程序中。 但是，这并非总是可行的。 中所述[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)，大多数类型的项目必须是唯一 BizTalk 组中。 您不能在同一组的两个不同应用程序中具有相同的项目，即使这两个应用程序都包含依赖于相同项目的项目。  
  
 在发生此情况时，您可以将所需的项目添加到一个应用程序，然后添加从包含依赖它的项目的任何其他应用程序对该应用程序的引用。 在您添加对某一应用程序的引用时，该应用程序中的项目可以使用它引用的应用程序中的任何项目。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
 下图描述了两个应用程序，这两个应用程序分别依赖于第三个应用程序中的项目。 订单处理应用程序使用 Schema1，而它包含在架构应用程序中，因此，订单处理应用程序包含对架构应用程序的引用。 抵押应用程序使用 Schema2，它也包含在架构应用程序中，同样，抵押应用程序包含对后者的引用。  
  
 ![两个应用程序都引用第三个应用程序](../core/media/applicationdependencies.gif "ApplicationDependencies")  
  
 添加从一个应用程序到另一个应用程序的引用将在两个应用程序之间创建一个依存关系，这个依存关系影响您部署和管理这两个应用程序的方式。 由于在本主题后面所述的应用程序依赖项的各种影响，我们建议你遵循的最佳做法来将项目添加到应用程序，中, 所述[部署 BizTalk 应用程序的最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md).  
  
 下图阐释在存在依存关系链时更新某一程序集所涉及的步骤，并且依赖于要更新的程序集的所有程序集都存在于同一应用程序中。  
  
 ![更新具有依赖项的程序集](../core/media/simpleadminredeploy.gif "SimpleAdminRedeploy")  
  
 下图阐释在要更新的程序集上存在依存关系链时更新某一程序集所涉及的步骤，并且其中一个依赖的程序集存在于不同的应用程序中。  
  
 ![更新具有外部依赖项的程序集](../core/media/complexadminredeploy.gif "ComplexAdminRedeploy")  
  
> [!NOTE]
>  在更新某一程序集之前执行完全停止的原因在于，进行更新将自动取消登记业务流程，并且停止和终止所有消息。 如果您需要继续处理消息，可以部署同一程序集的不同版本，因此无需停止和终止消息。 有关详细信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
 下面的结果可能会在两个应用程序之间导致依存关系。  
  
-   **停止项目。** 如果您停止一个应用程序中另一个应用程序所依赖的项目（这可能导致停止整个应用程序），则依赖的应用程序将无法正常工作。 要停止应用程序的详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
-   **删除或更改项目的状态。** 在您添加从一个应用程序到另一个应用程序的引用，并且对其他应用程序所依赖的项目状态进行更改或删除该项目时，具有依存关系的应用程序将不会正常工作。 有关更改项目的状态的详细信息，请参阅部分中相应项目[管理项目](../core/managing-artifacts.md)。  
  
-   **导入具有依赖关系的应用程序。** 如果您想要将某一应用程序导入到不同的 BizTalk 组并在该组中运行此应用程序，则还必须导入此应用程序所依赖的所有项目。 您可以通过首先导入其他应用程序或通过将所需项目添加到需要它的应用程序，实现上述要求。 有关导入应用程序的详细信息，请参阅[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
    > [!NOTE]
    >  BizTalk Server 通过将源中的应用程序名称与目标 BizTalk 组中的名称进行匹配，确认应用程序的标识。 它并不确认您的应用程序具有依存关系的项目是否包括在其中。 在导入具有依存关系的应用程序以及它所引用的应用程序时，我们建议您确认引用的应用程序包含所需的项目。  
  
-   **导入引用的应用程序。** 如果要导入的应用程序依赖于其他应用程序中的项目，则需要添加指向此应用程序的引用。 导入向导可提供此选项。 如果你使用的 BTSTask ImportApp 命令，但是，你必须添加对导入之后, 应用程序的引用中所述[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。 在 BizTalk Server 确认存在引用的应用程序时，我们建议您采取其他步骤来确认引用的应用程序包含所需项目。  
  
-   **安装具有依赖关系的应用程序。** 在您安装某一应用程序时，还必须安装它所依赖的任何应用程序。 如果某个项目（如 BizTalk 程序集）包含在另一个应用程序中，而要安装的应用程序与该项目之间存在依存关系，则在安装该应用程序时，必须首先安装包含该项目的应用程序。 例如，如果您要安装应用程序 A，并且它依赖于应用程序 B 中的程序集，则您必须首先安装应用程序 B。 然后，你可以安装应用程序 a。有关安装应用程序的详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
-   **移动项目。** 将项目移向新应用程序时，该项目所依赖的其他所有项目也会被移动，除非此新应用程序有对包含移动项目所依赖项目的应用程序的引用。 同样，与移动项目有依存关系的所有项目也会被移动，除非包含这些项目的应用程序具有对新应用程序的引用。 移动项目时，系统会显示一起移动的其他项目的列表。 有关移动项目的说明，请参阅[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。  
  
-   **当其他应用程序中的项目依赖于它时，请更新某个项目。** 在您更新应用程序中对同一应用程序中的某一程序集具有依存关系的某一程序集时，BizTalk Server 自动执行对依赖的程序集的取消部署和重新部署。 如果您要更新一个应用程序中的某一项目，但其他应用程序中的某个项目对该项目具有依存关系，则您必须按如下所示取消部署和重新部署这个依赖的程序集：  
  
    1.  停止、取消登记和取消绑定依赖的程序集。  
  
    2.  更新它依赖的程序集。  
  
    3.  绑定、登记和启动依赖的程序集。  
  
## <a name="see-also"></a>另请参阅  
 [了解 BizTalk 应用程序部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)