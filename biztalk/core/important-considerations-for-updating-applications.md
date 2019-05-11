---
title: 有关更新应用程序的重要注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- updating, applications
- applications, planning
- applications, updating
- planning, applications
- planning, updating
- updating, planning
ms.assetid: e7690bdf-943d-4bb6-b8cd-a6841b722d40
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39b3bdd5d939edd1fa1d930d5711f8bac8a8f71c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382587"
---
# <a name="important-considerations-for-updating-applications"></a>有关更新应用程序的重要注意事项
以下是更新应用程序，尤其是在生产环境中运行的是之前要考虑的重要问题。  
  
## <a name="general-considerations"></a>一般注意事项  
  
-   参与方和规则是在组作用域中可见，因此添加其他参与方和规则可能会中断其他应用程序。  
  
-   如果取消部署的其他项目所依赖的项目依赖的程序集必须首先取消部署。  
  
    > [!NOTE]
    >  在 BizTalk Server 管理控制台将显示一条警告，并阻止您从错误的顺序取消部署项目。  
  
-   如果更新现有应用程序中的 BizTalk 程序集时，可能需要重新启动主机实例以使更改生效。 重新启动主机实例停止所有主机实例运行其他应用程序。  
  
-   如果你使用 Visual Studio 部署到生产环境中 （我们强烈建议不要这样做） 的应用程序和项目属性中重新启动主机实例选项设置为 True，所有主机实例时部署应用程序，将重新都启动包括那些不与此应用程序相关联。 这将停止所有本地计算机上的任何主机实例运行其他应用程序。  
  
-   如果你想要更新 BizTalk Server 程序集 （包含业务流程、 架构或映射） 为 BizTalk 应用程序部署，可以执行以下任一操作：  
  
    -   执行的并行部署。 适当地可以通过递增版本号通常修改的较新的程序集。 这样，两个具有不同的完全限定程序集名称的程序集。 有关详细信息，请参阅[如何部署到运行的并排方案与现有版本的应用程序的新版本](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md)。  
  
    -   现有的 BizTalk Server 程序集替换为新的程序集。 必须停止所有主机实例可能加载过期程序集、 替换过期程序集位于 GAC 中的并然后重新启动主机实例。  
  
-   如果部署全新的应用程序以替换现有应用程序，你必须更正其他应用程序以及要替换的应用程序之间的所有引用。  
  
## <a name="considerations-for-updating-schemas"></a>更新架构的注意事项  
  
-   如果向 BizTalk 组中包括的新架构具有与现有架构相同的消息类型的应用程序添加程序集，管道中发生架构解析时将使用具有最高版本号的架构。 此外，如果一种消息类型所引用的多个.NET 类型，此二义性可能会导致管道执行失败。 这是实例的因为架构查找使用的消息类型、 目标命名空间和根的名称。 这可能与新的架构相同的消息类型与使用的架构的任何应用程序中的管道。 有关架构解析的详细信息，请参阅[管道组件中的架构解析](../core/schema-resolution-in-pipeline-components.md)。  
  
-   更新架构时，还必须依赖于架构的任何业务流程以及更新引用架构 （或创建新映射） 的映射。  
  
-   如果递增的架构版本，则应更新架构以了解任何管道实例和管道组件使用它的引用。  
  
-   取消部署架构会导致该架构的以前版本，如果可用，变为活动状态。  
  
## <a name="considerations-for-updating-policies"></a>更新策略的注意事项  
  
-   BizTalk Server 运行时使用的策略处于已部署状态的最高版本。  
  
## <a name="see-also"></a>请参阅  
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)