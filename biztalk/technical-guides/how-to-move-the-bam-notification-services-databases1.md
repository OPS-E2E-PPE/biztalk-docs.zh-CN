---
title: 如何移动 BAM Notification Services Databases1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 735a0e5d1d84c589948dcf5e075a665c66c50a94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393505"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>如何移动 BAM Notification Services 数据库
可以使用此过程将 BAM Notification Services 数据库移到另一台服务器。  从端到端方案的角度看，移动 BAM Notification Services 数据库涉及到两个主要步骤：  
  
-   [移动 BAM 通知服务数据库](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [正在更新引用对新的 BAM Notification Services 数据库](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  必须一起移动 BAM Notification Services 应用程序 (BAMAlertsApplication) 数据库和 BAM Notification Services 实例 (BAMAlertsNSMain) 数据库。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。  
  
##  <a name="BKMK_NotiMoveDB"></a> 移动 BAM 通知服务数据库  
 以下过程来移动 BAM Notification Services 数据库中执行的步骤。  
  
#### <a name="to-move-the-bam-notification-services-database"></a>移动 BAM Notification Services 数据库  
  
1. 停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAM Notification Services 数据库的还原。  
  
2. 停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (<http://go.microsoft.com/fwlink/?LinkId=154394>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
3. 停止 IIS 服务。  
  
4. 停止 BAM 警报 Notification service:  
  
   1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2.  在命令提示符下，键入：  
  
        **net stop NS$ BamAlerts**  
  
5. 在旧服务器上备份 BAM Notification Services 数据库。 备份数据库的说明，请遵循的说明[如何：备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (<http://go.microsoft.com/fwlink/?LinkId=156510>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何备份数据库的联机丛书。  
  
   > [!NOTE]  
   >  BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。  
  
6. 将 BAM Notification Services 数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
7. 还原新服务器上的 BAM Notification Services 数据库。 对于还原数据库的说明，请按照的说明[如何：还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (<http://go.microsoft.com/fwlink/?LinkId=156511>) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上如何还原数据库的联机丛书。  
  
   > [!NOTE]  
   >  BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。  
  
##  <a name="BKMK_NotiUpdate"></a> 正在更新引用对新的 BAM Notification Services 数据库  
 在移动数据库之后，必须更新到新的 BAM Notification Services 数据库的所有引用。 必须更新以下引用：  
  
- 使用新的数据库和服务器名称更新 BAM 配置。 请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig)。  
  
- 重新注册中的所有计算机上的通知服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 请参阅[注册 Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister)。  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a> 若要更新 BAM 配置  
  
1. 获取用于还原 BAM 的.xml 文件的副本：  
  
   1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
   2. 在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
      - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
      - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
   3. 在命令提示符下，键入：  
  
       **Bm.exe get-config –filename:BAMConfiguration.xml -server:\<servername\> -database:\<database\>**  
  
      > [!NOTE]
      >  当运行此命令，替换从其获取的配置信息的服务器的实际名称<servername>并将其替换从其获取的配置信息的数据库的实际名称<database>。 有关使用 BAM 管理 (BM) 实用程序的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(<http://go.microsoft.com/fwlink/?LinkId=156516>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
2. 编辑 BAMConfiguration.xml 文件，将**数据库服务器**中的属性`<DeploymentUnit Name="Alert">`到新的服务器名称的部分。  
  
3. 保存并关闭 BAMConfiguration.xml 文件。  
  
4. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
5. 在运行 BizTalk Server 的计算机，浏览到以下文件夹：  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 位版本的 Windows Server 上安装：  
  
      **%ProgramFiles(x86)%\Microsoft BizTalk Server 2010\Tracking**  
  
   - 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
      **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6. 在命令提示符下，键入：  
  
    **bm.exe update-config -FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_NotiRegister"></a> 注册 Notification Services  
 移动 BAM Notification Services 数据库后，必须重新注册 Notification Service 的 BizTalk Server 组中运行 Notification Services (NSservice.exe) 的所有计算机上。 这可使 Notification Services 连接到其新位置中的数据库。 有关如何注册 Notification Services 的说明，请按照步骤 5 到 11[如何更新对 BAM Notification Services 数据库的引用](http://go.microsoft.com/fwlink/?LinkId=156684)(<http://go.microsoft.com/fwlink/?LinkId=156684>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 请注意以下时执行上述链接中所述的步骤：  
  
-   必须在 BAM 配置 XML 中的以下属性中列出的服务器上执行步骤 5 和 6 上述链接中：  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   步骤 7 至 11 必须在承载 BAM 门户的计算机上执行。  
  
## <a name="see-also"></a>请参阅  
 [移动数据库](../technical-guides/moving-databases.md)