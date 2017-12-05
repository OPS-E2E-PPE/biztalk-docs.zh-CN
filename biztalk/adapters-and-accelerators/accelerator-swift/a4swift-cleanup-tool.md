---
title: "A4SWIFT 清理工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: A4SWIFT Cleanup tool
ms.assetid: e694f824-6097-4d60-bc7b-b4f1a40acea0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b2d0e251bf5e8a4169ff0d86cc6635944ca12e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="a4swift-cleanup-tool"></a>A4SWIFT 清理工具
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]清理工具使你可以准备服务器具有[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]上安装的新安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。 该工具中删除协议、 部门和业务规则引擎 (BRE) 策略，如 A4SWIFT 项目，并取消部署程序集。 运行此工具使你可以避免手动删除许多 A4SWIFT 项目，并用于解决正在取消部署可能会从其他程序集引用的程序集的问题。  
  
 运行清理工具时，你可以将保留在删除项目后安装在计算机 （默认值） 或卸载 A4SWIFT A4SWIFT 选择。 在卸载 A4SWIFT 之前，应运行该工具。  
  
> [!CAUTION]
>  不要在生产环境中使用 A4SWIFT 清理工具。 该工具用于在单一服务器开发环境中，不在多服务器部署中使用。  
  
> [!NOTE]
>  默认情况下，并不适用于任何其他语言比英语才可以使用清理工具。 但是，可以修改环境，以便在本地化的计算机上的清理工具能起作用。 使用 t 参数和本地化的字符串模板文档库，例如，运行 FormPublish 工具**t:VorLagen**德语环境中。 然后可以在本地化环境中运行清理工具。  
  
 必须满足以下清理工具才能运行：  
  
-   你必须是成员[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]必须在运行该工具的服务器上安装。  
  
-   MrsrConfiguration.dll、 Shared.dll 和 RuleEngineExtension.dll 必须部署在运行该工具的服务器上。  
  
## <a name="what-the-cleanup-tool-does"></a>清理工具的功能  
 A4SWIFT 清理工具执行以下操作：  
  
-   运行**BM 取消部署**针对 ForActivities.xml 和 MRSRBAM.xml  
  
-   删除 FrrActivities_ConnectionStrings.xml 和 MRSRActivities_ConnectionStrings.xml 文件中，如果它们存在  
  
-   删除 A4SWIFT 2.1，如果存在 (如果已升级到的服务器[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，但安装程序仍保持安装 A4SWIFT 2.1) 和删除 A4SWIFT 2.1 文件夹  
  
-   取消部署所有 A4SWIFT 程序集  
  
-   删除 A4SWIFT 管理员组和 A4SWIFT 用户组  
  
-   将删除 A4SWIFT 数据库  
  
-   删除 A4SWIFT 虚拟目录  
  
-   运行完全无提示卸载[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]并删除[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]文件夹 （如果选中）  
  
 它移除项目，并取消部署程序集，如清理工具还执行以下操作：  
  
-   启动 Internet 信息服务 (IIS) 管理服务，以便运行  
  
-   停止，然后重新启动 MSSQLSERVER、 SQLSERVERAGENT、 BizTalk，和企业单一登录服务  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a>若要运行 A4SWIFT 清理工具  
  
1.  在运行 A4SWIFT 清理工具时之前, 取消部署任何 A4SWIFT 默认程序集是指任何项目。  
  
2.  打开命令提示符，并将移到\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\SDK\Tools。  
  
3.  类型**A4SWIFTCleanupTool.exe**然后按**ENTER**。  
  
    > [!NOTE]
    >  当你最初运行 A4SWIFTCleanupTool.exe 时，该工具将显示帮助屏幕中，并将提示你输入参数。 该工具将不运行，直到输入参数。  
  
4.  根据您希望该工具要执行的操作，按以下各项，之一，然后按**ENTER**:  
  
    -   **0**的执行 （默认值） 无操作  
  
    -   **1**若要删除所有本地 A4SWIFT 计算机上的资源，包括虚拟目录和注册表设置  
  
    -   **2**若要删除的 BizTalk Server 组中，包括 Sharepoint Web 文件夹、 FIN 消息模板、 BRE 策略和词汇、 BizTalk 项目，以及 A4SWIFT 数据库上的所有共享的 A4SWIFT 资源  
  
    -   **3**删除所有本地和共享资源  
  
    -   **4**用于删除所有本地和共享资源和卸载[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]产品。  
  
## <a name="see-also"></a>另请参阅  
 [工具](../../adapters-and-accelerators/accelerator-swift/tools.md)