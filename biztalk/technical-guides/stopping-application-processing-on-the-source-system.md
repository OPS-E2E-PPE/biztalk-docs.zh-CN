---
title: "停止处理源系统上的应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cde5fc62-4bc2-4ef0-81bc-c7d39ff36cb6
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe980e3f29e2bd4cf13aa2b74a1923126fcec2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="stopping-application-processing-on-the-source-system"></a>停止处理源系统上的应用程序
应用程序处理应停止时源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器是仍能够参与使用现有的数据库服务器的文档处理。 在此方案中，处理活动必须先停止，以便可以在完成一致还原操作。  
  
 若要停止应用程序处理源系统上，确保没有连接处于打开状态之间生产[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 请按照下列步骤以停止对生产应用程序处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时计算机：  
  
1.  禁用所有接收位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 组中的计算机。 记下的所有接收可以以后重新启用已禁用，以便这些接收位置的位置。 这将停止[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理传入消息。  
  
2.  停止从上运行的所有主机实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中的计算机。 这可以从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 记下已停止，以便可以更高版本重新启动这些主机实例的所有主机实例。  
  
3.  停止所有[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
4.  如果 BAM 正在使用中，禁用任何 BAM 多维数据集更新和数据维护 SSIS 包。 这可以通过使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio。  
  
5.  上停止 Analysis Services[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 这可以通过停止 MSSQLServerOLAPService 的所有实例上完成[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]安装 Analysis Services 的计算机。  
  
6.  停止任何其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在可能正在运行的服务管理器服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机的组中，例如，企业单一登录服务和规则引擎更新服务。 记下，以便它们可以在稍后重新启动停止的服务。  
  
7.  关闭所有应用程序连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 这包括的实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中， [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)]，和任何其他已安装 BizTalk 应用程序。  
  
8.  验证不是否有生成的任何数据库活动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 使用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio，若要查看哪些过程连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 这可以通过展开**管理**双击**活动监视器**中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio。 然后单击以选择**进程信息**。 或者使用系统存储过程**sp_who**或**sp_who2**来标识到任何打开的连接[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]容纳的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 如果有连接任何进程，找到它们，并终止这些通常;或者作为最后一招，请右键单击每个进程中的**进程信息**窗格中的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio，然后单击**终止进程**可以终止的连接。  
  
9. 附加数据库处理可能发生在应用程序数据库。 如果将恢复这些数据库，请确保所有处理已都停止。  
  
## <a name="see-also"></a>另请参阅  
 [还原 BizTalk 组](../technical-guides/restoring-the-biztalk-group.md)