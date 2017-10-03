---
title: "如何恢复 BAM 门户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 781191047e0ee99b0000c7b773d46aa035a7e1d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-bam-portal"></a>如何恢复 BAM 门户
如果在使用业务活动监视 (BAM)，则必须在恢复 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时恢复 BAM 门户。 如果没有使用 BAM，则此过程为可选。  
  
 根据 IIS 的版本使用以便恢复 BAM 门户配置过程有很大不同。 在还原 IIS 7 的配置时，你使用**Appcmd.exe**，和还原整个默认网站，而不仅仅是 BAM 门户的配置。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a>若要恢复的 BAM 门户配置 (IIS 7.0)  
  
1.  在运行对话框中，在打开的框中，键入以下内容： `runas /user:` *computername*`\`*accountname* `cmd`，然后单击**确定**或按**Enter**。  
  
     *Accountname*必须是本地计算机上 administrators 组的成员。  
  
2.  出现提示时，键入的密码*accountname*，然后按**Enter**。  
  
3.  类型`cd %windir%\system32\inetsrv`，然后按**Enter**。  
  
4.  类型`appcmd restore backup “` *backupname*`”`，然后按**Enter**。  
  
     *Backupname*是先前使用创建的备份名称**Appcmd.exe**。 此备份必须存在于**%windir%\system32\inetsrv\backup**目录。 备份不能用于还原的其他计算机上创建的密码。 如果 BAMAppPool 配置为在不同于默认标识下运行**NetworkService**帐户，您必须单独下, 一步中所述配置的帐户和密码。  
  
5.  使用**Internet Information Services (IIS) Manager**，选择**应用程序池**中**连接**窗格。  
  
6.  在**应用程序池**窗格中，右键单击**BAMAppPool**，然后单击**高级设置**  
  
7.  在**高级设置**s 对话框中，向下滚动到**进程模型**部分。 单击**标识**框。 这将导致一个用于出现在框的右侧的省略号按钮。 单击**省略号**按钮。  
  
8.  在**应用程序池标识**对话框中，单击**自定义帐户**按钮，然后单击**设置**按钮。  
  
9. 在**设置凭据**对话框框中，输入帐户名和你想要用于 BAMAppPool 的密码。 应输入的帐户名称作为*计算机名称*`\`*accountname*，或*域*`\`*accountname*. 单击**确定**关闭**设置凭据**对话框。  
  
10. 单击**确定**关闭**应用程序池标识**对话框。  
  
11. 单击**确定**关闭**高级设置**对话框。  
  
12. 验证**BAMAppPool**在应用程序池的列表中选择。 在**操作**的右侧窗格中**Internet Information Services (IIS) Manager**屏幕上，在**应用程序池任务**，单击**启动**.  
  
## <a name="see-also"></a>另请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [BAM 门户](../core/bam-portal.md)