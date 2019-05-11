---
title: 如何从 BizTalk 跟踪数据库中手动清除数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- purging, manually
- purging, warnings
ms.assetid: f350d850-5034-4166-940c-8d10b7b445fb
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4e4366edf0187ee74391ea144b67878fb51999a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336688"
---
# <a name="how-to-manually-purge-data-from-the-biztalk-tracking-database"></a>如何从 BizTalk 跟踪数据库中手动清除数据
DTA 存档和清除 SQL Server 代理作业减少了需要手动清除数据从 BizTalk 跟踪 (BizTalkDTADb) 数据库由于不断清除数据库和存储的跟踪数据的压缩功能。 您可能需要手动清除发生数据 BizTalk 跟踪 (BizTalkDTADb) 数据库已变得如此多的持续的性能下降以及 DTA 存档和清除作业无法跟上数据库的增长速度。  
  
> [!CAUTION]
>  执行此过程删除已完成的实例的所有跟踪数据从 BizTalk 跟踪 (BizTalkDTADb) 数据库而不考虑完成时间。 在执行此过程之前, 应存档 BizTalk 跟踪 (BizTalkDTADb) 数据库独立于其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。  
  
### <a name="to-manually-purge-data-from-the-biztalk-tracking-database"></a>若要从 BizTalk 跟踪数据库中手动清除数据  
  
1. 备份 BizTalk Server 数据库。  
  
2. 存档 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
3. 打开服务控制台。 单击**启动**，单击**运行**，然后键入**services.msc**。 如果**用户帐户控制**显示对话框中，单击**继续**。  
  
4. 服务控制台出现时，查找，然后停止以下服务的每个。 若要停止服务，右键单击服务中行**Services**窗格中，，然后单击**停止**。  
  
   -   BizTalkServiceBizTalkGroup:BizTalkServerApplication  
  
   -   企业单一登录服务  
  
        如果 BizTalkServiceBizTalkGroup:尝试关闭企业单一登录服务时 BizTalkServerApplication 服务正在运行**停止其他服务**将显示对话框。 单击 **“是”**。  
  
   -   规则引擎更新服务  
  
5. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。 如果**用户帐户控制**显示对话框中，验证所述的操作是您想要，然后单击**继续**。  
  
6. 在中**BizTalk Server 管理控制台**在窗口左侧的资源管理器窗格中，双击**BizTalk 组**若要展开它下面的列表，然后双击**平台设置**，然后单击**主机实例**。 这将显示一系列主机实例 (**主机实例**窗格) 及相关的属性，在屏幕右侧。  
  
7. 在中**主机实例**窗格中，右键单击每个正在运行的主机实例，然后单击**停止**。  
  
8. 单击**启动**，请转到**运行**，类型**cmd**，然后单击**确定**。  
  
9. 在命令提示符下，键入：  
  
     **net 停止 iisadmin /y**  
  
     这会停止 IIS 管理服务和所有依赖服务，一个地并防止清除数据时向 BizTalkDTADb 写入新数据。 记下的服务列表因为每个已停止。 需要重新启动 IIS 时使用此服务更高版本列表。  
  
     下面是将发出此命令 （您的计算机上列出的依存服务可能有所不同） 后看到的输出示例：  
  
    ```  
    The following services are dependent on the IIS Admin Service service. Stopping the IIS Admin Service service will also stop these services.  
    World Wide Web Publishing Service  
    HTTP SSL  
    ```  
  
10. 单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**。  
  
11. 在中**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL 服务器和相应的验证类型的名称，然后单击**Connect**到连接到相应的 SQL Server。  
  
12. 在中**Microsoft SQL Server Management Studio**，双击**数据库**，双击**BizTalkDTADb**数据库中，双击**可编程性**，然后单击**存储过程**。  
  
13. 在中**对象资源管理器详细信息**窗格中，右键单击**dtasp_PurgeAllCompletedTrackingData**，然后单击**执行存储过程**。  
  
14. 在中**执行过程**对话框中，单击**确定**。  
  
     此存储的过程删除已完成的实例，而不考虑其完成时间与关联的所有跟踪数据。  
  
15. 打开服务。 单击**启动**，单击**运行**，然后键入**services.msc**。 如果**用户帐户控制**显示对话框中，验证所述的操作是您想要，然后单击**继续**。  
  
16. 右键单击每个以下的服务，然后依次**启动**:  
  
    -   BizTalkServiceBizTalkGroup:BizTalkServerApplication  
  
    -   企业单一登录服务  
  
    -   规则引擎更新服务  
  
17. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
18. 在中**BizTalk Server 管理控制台**，双击**BizTalk 组**，双击**平台设置**，然后单击**主机实例**。  
  
19. 在中**对象资源管理器详细信息**窗格中，右键单击每个停止的主机实例，然后依次**启动**。  
  
20. 启动命令提示符下，如上面的步骤 8 中所述。  
  
21. 在命令提示符下，在重新启动停止 IIS 服务的每个步骤 4。 键入：  
  
     **net start** *\<IISserviceName\>*  
  
     其中*\<IISserviceName\>* 是你想要重新启动 IIS 服务的名称。 必须为每个 IIS 服务重复此命令。  
  
## <a name="see-also"></a>请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)   
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)   
 [如何启动、 停止、 暂停、 恢复或重新启动 BizTalk Server 服务](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)