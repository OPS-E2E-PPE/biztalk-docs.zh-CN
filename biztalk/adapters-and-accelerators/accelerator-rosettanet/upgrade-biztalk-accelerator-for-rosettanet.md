---
title: 升级 BizTalk Server 中的 RosettaNet 加速器 (BTARN) |Microsoft Docs"
description: 请按照升级步骤更新到 BizTalk Server 中的当前版本的 BTARN
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 80e813ced767cdd56910027b655060e1db9f91fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011294"
---
# <a name="upgrade-the-rosettanet-accelerator"></a>升级 RosettaNet 加速器

## <a name="upgrade-overview"></a>升级概述
你可以升级到最新版本的以前版本的 BizTalk Accelerator for RosettaNet (BTARN) 安装。 升级过程包括升级 BizTalk Server 以及然后升级 BTARN。  
  
 可以升级从以前版本的 BTARN 到通过运行 BTARN 安装程序。 安装程序会将 BTRAN 配置信息迁移到最新版本。  
  
 在多服务器 BTARN 环境中，应升级所有 BizTalk Server，然后再到 BTARN。 请按以下顺序迁移服务器：  
  
- 承载 BizTalk 组的服务器  
  
- 各个处理节点  
  
- BAM 门户服务器  
  
  BTARN 中升级过程，请确保您执行以下操作：  
  
- 检查 SQL Server (MSSQLSERVER) 服务是否正在运行。  
  
- 切勿运行无提示安装。  
  
## <a name="upgrade-steps"></a>升级步骤  
  
1.  升级 BizTalk Server。 请参阅[BizTalk Server 最新内容、 安装、 配置和升级](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。
  
2.  备份 BTARN 数据库和 BTARN 消息架构。  
  
    > [!NOTE]
    >  您应备份出于安全考虑在 BTARN 数据库。 安装程序会将 BTRAN 数据库迁移到较新版本。  
  
3.  备份下的任何文件 *< 驱动器\>*: \Program Files\\Microsoft BizTalk Accelerator RosettaNet 文件夹所做的更改，例如，SDK 中的文件。  
  
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
  
6.  运行 BTARN 安装。 请参阅[安装和配置 RosettaNet 加速器](install-configure-biztalk-accelerator-for-rosettanet.md)。
  
7.  使用**BTSTask.exe** (\Program Files\Microsoft BizTalk Server) 来手动重新部署 BTARN 程序集按以下顺序：  
  
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
  
8.  重新生成任何项目或程序集引用了一个或多个 [BTARN 程序集。 使用**BTSTask.exe**手动重新部署这些项目。  
  
9. 对于以下各项，请将 IIS 中的虚拟文件夹从 ASP.NET 2.0 升级到 ASP.NET 4.0：  
  
    -   BTARNApp  
  
    -   BTARNHttpReceive  
  
10. 重新启动计算机以应用所作的任何修改。  
  
