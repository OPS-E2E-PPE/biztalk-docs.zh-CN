---
title: 为业务流程配置绑定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9724a3a0-c217-4f98-b6d9-21f788ce50ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb695f9636327107887397372d5fc2dda74e4eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248917"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a>如何配置适用于业务流程的绑定

## <a name="overview"></a>概述
本主题将介绍如何使用 BizTalk Server 管理控制台为业务流程配置绑定。 这包括在过渡环境或生产环境中将为业务流程定义的逻辑端口绑定到物理端口，以及将业务流程绑定到主机。 如果业务流程已绑定，则使用此过程可以更改这些绑定。  
  
 配置绑定后，可以登记业务流程，然后启动它，以使该业务流程开始处理消息。 有关执行这些任务的说明，请参阅[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)和[如何启动 Orchestration](../core/how-to-start-an-orchestration.md)。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来为业务流程配置绑定。 你可以使用 Microsoft Windows Management Instrumentation (WMI) 对象模型来创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="configure-bindings-for-an-orchestration"></a>为业务流程配置绑定  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含要为其业务的流程的应用程序配置绑定  
  
3.  单击**业务流程**，右键单击你想要配置的绑定，，然后单击业务的流程**属性**。  
  
4.  单击**绑定**选项卡上，并从**主机**列表中，选择在用于登记业务流程的上的主机。  
  
5.  从下拉列表列出了在**接收端口**列中，每个入站的逻辑端口旁选择你想要绑定的逻辑端口接收端口。  
  
6.  从下拉列表中**发送端口/发送端口组**列中，每个入站的逻辑端口旁选择你想要将绑定的逻辑端口，然后单击发送端口**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何取消绑定某个业务流程](../core/how-to-unbind-an-orchestration.md)   
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)