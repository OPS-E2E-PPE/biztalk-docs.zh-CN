---
title: 如何恢复 BAM 警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56c477b4-4605-4763-b20a-3baf4529f13f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fc3e51593b0a01fb43111f58f01ec07efdc09f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335622"
---
# <a name="how-to-recover-bam-alerts"></a>如何恢复 BAM 警报
作为恢复的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，如果使用业务活动监视 (BAM)，则还必须恢复 BAM 警报。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组才能执行此过程。  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a>若要恢复 BAM 警报 (SQL Server 2008)  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。  
  
2.  在命令提示符下，键入：  
  
     **nscontrol register-name BamAlerts-server***\<ServerName\>***-服务-serviceusername"** *\<ServiceUserName\>* **"-servicepassword"** *\<ServicePassword\>* **"**   
  
     这可使 Notification Services 登录到正确的数据库 （此信息保留在服务计算机的注册表中由 nscontrol）。  
  
    > [!IMPORTANT]
    >  请记得使用新的 Notification Services 数据库服务器 **-服务器**选项时重新注册该服务。 此外，您应使用新的 Notification Services 服务的同一用户名称与旧。  
  
3.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
4.  在命令提示符处，键入： **net start NS$ BamAlerts**。  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)