---
title: 依赖项和应用程序部署 |Microsoft Docs
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
ms.openlocfilehash: 1b2111891b79dd343c121746db7f9959c92464df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389663"
---
# <a name="dependencies-and-application-deployment"></a>依赖项和应用程序部署
本主题介绍如何在两个或多个 BizTalk 应用程序中的项目之间的依赖关系会影响应用程序部署和维护。  
  
 当一个项目需要使用另一个项目才能正常运行时，就说要*依赖*于其他项目。 此依赖关系的一个示例是当业务流程需要使用特定架构进行消息解析或特定管道以便正确传输消息时。 在这两个方案，该业务流程是依赖于其他项目。  
  
 可以更新应用程序中的某个项目之前，您必须先取消部署它，以及依赖于它的所有项目。 项目的依赖关系存在于同一应用程序中，BizTalk Server 将自动处理更新和依赖的项目取消部署和重新部署任务。 当项目的依赖关系存在于不同的应用程序中时，但是，这不是种。 必须执行手动步骤来取消部署具有依赖项，然后才能更新所依赖的项目的项目。 之后，你必须手动重新部署依存项目。  
  
 若要无需执行这些手动步骤，当你想要更新某个项目上的其他项目所依赖，您可以尝试在同一应用程序将依赖项的所有项目放在一起。 这并不总是有可能，但是。 如中所述[项目，必须是唯一的应用程序或组](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)，大多数类型的项目必须是 BizTalk 组中唯一。 不能在同一组中的两个不同应用程序中具有相同的项目，即使这两个应用程序包含依赖于相同的项目的项目。  
  
 在此情况下，您可以将所需的项目添加到一个应用程序，然后添加对该应用程序中包含的项目的依赖于它的任何其他应用程序的引用。 时添加到应用程序的引用，请在应用程序中的项目可以使用它所引用的应用程序中的所有项目。 有关添加引用的说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
 下图描绘了两个应用程序的每个依赖于第三个应用程序中的项目。 订单处理应用程序使用 Schema1，而它包含在架构应用程序，因此 Order Processing 应用程序包含对架构应用程序的引用。 抵押应用程序使用 Schema2，它也会包含在架构应用程序，并同样以前的应用程序包含对后者的引用。  
  
 ![两个应用程序引用第三个应用程序](../core/media/applicationdependencies.gif "ApplicationDependencies")  
  
 添加到另一个应用程序的引用创建会影响部署和管理这两个应用程序的方式在两个应用程序之间的依赖项。 由于本主题后面所述的应用程序依赖关系的不同效果，我们建议你遵循有关将项目添加到应用程序的最佳实践，如中所述[部署 BizTalk 应用程序最佳做法](../core/best-practices-for-deploying-a-biztalk-application.md).  
  
 下图说明了在更新的程序集的依赖关系链，并且取决于正在更新的程序集的所有程序集存在于同一应用程序时所涉及的步骤。  
  
 ![更新的程序集具有依赖项](../core/media/simpleadminredeploy.gif "SimpleAdminRedeploy")  
  
 下图说明了在更新的程序集的被更新的程序集上的依赖关系链时所涉及的步骤和某个依赖程序集存在于不同的应用程序。  
  
 ![更新具有外部依赖项的程序集](../core/media/complexadminredeploy.gif "ComplexAdminRedeploy")  
  
> [!NOTE]
>  若要更新的程序集是自动执行此操作之前执行完全停止的原因取消登记业务流程，并停止并终止所有消息。 如果需要继续处理消息，你可以部署同一程序集的不同版本，从而避免停止和终止消息的需要。 有关详细信息，请参阅[更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)。  
  
 应用程序之间的依赖关系，可能会导致以下影响：  
  
-   **停止某一项目。** 如果您停止一个应用程序 （这可能导致停止整个应用程序） 中的项目取决于其他应用程序，将从属应用程序将无法正常工作。 有关停止应用程序的详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
-   **删除或更改项目的状态。** 如果您添加从应用程序的不同而不同的引用，对项目的另一个应用程序依赖于或删除该项目的状态进行任何更改具有依存关系的应用程序将无法正常工作。 有关更改项目的状态的详细信息，请参阅部分中针对相应项目中[管理项目](../core/managing-artifacts.md)。  
  
-   **导入具有依存关系的应用程序。** 如果你想要将应用程序导入不同的 BizTalk 组并在该组中运行它，您还必须导入此应用程序所依赖的所有项目。 通过首先导入到其他应用程序或通过将所需的项目添加到需要它的应用程序时，可以执行此操作。 有关导入应用程序的详细信息，请参阅[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
    > [!NOTE]
    >  BizTalk Server 进行匹配的源和目标 BizTalk 组中的应用程序名称来验证应用程序的标识。 它不会验证你的应用程序在其具有依赖关系的项目会包括在其中。 导入具有依存关系的应用程序和它所引用的应用程序时，我们建议你验证引用的应用程序包含所需的项目。  
  
-   **导入具有引用的应用程序。** 如果您要导入的应用程序依赖于另一个应用程序中的某个项目，您需要添加对此应用程序的引用。 导入向导提供了此选项。 如果使用 BTSTask 的 ImportApp 命令，但是，您必须添加对导入之后，应用程序的引用中所述[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。 虽然 BizTalk Server 验证引用的应用程序存在，我们建议您采取额外的步骤来验证引用的应用程序包含所需的项目。  
  
-   **安装具有依赖项的应用程序。** 在安装应用程序时，还必须安装它所依赖的任何应用程序。 当安装某个项目，如 BizTalk 程序集，其中包含在另一个应用程序中，具有一个依赖项的应用程序时必须首先安装包含该项目的应用程序。 例如，如果你想要安装应用程序 A，并且取决于应用程序 B 中的程序集，您必须首先安装应用程序 B。 然后，你可以安装应用程序 a。有关安装应用程序的详细信息，请参阅[如何安装 BizTalk 应用程序](../core/how-to-install-a-biztalk-application.md)。  
  
-   **移动项目。** 当将项目移到新的应用程序时，它在其具有依赖关系的任何其他项目也被移动，除非新的应用程序具有对包含移动的项目所依赖的项目的应用程序的引用。 此外，移动项目有依赖关系的任何项目也将被移动，除非其包含的应用程序具有对新应用程序的引用。 当移动项目，将向您显示一起移动的其他项目的列表。 有关移动项目的说明，请参阅[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。  
  
-   **更新某一项目时在另一个应用程序中的项目依赖于它。** 更新应用程序具有相同的应用程序中的某个项目的依赖关系中的项目时，BizTalk Server 会自动负责取消部署和重新部署依赖的程序集。 如果你想要更新一个应用程序中的项目，并且另一个应用程序中的项目有依赖关系，但是，你必须取消部署，并按如下所示重新部署依赖的程序集：  
  
    1.  停止、 取消登记和取消绑定依赖的程序集。  
  
    2.  更新所依赖的项目。  
  
    3.  将绑定、 登记并启动依赖的程序集。  
  
## <a name="see-also"></a>请参阅  
 [了解 BizTalk 应用程序的部署和管理](../core/understanding-biztalk-application-deployment-and-management.md)