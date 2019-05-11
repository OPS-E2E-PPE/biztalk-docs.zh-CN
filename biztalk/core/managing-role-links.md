---
title: 管理角色链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8860e11-3d2c-450f-a7d2-cc116478999c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 358f98e35503abeceb41d8e0f799044ceb6539b8
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530369"
---
# <a name="manage-role-links"></a>管理角色链接

## <a name="overview"></a>概述
本部分说明了使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来管理 BizTalk 应用程序中的角色链接。 角色链接定义商业交易中所涉及参与方之间的关系，并指定双向交互中使用的消息和端口类型。 角色链接的背景信息，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  

## <a name="added-to-application"></a>添加到应用程序  
 角色链接内置于[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。 不能单独; 添加到应用程序的角色链接角色链接添加到应用程序，如下所示：  
  
- 添加 BizTalk 程序集包含角色链接的应用程序，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
- 某一.msi 文件导入包含 BizTalk 程序集包含角色链接，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
- 当开发人员部署到应用程序包含角色链接中的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

## <a name="deploy-to-production"></a>部署到生产环境  
 BizTalk 应用程序开发人员创建角色链接，以实现业务事务，例如你的组织和供应商中涉及的两个或多个参与方之间的通信。 开发人员不一定是指定在事务中，仅其角色所涉及的参与方。 若要部署的应用程序包含角色链接到生产环境并启用参与方之间的实际通信，下面的配置必须执行，如本部分中所述：  
  
- 如果它未按时完成开发过程中，一个参与方必须分配到角色链接中定义的每个角色。 这称为"登记"参与方的角色。 如果不再需要该参与方分配的角色，可以稍后取消登记参与方。  
  
- 将托管应用程序的 BizTalk 主机实例上，每个参与方的角色链接中定义的逻辑端口必须绑定到物理端口。  
  
  有关开发角色链接的详细信息，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
## <a name="next-step"></a>下一步
  
-   [如何登记或取消登记角色参与方](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)