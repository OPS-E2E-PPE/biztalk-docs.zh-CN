---
title: "如何移动 BAM 通知 Services Databases1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89b4938e-ea4a-48d3-80c3-eb9401e28323
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a5f643d764790b37deaab445290f1230c9ed8ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>如何移动 BAM 通知 Services 数据库
可以使用此过程将 BAM Notification Services 数据库移到另一台服务器。  从端到端方案的角度看，移动 BAM Notification Services 数据库涉及到两个主要步骤：  
  
-   [移动 BAM 通知服务数据库](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiMoveDB)  
  
-   [更新到新的 BAM 通知引用 Services 数据库](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdate)  
  
> [!NOTE]  
>  必须一起移动 BAM 通知服务应用程序 (BAMAlertsApplication) 数据库和 BAM 通知服务实例 (BAMAlertsNSMain) 数据库。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。  
  
##  <a name="BKMK_NotiMoveDB"></a>移动 BAM 通知服务数据库  
 执行以下过程来移动 BAM Notification Services 数据库中的步骤。  
  
#### <a name="to-move-the-bam-notification-services-database"></a>若要移动 BAM Notification Services 数据库  
  
1.  停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或防止它们运行，直到您已还原 BAM Notification Services 数据库。  
  
2.  停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。 有关详细信息，请参阅主题[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](http://go.microsoft.com/fwlink/?LinkId=154394) (http://go.microsoft.com/fwlink/?LinkId=154394) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
3.  停止 IIS 服务。  
  
4.  停止 BAM 警报通知服务：  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在命令提示符下，键入：  
  
         **Net stop NS$ BamAlerts**  
  
5.  旧服务器上备份 BAM Notification Services 数据库。 有关备份数据库的说明，请遵循的说明[How to： 备份数据库 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156510) (http://go.microsoft.com/fwlink/?LinkId=156510) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何备份数据库联机丛书。  
  
    > [!NOTE]  
    >  BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。  
  
6.  BAM Notification Services 数据库复制到新[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
7.  还原新的服务器上的 BAM Notification Services 数据库。 对于说明还原数据库，请按照说明[如何： 还原数据库备份 (SQL Server Management Studio)](http://go.microsoft.com/fwlink/?LinkId=156511) (http://go.microsoft.com/fwlink/?LinkId=156511) 中[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]如何还原数据库联机丛书。  
  
    > [!NOTE]  
    >  BAMAlertsApplication 和 BAMAlertsNSMain 数据库执行此步骤。  
  
##  <a name="BKMK_NotiUpdate"></a>更新到新的 BAM 通知引用 Services 数据库  
 将数据库移动后，你必须更新到新的 BAM Notification Services 数据库的所有引用。 必须更新以下引用：  
  
-   使用新的数据库和服务器名称更新 BAM 配置。 请参阅[更新 BAM 配置](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiUpdateBAMConfig)。  
  
-   重新注册中的所有计算机上的通知服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 请参阅[注册 Notification Services](../technical-guides/how-to-move-the-bam-notification-services-databases1.md#BKMK_NotiRegister)。  
  
###  <a name="BKMK_NotiUpdateBAMConfig"></a>若要更新 BAM 配置  
  
1.  获取用于还原 BAM 的 .xml 文件的副本：  
  
    1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
    2.  在运行 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的计算机中，浏览至以下文件夹：  
  
        -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：  
  
             **%Programfiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
        -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
             **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
    3.  在命令提示符下，键入：  
  
         **Bm.exe get-config –filename:BAMConfiguration.xml-server:\<服务器名称 >-数据库：\<数据库 >**  
  
        > [!NOTE]  
        >  运行此命令时, 替换从其获取的配置信息的服务器的实际名称<servername>和替换从其获取的配置信息的数据库的实际名称<database>。 有关使用 BAM 管理 (BM) 实用工具的详细信息，请参阅[基础结构管理命令](http://go.microsoft.com/fwlink/?LinkId=156516)(http://go.microsoft.com/fwlink/?LinkId=156516) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
2.  编辑 BAMConfiguration.xml 文件并将更改**DBServer**中的属性`<DeploymentUnit Name="Alert">`到新的服务器名称的部分。  
  
3.  保存并关闭 BAMConfiguration.xml 文件。  
  
4.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
5.  在运行 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的计算机中，浏览至以下文件夹：  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装在 64 位版本的 Windows Server 上：  
  
         **%Programfiles (x86) %\Microsoft BizTalk Server 2010\Tracking**  
  
    -   如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]32 位版本的 Windows Server 上安装：  
  
         **%ProgramFiles%\Microsoft BizTalk Server 2010\Tracking**  
  
6.  在命令提示符下，键入：  
  
     **bm.exe 更新-config-FileName:BAMConfiguration.xml**  
  
###  <a name="BKMK_NotiRegister"></a>注册通知服务  
 将 BAM Notification Services 数据库移动后，你必须重新注册 BizTalk Server 组中所有正在运行通知服务 (NSservice.exe) 的计算机上的通知服务。 这样可使 Notification Services 连接到新位置上的数据库。 有关如何注册通知服务的说明，请按照步骤 5 至 11[如何对 BAM 通知服务数据库的更新引用](http://go.microsoft.com/fwlink/?LinkId=156684)(http://go.microsoft.com/fwlink/?LinkId=156684) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
 注意在执行前面的链接中所述的步骤时以下信息：  
  
-   必须针对以下属性的 BAM 配置 XML 中列出的服务器上执行步骤 5 和 6 上述链接中：  
  
    ```  
    <DeploymentUnit Name="Alert">  
      <Property Name="GeneratorServerName">Server_Name</Property>  
      <Property Name="ProviderServerName">Server_Name</Property>  
      <Property Name="DistributorServerName">Server_Name</Property>  
    </DeploymentUnit>  
  
    ```  
  
-   步骤 7 至 11，必须在承载 BAM 门户的计算机上执行。  
  
## <a name="see-also"></a>另请参阅  
 [移动数据库](../technical-guides/moving-databases.md)