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
ms.openlocfilehash: e31ec8af7f8c5dd785b471654e9a9cfd7446bbf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998942"
---
# <a name="manage-role-links"></a>管理角色链接

## <a name="overview"></a>概述
本部分说明如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来管理 BizTalk 应用程序中的角色链接。 角色链接定义商业交易参与方之间的关系并指定双向交互中使用的消息类型和端口类型。 角色链接的背景信息，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  

## <a name="added-to-application"></a>添加到应用程序  
 角色链接内置于[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并编译到 BizTalk 程序集。 不能向应用程序中单独地添加角色链接，而应按照以下方式向应用程序中添加角色链接：  
  
- 添加 BizTalk 程序集包含角色链接的应用程序，如中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
- 某一.msi 文件导入包含 BizTalk 程序集包含角色链接，如中所述的应用程序[导入 BizTalk 应用程序的方式](../core/how-to-import-a-biztalk-application.md)。  
  
- 当开发人员部署到应用程序包含角色链接中的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如中所述[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

## <a name="deploy-to-production"></a>部署到生产环境  
 BizTalk 应用程序开发人员创建角色链接以实现商业交易中两个或多个参与方（如您的组织与供应商）之间的通信。 开发人员不必指定参与交易的参与方，只需指定他们的角色。 若要将包含角色链接的应用程序部署到生产环境，并启用参与方之间的实际通信，必须执行以下配置，如本部分中所述：  
  
- 必须为参与方分配一个角色链接中定义的角色（如果在开发过程中未指定）。 此操作称为“登记”参与方的角色。 登记后，如果您希望该参与方不再是指定的角色，则可以取消登记该参与方。  
  
- 角色链接中定义的每个参与方的逻辑端口都必须绑定到应用程序的宿主 BizTalk 主机实例上的物理端口。  
  
  有关开发角色链接的详细信息，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
## <a name="next-step"></a>下一步
  
-   [如何登记或取消登记角色参与方](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)