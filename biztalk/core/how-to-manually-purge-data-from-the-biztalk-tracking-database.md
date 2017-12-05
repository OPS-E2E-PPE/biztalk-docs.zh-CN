---
title: "如何从 BizTalk 跟踪数据库手动清除数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8bf8d87f7868367c252cdc75842b234cb06ff9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a>如何从 BizTalk 跟踪数据库手动清除数据
由于 DTA 存档和清除 SQL Server 代理作业不断清除 BizTalk 跟踪 (BizTalkDTADb) 数据库并对存储的跟踪数据进行压缩，因此可减少从该数据库中手动清除数据的需要。 但是，如果 BizTalk 跟踪 (BizTalkDTADb) 数据库迅速增长，从而导致性能持续下降以及 DTA 存档和清除作业无法跟上数据库的增长速度，则可能需要手动清除数据。  
  
> [!CAUTION]
>  执行此过程将会从 BizTalk 跟踪 (BizTalkDTADb) 数据库中删除已完成实例的所有跟踪数据，而不考虑这些实例的完成时间。 在执行此过程之前，应将 BizTalk 跟踪 (BizTalkDTADb) 数据库与其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库分开进行存档。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a>从 BizTalk 跟踪数据库中手动清除数据  
  
1.  备份 BizTalk Server 数据库。  
  
2.  存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
3.  打开“服务”控制台。 单击**启动**，单击**运行**，然后键入**services.msc**。 如果**用户帐户控制**显示对话框，请单击**继续**。  
  
4.  “服务”控制台出现时，查找以下每个服务，然后将它们停止。 若要停止服务，右键单击中的服务行**服务**窗格中，，然后单击**停止**。  
  
    -   BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
    -   企业单一登录服务  
  
         如果 BizTalkServiceBizTalkGroup: BizTalkServerApplication 服务正在运行时尝试关闭企业单一登录服务，**停止其他服务**将显示对话框。 单击 **“是”**。  
  
    -   规则引擎更新服务  
  
5.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。 如果**用户帐户控制**显示对话框，请确保所述的操作是你想，，然后单击**继续**。  
  
6.  在**BizTalk Server 管理控制台**在窗口左侧的资源管理器窗格中，双击**BizTalk 组**来展开它下面的列表，然后双击**平台设置**，然后单击**主机实例**。 这将显示的主机实例的列表 (**主机实例**窗格中) 和与相关的属性，在屏幕的右侧。  
  
7.  在**主机实例**窗格中，右键单击每个正在运行的主机实例，并依次**停止**。  
  
8.  单击**启动**，请转到**运行**，类型**cmd**，然后单击**确定**。  
  
9. 在命令提示符下，键入：  
  
     **net 停止 iisadmin /y**  
  
     这将逐一停止 IIS 管理服务及所有依存的服务，并在清除数据期间阻止向 BizTalkDTADb 写入新数据。 在停止每个服务时，请记下这些服务的列表。 以后重新启动 IIS 时，将需要使用此服务列表。  
  
     以下是一个在发出此命令后将显示的输出示例（您的计算机上列出的依存服务可能会有所不同）：  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。  
  
11. 在**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL Server 和适当的身份验证类型的名称，然后单击**连接**到连接到相应的 SQL Server。  
  
12. 在**Microsoft SQL Server Management Studio**，双击**数据库**，双击**BizTalkDTADb**数据库中，双击**可编程性**，然后单击**存储过程**。  
  
13. 在**对象资源管理器详细信息**窗格中，右键单击**dtasp_PurgeAllCompletedTrackingData**，然后单击**执行存储过程**。  
  
14. 在**执行过程**对话框中，单击**确定**。  
  
     此存储过程将删除与完成的实例相关联的所有跟踪数据，而不考虑其完成时间。  
  
15. 打开“服务”。 单击**启动**，单击**运行**，然后键入**services.msc**。 如果**用户帐户控制**显示对话框，请确保所述的操作是你想，，然后单击**继续**。  
  
16. 右键单击每个以下服务，然后单击**启动**:  
  
    -   BizTalkServiceBizTalkGroup: BizTalkServerApplication  
  
    -   企业单一登录服务  
  
    -   规则引擎更新服务  
  
17. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
18. 在**BizTalk Server 管理控制台**，双击**BizTalk 组**，双击**平台设置**，然后单击**主机实例**。  
  
19. 在**对象资源管理器详细信息**窗格中，右键单击每个已停止的主机实例，并依次**启动**。  
  
20. 如上面的步骤 8 中所述，启动命令提示符。  
  
21. 在命令提示符下，请重新启动每个 IIS 服务停止在步骤 4 中。 类型：  
  
     **net 开始**  *\<IISserviceName\>*  
  
     其中 *\<IISserviceName\>* 是你想要重新启动 IIS 服务的名称。 您必须对每个 IIS 服务重复执行此命令。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server 服务](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)