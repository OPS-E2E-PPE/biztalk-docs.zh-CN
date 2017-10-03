---
title: "如何取消登记业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, unenlisting
- enlisting, unenlisting
- managing [orchestrations], unenlisting
- unenlisting, orchestrations
ms.assetid: 038ed7bb-615c-4e4e-a5bb-79de2626de77
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c55f0f7daee927e90e514cb7b566b058cee8044a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-unenlist-an-orchestration"></a>如何取消登记业务流程
本主题介绍如何使用 BizTalk Server 管理控制台来取消登记业务流程。 取消登记业务流程从主机中删除它。 这将删除订阅，因此该业务流程将不再处理消息。 在编辑业务流程的绑定前，必须先对该业务流程进行取消登记。  
  
 你可以取消登记业务流程之前，你必须终止任何正在运行的实例中所述[如何挂起、 继续和终止业务流程实例](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来取消登记业务流程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-unenlist-an-orchestration"></a>若要取消登记业务流程  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含你想要取消登记业务流程的应用程序。  
  
3.  单击**业务流程**，右键单击以取消登记，然后单击业务流程**Unenlist**。  
  
    > [!NOTE]
    >  要在一次取消登记多个业务流程，请按住 shift 键，并选择要取消登记每个业务流程业务流程，右键单击，然后单击**Unenlist**。  
  
## <a name="see-also"></a>另请参阅  
 [管理业务流程](../core/managing-orchestrations.md)   
 [如何登记业务流程](../core/how-to-enlist-an-orchestration.md)   
 [部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)