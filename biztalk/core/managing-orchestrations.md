---
title: "管理业务流程 |Microsoft 文档"
description: "若要使用业务流程在 BizTalk Server 中，包括启动、 停止、 绑定、 配置、 启用跟踪，挂起的链接和的详细信息"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cd12c202822c4d9ff849cc762b55e8f4880d80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-orchestrations"></a>管理业务流程

## <a name="overview"></a>概述
本部分说明如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来管理业务流程。 业务流程是一个可执行的业务程序。 有关业务流程的背景信息，请参阅[业务流程](../core/orchestrations.md)。  

## <a name="add-to-application"></a>将添加到应用程序  
 业务流程内置于[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和编译到 BizTalk 程序集中。 不能向应用程序中单独地添加业务流程，而应按照以下方式向应用程序中添加业务流程：  
  
-   当你添加 BizTalk 程序集包含应用程序，业务流程中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
-   当你导入的应用程序中所述包括 BizTalk 程序集包含业务流程，.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
-   当开发人员将部署到应用程序包含从业务流程的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中所述，[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

## <a name="biztalk-administration-tasks"></a>BizTalk 管理任务  
 如本部分所述，使用管理控制台可执行以下操作：  
  
-   通过将业务流程绑定到适当的发送端口、接收端口和主机，可配置业务流程绑定，或删除业务流程绑定。  
  
-   为业务流程配置消息跟踪。  
  
-   查看业务流程的实例信息。  
  
-   将业务流程登记到适当的主机，或从主机取消登记业务流程。  
  
-   启动或停止业务流程，以便启动或停止消息的处理过程。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
> [!NOTE]
>  开发人员使用业务流程设计器用于创建业务流程中, 所述[创建业务流程使用 Orchestration 设计器](../core/creating-orchestrations-using-orchestration-designer.md)。 开发人员可以通过在开发过程中使用管理控制台来管理业务流程，如本部分所述。  
  
## <a name="next-steps"></a>后续步骤
  
-   [为业务流程配置绑定](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [取消绑定某个业务流程](../core/how-to-unbind-an-orchestration.md)  
  
-   [配置业务流程的跟踪](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [查看为业务流程的的实例信息](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [删除从应用程序的业务流程](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [登记业务流程](../core/how-to-enlist-an-orchestration.md)  
  
-   [取消登记业务流程](../core/how-to-unenlist-an-orchestration.md)  
  
-   [启动业务流程](../core/how-to-start-an-orchestration.md)  
  
-   [停止一个业务流程](../core/how-to-stop-an-orchestration.md)  
  
-   [挂起、 恢复和终止业务流程实例](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [升级业务流程](../core/how-to-upgrade-an-orchestration.md)