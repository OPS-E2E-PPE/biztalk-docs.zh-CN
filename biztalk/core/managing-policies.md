---
title: "管理策略 |Microsoft 文档"
description: "快速链接要导入，发布、 添加、 部署、 删除或导出 BizTalk Server 中的策略"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d49f0343c324900bf10c2efcce46cd57682ed04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-policies"></a>管理策略

## <a name="overview"></a>概述
本部分中的主题提供有关使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理策略的说明。 策略是业务规则的逻辑分组。 策略的背景信息，请参阅[策略](../core/policies.md)。  
  
## <a name="import-publish-deploy-and-remove-policies"></a>导入、 发布、 部署和删除策略
 解决方案开发人员可以创建和使用业务规则编辑器中，查看策略中所述[创建业务规则使用业务规则编辑器](../core/creating-business-rules-using-the-business-rule-composer.md)。 然后，开发人员和 IT 管理员可以执行以下任务（如本部分的各主题中所述），以便在某个 BizTalk 组和应用程序中部署并管理策略：  
  
-   **将策略导入到 BizTalk 组。** 执行此操作时，该策略添加到组的规则引擎数据库，并在中的 BizTalk Server 管理控制台中显示\<所有项目 > BizTalk 组的节点。 导入操作不会使该策略针对任何特定应用程序生效。 您必须先发布策略，将其添加到应用程序中，然后进行部署，如本部分其他主题中所述。 规则引擎数据库是包含某个 BizTalk 组中的所有策略的数据库。  
  
-   **发布策略。** 这将使它可以在 BizTalk 应用程序中使用。  
  
-   **将策略添加到 BizTalk 应用程序。** 这使得应用程序可以使用该策略，但不会使策略生效。 策略在部署后才能生效。  
  
    > [!IMPORTANT]
    >  如果有两个或更多应用程序共享一个策略，应创建一个单独的应用程序以包含此策略，然后创建从使用该策略的应用程序到包含该策略的应用程序的引用。 这是因为，如果您停止一个包含策略的应用程序，该策略将自动取消部署，并且不能再为使用它的任何应用程序发挥作用。  
  
-   **部署策略。** 这将使策略生效。 （这类似于启动一个业务流程。）您可以手动部署或取消部署策略。 此外，启动应用程序时会自动部署其策略，停止应用程序时会自动取消部署其策略。  
  
    > [!NOTE]
    >  部署策略后，不能再对其进行修改。 如果希望修改部署的策略，必须取消其部署，或者使用业务规则编辑器重新创建它，并为其指定一个新版本号。  
  
-   **从 BizTalk 应用程序和 BizTalk 组中删除策略。** 这将取消策略的部署并将其从应用程序以及该组的规则引擎数据库中删除。  
  
-   **将策略导出。** 导出策略后，可以将其导入不同的 BizTalk 组进行使用。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [导入策略](../core/how-to-import-a-policy.md)  
  
-   [发布策略](../core/how-to-publish-a-policy.md)  
  
-   [将策略添加到应用程序](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [配置策略的跟踪](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [从应用程序和 BizTalk 组中删除策略](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [导出策略](../core/how-to-export-a-policy.md)