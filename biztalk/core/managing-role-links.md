---
title: 管理角色链接 |Microsoft 文档
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
ms.openlocfilehash: 07f85bfe0d16b3963b0ba18585220f508f679346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262629"
---
# <a name="manage-role-links"></a>管理角色的链接

## <a name="overview"></a>概述
本部分说明如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来管理 BizTalk 应用程序中的角色链接。 角色链接定义商业交易参与方之间的关系并指定双向交互中使用的消息类型和端口类型。 在角色链接上的背景信息，请参阅[在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  

## <a name="added-to-application"></a>添加到应用程序  
 内置角色链接[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和编译到 BizTalk 程序集中。 不能向应用程序中单独地添加角色链接，而应按照以下方式向应用程序中添加角色链接：  
  
-   当你添加 BizTalk 程序集包含应用程序，角色链接中所述[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
-   当你导入的应用程序中所述包括 BizTalk 程序集包含角色链接，.msi 文件[如何导入 BizTalk 应用程序](../core/how-to-import-a-biztalk-application.md)。  
  
-   当开发人员将部署到应用程序包含中的角色链接的程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]中所述，[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)。  

## <a name="deploy-to-production"></a>部署到生产环境  
 BizTalk 应用程序开发人员创建角色链接以实现商业交易中两个或多个参与方（如您的组织与供应商）之间的通信。 开发人员不必指定参与交易的参与方，只需指定他们的角色。 若要将包含角色链接的应用程序部署到生产环境，并启用参与方之间的实际通信，必须执行以下配置，如本部分中所述：  
  
-   必须为参与方分配一个角色链接中定义的角色（如果在开发过程中未指定）。 此操作称为“登记”参与方的角色。 登记后，如果您希望该参与方不再是指定的角色，则可以取消登记该参与方。  
  
-   角色链接中定义的每个参与方的逻辑端口都必须绑定到应用程序的宿主 BizTalk 主机实例上的物理端口。  
  
 有关开发角色链接的详细信息，请参阅[在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
## <a name="next-step"></a>下一步
  
-   [如何登记或取消登记角色方](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)