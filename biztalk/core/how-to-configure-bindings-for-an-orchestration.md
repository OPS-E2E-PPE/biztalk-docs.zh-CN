---
title: 为业务流程配置绑定 |Microsoft Docs
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
ms.openlocfilehash: 6de8d8626dbe0ad110e46d399c32f2dc9ba8a321
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386313"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a>如何为业务流程配置绑定

## <a name="overview"></a>概述
本主题介绍如何使用 BizTalk Server 管理控制台为业务流程配置绑定。 这涉及到为业务流程到过渡或生产环境中的物理端口定义，以及将业务流程绑定到主机的逻辑端口绑定。 如果业务流程已绑定，可以使用此过程来更改绑定。  
  
 配置绑定后，您可以登记业务流程，然后启动它，以便开始处理消息。 有关执行这些任务的说明，请参阅[如何登记业务流程](../core/how-to-enlist-an-orchestration.md)并[如何启动业务流程](../core/how-to-start-an-orchestration.md)。  
  
> [!NOTE]
>  应用程序开发人员可以配置为业务流程的绑定，以通过使用本主题中的过程在开发过程中测试其功能。 此外可以使用 Microsoft Windows Management Instrumentation (WMI) 对象模型来创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="configure-bindings-for-an-orchestration"></a>为业务流程配置绑定  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含所需的业务流程的应用程序配置绑定  
  
3. 单击**业务流程**，右键单击您要为其配置绑定，然后单击该业务的流程**属性**。  
  
4. 单击**绑定**选项卡上，并从**主机**列表中，选择要登记业务流程的主机。  
  
5. 从下拉列表中列出了**接收端口**列中的，每个入站逻辑端口旁边，选择你想要将逻辑端口绑定的接收端口。  
  
6. 从下拉列表中**发送端口/发送端口组**列中的，每个入站逻辑端口旁边，选择你想要将逻辑端口绑定，然后单击发送端口**确定**。  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何取消绑定业务流程](../core/how-to-unbind-an-orchestration.md)   
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)