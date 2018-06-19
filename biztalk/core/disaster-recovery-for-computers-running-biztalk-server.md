---
title: 运行 BizTalk Server 的计算机的灾难恢复 |Microsoft 文档
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
ms.openlocfilehash: b0ca86ef9a412514fdf3f30f0a38cbac710e0f59
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005222"
---
# <a name="disaster-recovery-for-computers-running-biztalk-server"></a>运行 BizTalk Server 的计算机的灾难恢复
如果您的组织中运行 BizTalk Server 的计算机出现了无法恢复的硬件故障，则应该用相同设置的计算机代替它。 其假定条件是，BizTalk Server 数据库保存完整，并且故障发生在运行 BizTalk Server 的任何计算机上。  
  
 一种可能的方法是为安装环境中运行 BizTalk Server 的每台计算机都保留一个最新的映像。 在计算机出现硬件故障时，恢复操作只不过是在新计算机上部署存储的映像。 本灾难恢复主题讨论不适于存储这种映像的情况。  
## <a name="recovering-different-editions-of-biztalk-server"></a>恢复不同版本的 BizTalk Server  
 恢复方法因计算机上运行的 BizTalk Server 的版本不同而异。  
  
 BizTalk Server Developer Edition 和 BizTalk Server Enterprise Edition，多台计算机运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]允许。 当其中一台运行 BizTalk Server 的计算机发生故障时，可以准备一台替代计算机并将其加入现有 BizTalk 组。 在这种情况下，可以向 BizTalk 组中加入同名或不同名的计算机。  
  
 为 BizTalk Server Standard Edition，你无法将计算机加入到 BizTalk 组，因此上面的方法是不适合。 我们概述以下必要步骤，以设置一台新计算机并还原 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的配置设置，从而使其具备替代功能。 有关详细信息，请参阅[如何恢复 BizTalk 组](../core/how-to-recover-the-biztalk-group.md)。  
  
## <a name="recovery-phases"></a>恢复阶段  
 运行 BizTalk Server 的计算机的恢复过程可分为以下三个阶段：  
  
1.  **准备基础平台**  
  
     此阶段需要准备一个具有基础平台的计算机，该平台需包含操作系统、必备软件和适当的 BizTalk Server 组件。 本指南假定，在尝试还原 BizTalk Server 配置前，计算机已安装了基础平台、必备软件和 BizTalk Server 组件。 本指南不涉及基础平台的还原。  
  
2.  **还原 BizTalk Server 配置**  
  
     此阶段假定您已记录了发生故障计算机上的功能，这包括该计算机的 BizTalk Server 配置文件的副本。 本指南将指导您还原 BizTalk Server 配置。  
  
3.  **还原 BizTalk 应用程序**  
  
     此阶段将在替代计算机上还原与在 BizTalk Server 进程上运行的应用程序连接的 .NET 程序集。 所需的所有项目，如 BizTalk 程序集之外的用户程序集，都应该安装到计算机上其各自的位置或全局程序集缓存 (GAC) 中。 本指南为此阶段提供了一些指导。 但是，并不涉及用于还原 BizTalk 应用程序的单独脚本或工具。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)