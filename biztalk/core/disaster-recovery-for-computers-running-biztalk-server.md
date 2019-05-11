---
title: 运行 BizTalk Server 的计算机的灾难恢复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10a2c26d-55d5-45d1-9fb1-e0664f005c21
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7469c97409ce53a995db95b263f5874e737a9905
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350996"
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a>运行 BizTalk Server 的计算机的灾难恢复
如果你的组织中运行 BizTalk Server 的计算机出现了不可恢复的硬件故障，您应将其替换相同设置的计算机。 这假定 BizTalk Server 数据库将保持不变，并故障是其中的任何一种运行 BizTalk Server 的计算机。  
  
 一种可行方法是保持运行 BizTalk Server 安装中的每台计算机的已更新的映像。 在计算机出现硬件故障，恢复操作只需部署一台新计算机上存储的映像。 灾难恢复主题讨论其中存储此类映像是不可行的情况。  
## <a name="recovering-different-editions-of-biztalk-server"></a>恢复不同版本的 BizTalk Server  
 恢复方法是在计算机上运行的 BizTalk Server 的版本而异。  
  
 对于 BizTalk Server 开发人员版和 BizTalk Server Enterprise Edition，多台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]允许。 当运行 BizTalk Server 的计算机出现故障时，可以准备一台替代计算机并将其加入到现有的 BizTalk 组。 在这种情况下，可以使用相同的名称或不同的名称的计算机加入到 BizTalk 组。  
  
 对于 BizTalk Server Standard Edition，您不能将计算机加入到 BizTalk 组，所以上述方法不适用。 相反，我们概述了设置一台新计算机并还原所需的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置设置，从而替代其功能。 有关详细信息，请参阅[如何恢复 BizTalk 组](../core/how-to-recover-the-biztalk-group.md)。  
  
## <a name="recovery-phases"></a>恢复阶段  
 运行 BizTalk Server 的计算机的恢复可分为以下三个阶段：  
  
1.  **准备基础平台**  
  
     本阶段包括基本平台包括操作系统、 必备软件和适当的 BizTalk Server 组件的计算机的准备。 本指南假定，在尝试还原 BizTalk Server 配置前，必须具有基础平台、 先决条件和安装 BizTalk Server 组件的计算机。 本指南不涉及基础平台的还原。  
  
2.  **还原 BizTalk Server 配置**  
  
     此阶段假定出现故障的计算机，包括该计算机的 BizTalk Server 配置文件的副本上配置的功能的记录。 本指南提供有关还原 BizTalk Server 配置的指导。  
  
3.  **还原 BizTalk 应用程序**  
  
     此阶段涉及到还原与由替代计算机上的 BizTalk Server 进程承载的应用程序相关联的.NET 程序集。 应在其各自的位置或在计算机上的全局程序集缓存 (GAC) 中安装需要如 BizTalk 程序集之外的用户程序集的任何项目。 在此阶段，本指南提供一些指导。 但是，没有单独的脚本或工具，用于还原 BizTalk 应用程序。  
  
## <a name="see-also"></a>请参阅  
 [备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)