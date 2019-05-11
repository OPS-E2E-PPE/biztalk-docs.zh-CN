---
title: 如何启动和停止 BizTalk 应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting
- starting, applications
- managing [applications], starting
- managing [applications], stopping
- applications, starting
- stopping, applications
- applications, stopping
- stopping
ms.assetid: f9f83e99-a1e2-4dfd-b3be-60d3ec2cbcc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c696583f8e08ad9588e4e00fed24151646a727ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334093"
---
# <a name="how-to-start-and-stop-a-biztalk-application"></a>如何启动和停止 BizTalk 应用程序
本主题介绍如何使用 BizTalk Server 管理控制台来启动和停止 BizTalk 应用程序。  
  
 如中所述，可以启动应用程序之前，必须为它所包含的所有业务流程中配置绑定[如何配置业务流程的绑定](../core/how-to-configure-bindings-for-an-orchestration.md)。  
  
 启动应用程序时，可以按如下所示选择一个或多个以下选项：  
  
-   登记并启动所有业务流程。  
  
-   登记并启动所有发送端口。  
  
-   登记并启动所有发送端口组。  
  
-   启用所有接收位置。  
  
-   启动所有关联的主机实例。  
  
-   恢复挂起的实例。  
  
-   部署所有策略。  
  
> [!NOTE]
>  仅在应用程序中已发布的策略自动部署。 如果策略未发布，它将不部署。  
  
 当你停止应用程序时，可以选择下列选项之一：  
  
-   **部分停止-允许正在运行的实例以继续。** 此选项将禁用所有应用程序中的接收位置，但在其以前的状态中保留所有其他项目。 这允许正在运行的实例来完成当前正在系统处理消息。 请注意，是否消息事务需要多个输入，它可能不能使用此选项时完成。  
  
-   **部分停止-挂起正在运行的实例。** 此选项禁用所有接收位置并停止所有业务流程和发送端口的应用程序中。 它不会取消登记或取消部署任何项目。 如果你想要暂时暂停应用程序，请使用此选项。  
  
-   **完全停止-终止实例。** 此选项将禁用所有接收位置，停止和取消登记所有业务流程和发送端口，并取消部署该应用程序中的所有策略。 如果你想要完全取消部署应用程序，请使用此选项。 请注意任何正在运行的实例仍在处理消息，将无法完成处理。 有关详细信息，请参阅[正在取消部署 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 BizTalk 操作员可以执行部分停止，但不是完全停止。 此外，BizTalk 操作员可以启动应用程序，如果所有项目都已都登记。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-start-or-stop-a-biztalk-application"></a>若要启动或停止 BizTalk 应用程序  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。  
  
3. 右键单击你想要启动或停止，，然后单击 BizTalk 应用程序**启动**或**停止**。  
  
4. 选择开始或停止选项，并单击**启动**或**停止**。  
  
## <a name="see-also"></a>请参阅  
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)   
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)