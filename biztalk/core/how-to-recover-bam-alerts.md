---
title: 如何恢复 BAM 警报 |Microsoft 文档
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
ms.openlocfilehash: ec36491dd7368e0e2fdbcd8fb5abab9d840c6b1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972539"
---
# <a name="how-to-recover-bam-alerts"></a>如何恢复 BAM 警报
作为恢复的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，如果要使用业务活动监视 (BAM)，你必须恢复 BAM 警报。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-recover-bam-alerts-sql-server-2008"></a>若要恢复 BAM 警报 (SQL Server 2008)  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008**，单击**配置工具**，然后单击**通知服务命令提示符**。  
  
2.  在命令提示符下，键入：  
  
     **nscontrol register-name BamAlerts-服务器***\<ServerName\>***-服务-serviceusername"**  *\<ServiceUserName\>*  **"-servicepassword"**  *\<ServicePassword\>*  **"**   
  
     这使通知服务登录到正确的数据库 （此信息将保留在服务计算机的注册表中通过 nscontrol）。  
  
    > [!IMPORTANT]
    >  请记住使用中的新 Notification Services 数据库服务器 **-服务器**选项时重新注册该服务。 此外，新的 Notification Services 服务使用的用户名应与旧名称相同。  
  
3.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
4.  在命令提示符处，键入： **net 开始 NS$ BamAlerts**。  
  
## <a name="see-also"></a>另请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)