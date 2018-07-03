---
title: 管理业务流程 |Microsoft Docs
description: 若要使用业务流程在 BizTalk Server 中，包括启动、 停止、 绑定、 配置、 启用跟踪、 挂起的链接和的详细信息
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a989cb7853e63e1e603febf44db45288276ecd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976478"
---
# <a name="manage-orchestrations"></a>管理业务流程

## <a name="overview"></a>概述
本部分说明如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来管理业务流程。 业务流程是一个可执行的业务程序。 有关业务流程的背景信息，请参阅[业务流程](../core/orchestrations.md)。  

## <a name="add-to-application"></a>将添加到应用程序  
 业务流程内置的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。 不能向应用程序中单独地添加业务流程，而应按照以下方式向应用程序中添加业务流程：  
  
- 当添加包含到应用程序，业务流程的 BizTalk 程序集，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
- 某一.msi 文件导入包含 BizTalk 程序集包含业务流程中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
- 当开发人员部署到应用程序包含从业务流程的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

## <a name="biztalk-administration-tasks"></a>BizTalk 管理任务  
 如本部分所述，使用管理控制台可执行以下操作：  
  
-   通过将业务流程绑定到适当的发送端口、接收端口和主机，可配置业务流程绑定，或删除业务流程绑定。  
  
-   为业务流程配置消息跟踪。  
  
-   查看业务流程的实例信息。  
  
-   将业务流程登记到适当的主机，或从主机取消登记业务流程。  
  
-   启动或停止业务流程，以便启动或停止消息的处理过程。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
> 
> [!NOTE]
>  开发人员使用业务流程设计器来创建业务流程，如中所述[业务流程使用业务流程设计器创建](../core/creating-orchestrations-using-orchestration-designer.md)。 开发人员可以通过在开发过程中使用管理控制台来管理业务流程，如本部分所述。  
  
## <a name="next-steps"></a>后续步骤
  
-   [为业务流程配置绑定](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [取消绑定业务流程](../core/how-to-unbind-an-orchestration.md)  
  
-   [为业务流程配置跟踪](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [查看业务流程的实例信息](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [从应用程序中删除业务流程](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [登记业务流程](../core/how-to-enlist-an-orchestration.md)  
  
-   [取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)  
  
-   [启动业务流程](../core/how-to-start-an-orchestration.md)  
  
-   [停止业务流程](../core/how-to-stop-an-orchestration.md)  
  
-   [暂停、恢复和终止业务流程实例](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [更新业务流程](../core/how-to-upgrade-an-orchestration.md)