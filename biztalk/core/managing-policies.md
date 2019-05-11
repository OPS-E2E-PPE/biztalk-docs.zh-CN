---
title: 管理策略 |Microsoft Docs
description: 快速链接以便在导入，发布、 添加、 部署、 删除或导出 BizTalk Server 中的策略
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7b3bf92-8868-4c35-953f-61a7f2edff9c
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99c3dbc60bde3fdf82dc44a68e34345d3225b92c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380274"
---
# <a name="manage-policies"></a>管理策略

## <a name="overview"></a>概述
在本部分中的主题提供有关使用 BizTalk Server 管理控制台或 BTSTask 命令行工具来管理策略的说明。 策略是业务规则的逻辑分组。 有关策略的背景信息，请参阅[策略](../core/policies.md)。  
  
## <a name="import-publish-deploy-and-remove-policies"></a>导入、 发布、 部署和删除策略
 解决方案开发人员可以创建和使用业务规则编辑器中，查看策略，如中所述[使用业务规则编辑器创建业务规则](../core/creating-business-rules-using-the-business-rule-composer.md)。 然后，开发人员和 IT 管理员可以执行以下任务，在本部分中，若要部署和管理 BizTalk 组和应用程序中的策略中的主题中所述：  
  
-   **将策略导入 BizTalk 组。** 执行此操作时，策略添加到组的规则引擎数据库和 BizTalk Server 管理控制台中显示\<的所有项目\>BizTalk 组节点。 这不会使策略生效的任何特定应用程序。 必须先发布策略，将其添加到应用程序，并部署它，如本部分中的其他主题中所述。 规则引擎数据库是包含所有 BizTalk 组中的策略的数据库。  
  
-   **发布策略。** 这使得可以在 BizTalk 应用程序中使用。  
  
-   **将策略添加到 BizTalk 应用程序。** 这允许应用程序使用策略，但不会使策略生效。 在部署时，该策略将生效。  
  
    > [!IMPORTANT]
    >  如果在两个或多个应用程序之间共享一个策略，则应创建单独的应用程序以包含此策略，然后创建从使用策略来包含该策略的应用程序的应用程序引用。 这是因为如果停止包含策略的应用程序，该策略将自动取消部署并不再为任何应用程序使用它的函数。  
  
-   **部署策略。** 执行此操作会将其放到操作。 （这类似于启动业务流程。）可以部署和手动取消部署策略。 此外，当启动应用程序时，会自动部署其策略，并且其策略应用程序停止时，会自动取消部署。  
  
    > [!NOTE]
    >  一旦部署了策略，可以再修改。 如果你想要修改已部署的策略，必须取消部署它，或通过使用业务规则编辑器重新创建对象并为其提供新的版本号。  
  
-   **从 BizTalk 应用程序和 BizTalk 组中删除策略。** 这将取消部署策略，并将其删除应用程序和组的规则引擎数据库中。  
  
-   **导出策略。** 然后，可以将其导入其他 BizTalk 组进行使用。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="next-steps"></a>后续步骤
  
-   [导入策略](../core/how-to-import-a-policy.md)  
  
-   [发布策略](../core/how-to-publish-a-policy.md)  
  
-   [向应用程序添加策略](../core/how-to-add-a-policy-to-an-application.md)  
  
-   [部署或取消部署策略](../core/how-to-deploy-or-undeploy-a-policy.md)  
  
-   [为策略配置跟踪](../core/how-to-configure-tracking-for-a-policy.md)  
  
-   [从应用程序和 BizTalk 组中删除策略](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [导出策略](../core/how-to-export-a-policy.md)