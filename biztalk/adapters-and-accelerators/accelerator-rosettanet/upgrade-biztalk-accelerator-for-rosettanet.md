---
title: "升级在 BizTalk Server 中的 RosettaNet 快捷键 (BTARN) |Microsoft 文档\""
description: "请按照更新 BTARN 到 BizTalk Server 中的当前版本的升级步骤"
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
ms.author: mandia
ms.openlocfilehash: 16e6083f3e5fb1778d77536cd602ee2208c0005f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-the-rosettanet-accelerator"></a>升级 RosettaNet 快捷键

## <a name="upgrade-overview"></a>升级概述
可以将 BizTalk Accelerator for RosettaNet (BTARN) 安装以前版本升级到最新版本。 升级过程包括升级 BizTalk Server 中，然后升级 BTARN。  
  
 你可以升级到 BTARN 的先前版本中通过运行 BTARN 安装程序。 安装程序将 BTRAN 配置信息迁移到最新版本。  
  
 在多服务器 BTARN 环境中，应升级所有 BizTalk 服务器，然后再到 BTARN。 请按以下顺序迁移服务器：  
  
-   承载 BizTalk 组的服务器  
  
-   各个处理节点  
  
-   BAM 门户服务器  
  
 BTARN 在升级过程，请确保你执行以下操作：  
  
-   检查 SQL Server (MSSQLSERVER) 服务是否正在运行。  
  
-   切勿运行无提示安装。  
  
## <a name="upgrade-steps"></a>升级步骤  
  
1.  升级 BizTalk Server。 请参阅[BizTalk Server 最新内容、 安装、 配置和升级](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。
  
2.  备份 BTARN 数据库和 BTARN 消息架构。  
  
    > [!NOTE]
    >  你应备份出于安全原因 BTARN 数据库。 安装程序将 BTRAN 数据库迁移到较新版本。  
  
3.  备份下的任何文件*< 驱动器\>*: \Program Files\\Microsoft BizTalk Accelerator RosettaNet 文件夹所做更改，例如，文件 SDK 中。  
  
4.  取消部署引用一个或多个早期版本 BTARN 程序集的项目或程序集。  
  
5.  在 Visual Studio 中，手动取消部署所有 BTARN 程序集，按以下顺序：  
  
    -   Microsoft.Solutions.BTARN.CommonTypes  
  
    -   Microsoft.Solutions.BTARN.GlobalSchemas  
  
    -   Microsoft.Solutions.BTARN.PipelineReceive  
  
    -   Microsoft.Solutions.BTARN.PipelineSend  
  
    -   Microsoft.Solutions.BTARN.PrivateInitiator  
  
    -   Microsoft.Solutions.BTARN.PrivateResponder  
  
    -   Microsoft.Solutions.BTARN.PublicInitiator  
  
    -   Microsoft.Solutions.BTARN.PublicResponder  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv11  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv20  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs  
  
6.  运行 BTARN 安装。 请参阅[安装和配置 RosettaNet 快捷键](install-configure-biztalk-accelerator-for-rosettanet.md)。
  
7.  使用**BTSTask.exe** (files\microsoft BizTalk Server) 手动重新部署 BTARN 程序集按以下顺序：  
  
    -   Microsoft.Solutions.BTARN.CommonTypes  
  
    -   Microsoft.Solutions.BTARN.GlobalSchemas  
  
    -   Microsoft.Solutions.BTARN.PipelineReceive  
  
    -   Microsoft.Solutions.BTARN.PipelineSend  
  
    -   Microsoft.Solutions.BTARN.PrivateInitiator  
  
    -   Microsoft.Solutions.BTARN.PrivateResponder  
  
    -   Microsoft.Solutions.BTARN.PublicInitiator  
  
    -   Microsoft.Solutions.BTARN.PublicResponder  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv11  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv20  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs  
  
    > [!NOTE]
    >  有关详细信息**BTSTask.exe**，请参阅 BizTalk Server 帮助中的"BTSTask 命令行参考"主题。  
  
8.  重新生成的任何项目或程序集引用了一个或多个 [BTARN 程序集。 使用**BTSTask.exe**手动重新部署这些项目。  
  
9. 对于以下各项，请将 IIS 中的虚拟文件夹从 ASP.NET 2.0 升级到 ASP.NET 4.0：  
  
    -   BTARNApp  
  
    -   BTARNHttpReceive  
  
10. 重新启动计算机以应用所作的任何修改。  
  
