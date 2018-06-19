---
title: 如何启动和停止 BizTalk 应用程序 |Microsoft 文档
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
ms.openlocfilehash: faacb2561b63d0e946c3408810db146e083f3e13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255589"
---
# <a name="how-to-start-and-stop-a-biztalk-application"></a>如何启动和停止 BizTalk 应用程序
本主题介绍如何使用 BizTalk Server 管理控制台启动和停止 BizTalk 应用程序。  
  
 绑定可以启动应用程序之前，必须为它包含的所有业务流程中所述配置[如何将绑定配置为业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。  
  
 启动应用程序时，可以选择如下所示的一个或多个选项：  
  
-   登记并启动所有业务流程。  
  
-   登记并启动所有发送端口。  
  
-   登记并启动所有发送端口组。  
  
-   启用所有接收位置。  
  
-   启动所有关联的主机实例。  
  
-   恢复挂起的实例。  
  
-   部署所有策略。  
  
> [!NOTE]
>  只有应用程序中已发布的策略才会自动进行部署。 如果某个策略未发布，则不会对它进行部署。  
  
 停止应用程序时，可以选择以下选项之一：  
  
-   **部分停止-允许正在运行的实例以继续。** 此选项禁用该应用程序中的所有接收位置，但会使所有其他项目保留其以前的状态不变。 这样就允许正在运行的实例处理完系统中当前存在的消息。 请注意，如果某一消息事务需要多个输入，则当您使用此选项时此消息事务可能无法完成。  
  
-   **部分停止-暂停正在运行的实例。** 此选项禁用该应用程序中的所有接收位置并停止该应用程序中的所有业务流程和发送端口。 它不会取消登记或取消部署任何项目。 如果希望临时暂停应用程序，请使用此选项。  
  
-   **完全停止-终止实例。** 此选项禁用应用程序中的所有接收位置，停止并取消登记应用程序中的所有业务流程和发送端口，并取消部署应用程序中的所有策略。 如果希望完全取消部署应用程序，请使用此选项。 请注意，任何仍在处理消息的正在运行的实例将不会完成处理。 有关详细信息，请参阅[正在取消部署的 BizTalk 应用程序](../core/undeploying-biztalk-applications.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 BizTalk 操作员可以执行部分停止，但不能执行完全停止。 此外，如果所有项目都已登记，则 BizTalk 操作员可以启动应用程序。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-start-or-stop-a-biztalk-application"></a>启动或停止 BizTalk 应用程序  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，然后展开**应用程序**。  
  
3.  右键单击你想要启动或停止，，然后单击的 BizTalk 应用**启动**或**停止**。  
  
4.  选择开始或停止的选项是你想和单击**启动**或**停止**。  
  
## <a name="see-also"></a>另请参阅  
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)   
 [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)