---
title: A4SWIFT 清理工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- A4SWIFT Cleanup tool
ms.assetid: e694f824-6097-4d60-bc7b-b4f1a40acea0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db6e9f6f6ec25762abc4416bc18f0955055b7e70
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983614"
---
# <a name="a4swift-cleanup-tool"></a>A4SWIFT 清理工具
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]清理工具，您可以准备了 Microsoft 的服务器[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]的新安装上安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。 该工具删除 A4SWIFT 项目，例如协议、 部门和业务规则引擎 (BRE) 策略，并取消部署程序集。 运行此工具使你可以避免手动删除许多 A4SWIFT 项目，并用于解决可能与其他程序集引用的取消部署程序集的问题。  
  
 当您运行清理工具时，您可以保留 A4SWIFT 安装上的计算机 （默认值） 或卸载 A4SWIFT 后删除这些项目的选择。 您应卸载 A4SWIFT 之前运行该工具。  
  
> [!CAUTION]
>  在生产环境中不使用 A4SWIFT 清理工具。 该工具用于在单一服务器开发环境，不在多服务器部署中使用。  
  
> [!NOTE]
>  默认情况下，清理工具不适用于任何其他语言比英语。 但是，可以修改环境，以便清理工具适用于本地化的计算机。 使用 t 参数和已本地化的字符串的模板文档库，例如，运行 FormPublish 工具**t:VorLagen**正使用德语的环境中。 然后可以在本地化环境中运行清理工具。  
  
 必须满足以下用于运行清理工具：  
  
- 您必须是成员[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
- [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] 必须在运行该工具的服务器上安装。  
  
- MrsrConfiguration.dll、 Shared.dll 和 RuleEngineExtension.dll 必须部署在运行该工具的服务器上。  
  
## <a name="what-the-cleanup-tool-does"></a>清理工具的功能  
 A4SWIFT 清理工具执行以下操作：  
  
- 运行**BM 取消部署**针对 ForActivities.xml 和 MRSRBAM.xml  
  
- 如果它们存在，删除 FrrActivities_ConnectionStrings.xml 和 MRSRActivities_ConnectionStrings.xml 文件  
  
- 删除 A4SWIFT 2.1，如果它存在 (如果已升级到服务器[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，但安装仍保持 A4SWIFT 2.1 安装)，并删除 A4SWIFT 2.1 文件夹  
  
- 取消部署所有 A4SWIFT 程序集  
  
- 将删除 A4SWIFT 管理员组的 A4SWIFT 用户组  
  
- 删除 A4SWIFT 数据库  
  
- 删除 A4SWIFT 虚拟目录  
  
- 运行完全无提示卸载[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]，并删除[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]文件夹 （如果选择）  
  
  因为它会删除项目，并取消部署程序集，清理工具还执行以下操作：  
  
- 若要运行启动 Internet Information Services (IIS) 管理服务  
  
- 停止并重新启动 MSSQLSERVER、 SQLSERVERAGENT、 BizTalk，和企业单一登录服务  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a>若要运行 A4SWIFT 清理工具  
  
1. 在运行之前 A4SWIFT 清理工具，取消部署任何 A4SWIFT 默认程序集是指任何项目。  
  
2. 打开命令提示符，并将移动到\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools。  
  
3. 类型**A4SWIFTCleanupTool.exe** ，然后按**ENTER**。  
  
   > [!NOTE]
   >  在最初运行 A4SWIFTCleanupTool.exe 时，该工具显示帮助屏幕，并提示您输入参数。 该工具将不运行，直到输入参数。  
  
4. 根据您希望该工具执行的操作，按以下项之一，然后按**ENTER**:  
  
   - **0**的执行 （默认值） 无操作  
  
   - **1**若要删除的计算机上，包括虚拟目录和注册表设置的所有本地 A4SWIFT 资源  
  
   - **2**若要删除的 BizTalk Server 组中，包括 Sharepoint Web 文件夹、 FIN 消息模板、 BRE 策略和词汇、 BizTalk 项目和 A4SWIFT 数据库上的所有共享的 A4SWIFT 资源  
  
   - **3**若要删除所有本地和共享资源  
  
   - **4**若要删除所有本地和共享资源并卸载[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]产品。  
  
## <a name="see-also"></a>请参阅  
 [工具](../../adapters-and-accelerators/accelerator-swift/tools.md)