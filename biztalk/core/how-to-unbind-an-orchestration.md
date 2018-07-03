---
title: 取消绑定业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5673101934c4ba35deb4d63839c23e3d9cda7e4b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992622"
---
# <a name="unbind-an-orchestration"></a>取消绑定业务流程

## <a name="overview"></a>概述
本主题将介绍如何使用 BizTalk Server 管理控制台从业务流程中删除接收端口绑定、发送端口绑定或主机绑定。  
  
> [!NOTE]
>  应用程序开发人员可以使用本主题中的过程来删除业务流程的绑定。 此外可以使用 Microsoft Windows Management Instrumentation (WMI) 对象模型来创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="remove-bindings-from-an-orchestration"></a>删除从业务流程绑定  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要删除的业务流程的应用程序绑定  
  
3. 单击**业务流程**，右键单击该业务流程，单击**属性**，然后单击**绑定**的左窗格中。  
  
4. 若要删除主机绑定，请从**主机**列表中，选择 **\<None\>**。  
  
5. 若要删除接收端口绑定，从下拉列表下**接收端口**，单击 **\<None\>**。  
  
6. 若要从下的下拉列表中删除发送端口绑定**发送端口/发送端口组**，单击 **\<None\>**。  
  
7. 完成删除绑定，请单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何为业务流程配置绑定](../core/how-to-configure-bindings-for-an-orchestration.md)   
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)