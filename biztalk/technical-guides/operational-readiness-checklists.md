---
title: "操作的准备工作核对清单 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c308a876-9872-43b3-a1fb-76e81396612f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87da295129a4cb90ecf643cd06eb18ac3e6aa18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operational-readiness-checklists"></a>操作的准备工作核对清单
操作的准备情况清单包含应考虑的建议和在 BizTalk 解决方案部署到生产环境之前应执行的任务。 这些清单包括用于配置必备软件，提高可用性，信息监视[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，并用于测试的步骤。  
  
 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上维护依赖关系，因此许多其他 Microsoft 技术，您应该完成的任务的每个相关的技术，以帮助确保你的生产[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平稳运行环境。  
  
## <a name="typical-prerequisite-software"></a>典型的必备软件  
 有关必备软件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台通常包括以下产品：  
  
-   Windows 操作系统  
  
-   [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]SP1 或[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]  
  
-   [!INCLUDE[vs2010](../includes/vs2010-md.md)]（出于开发目的，不在运行时）  
  
## <a name="additional-components"></a>其他组件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序平台可能还需要多个以下的软件组件：  
  
-   Internet 信息服务 (IIS)  
  
-   Windows SharePoint® Services 2010  
  
-   SharePoint Foundation 2010  
  
-   Microsoft Office SharePoint Server 2007 Service Pack 1 (SP1) (MOSS)  
  
-   SP1 或 SP2 的 Windows SharePoint Services 3.0  
  
-   Microsoft Office Excel 2010 或 2007  
  
    > [!NOTE]  
    >  [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]支持 Microsoft Office 2010 的 32 位版本。  
  
-   SQL Server 2005 Notification Services  
  
-   带有 Service Pack 1 的 SQLXML 4.0  
  
-   .NET framework 1.0  
  
-   .NET Framework 2.0  
  
-   .NET framework 3.0  
  
-   Microsoft.NET Framework 4 和.Net Framework 3.5 Service Pack 1 (SP1)  
  
-   非 Microsoft 组件，以便为某些功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器。  
  
 有关依赖软件所需的各种 Windows 操作系统版本的 BizTalk 应用程序平台的特定功能的详细信息，请参阅中的"功能依赖关系矩阵"一节[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装和升级为特定的 Windows 操作系统版本的指南。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]安装和升级指南位于[http://go.microsoft.com/fwlink/?LinkID=152913](http://go.microsoft.com/fwlink/?LinkID=152913)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [清单： BizTalk Server 入门](http://msdn.microsoft.com/library/37d265cd-c393-46ac-ac21-129a1511359b)  
  
-   [清单： 配置 Windows Server](../technical-guides/checklist-configuring-windows-server.md)  
  
-   [清单： 配置 Internet Information Services](../technical-guides/checklist-configuring-internet-information-services.md)  
  
-   [清单： 配置 SQL Server](~/technical-guides/checklist-configuring-sql-server.md)  
  
-   [清单： 配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)  
  
-   [清单： 会提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)  
  
-   [清单： 提高可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)  
  
-   [清单： 监视操作的准备情况](../technical-guides/checklist-monitoring-operational-readiness.md)  
  
-   [清单： 维护和故障排除 BizTalk Server 数据库](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)  
  
-   [清单： 测试操作的准备情况](../technical-guides/checklist-testing-operational-readiness.md)