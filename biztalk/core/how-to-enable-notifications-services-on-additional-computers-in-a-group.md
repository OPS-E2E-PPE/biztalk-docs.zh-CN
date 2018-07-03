---
title: 如何启用在组中的其他计算机上的通知服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fd8a1a49be2416fb8b7fe5d160dd5228a95e94f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983390"
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a>如何启用在组中的其他计算机上的通知服务
在多计算机环境中运行 BAM 时，必须在将运行 BAM 管理实用程序以便部署某一活动的每台计算机上都启用 Notification Services。  
  
 请考虑下列方案：  
  
- 组 A 由以下计算机组成：  
  
  - 计算机 1 用作 BAM 管理计算机。  
  
  - 计算机 2 承载 BAM PIT 和星型架构数据库。  
  
  - 计算机 3 承载 BAM 存档和分析数据库。  
  
  - 计算机 4 承载 BAM 警报数据库。  
  
  - 计算机 5 承载的其余部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
- 组 b:  
  
  -   为 BAM 管理计算机的所有数据库都共享与组 a。 使用计算机 6  
  
  若要能够从组 B 中的计算机组 A 中的数据库部署某一活动，必须先注册 Notification Services[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]托管通知服务。 如果未注册 Notification Services，您将收到以下错误：  
  
  部署警报...错误： BAM 部署失败。  
  
  未部署警报。  
  
  调用的目标发生了异常。  
  
  找不到指定的 Notification Services 实例的注册表项。  
  
### <a name="to-register-notifications-services-additional-computers"></a>若要注册通知服务的其他计算机  
  
1.  在其他组中计算机上，单击**启动**，依次指向**所有程序**，单击**Microsoft SQL Server 2005**，单击**配置工具**，然后单击**Notification Services 命令提示**。  
  
2.  在命令提示符处，键入： **nscontrol register-名称\<NS 前缀名称在配置选择\>-服务器\<ns db sql server\>**。 这样可使 Notification Services 登录到正确的数据库（此信息由 nscontrol 在服务所在计算机的注册表中维护）。  
  
## <a name="see-also"></a>请参阅  
 [更改 BAM 运行时设置](../core/changing-bam-runtime-settings.md)   
 [BAM 管理实用工具](../core/bam-management-utility.md)