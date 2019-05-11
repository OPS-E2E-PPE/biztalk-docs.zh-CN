---
title: 操作准备就绪清单 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b304b843806ed5550dd623d9980794a141083432
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400755"
---
# <a name="operational-readiness-checklists"></a>操作准备就绪清单
操作准备就绪清单包含应考虑的建议和部署 BizTalk 解决方案到生产环境之前应执行的任务。 这些清单提供信息，以便配置必备软件，从而提高可用性，监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中和用于测试的过程。  
  
 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上维护依赖关系，因此许多其他 Microsoft 技术，您应该完成每项依赖的技术来帮助确保您的生产任务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境能够顺利运行。  
  
## <a name="typical-prerequisite-software"></a>典型的必备软件  
 必备软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台通常包括以下产品：  
  
- Windows 操作系统  
  
- SQL Server 
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
- Visual Studio （适用于开发目的，不是在运行时）  
  
## <a name="additional-components"></a>其他组件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台可能还需要多个以下的软件组件：  
  
- Internet 信息服务 (IIS)  
  
- SharePoint
  
- Microsoft Office Excel 
  
  > [!NOTE]  
  >  BizTalk Server 支持 Microsoft Office 的 32 位版本。  
  
- SQL Server
  
- SQLXML 
  
- .NET Framework 
  
- 非 Microsoft 组件，以便为某些功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。  
  
  有关各种 Windows 操作系统版本的 BizTalk 应用程序平台的特定功能所需的依赖关系软件的详细信息，请参阅[新增功能、 安装、 配置和升级](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).
- 
  
## <a name="next-steps"></a>后续步骤
  
-   [清单：BizTalk Server 入门](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [清单：配置 Windows Server](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [清单：配置 Internet Information Services](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [清单：配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [清单：配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [清单：提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [清单：监视操作准备情况](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [清单：维护和故障排除 BizTalk Server 数据库](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [清单：测试操作准备情况](../technical-guides/checklist-testing-operational-readiness.md)