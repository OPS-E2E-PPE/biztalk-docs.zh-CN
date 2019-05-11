---
title: 如何恢复 BAM 门户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a5df99-6d03-4f1f-8540-1700d3a0b9db
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7f0d9a813b2a8cee115ba782131c2492ea14fff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335595"
---
# <a name="how-to-recover-the-bam-portal"></a>如何恢复 BAM 门户
如果使用业务活动监视 (BAM)，你必须恢复 BAM 门户作为恢复的一部分在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 如果您没有使用 BAM，则此过程是可选的。  
  
 恢复 BAM 门户配置的过程大不相同的 IIS 版本根据你使用。 在还原适用于 IIS 7 配置时，使用**Appcmd.exe**，你将还原整个默认网站，而不仅仅是 BAM 门户的配置。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的管理员组的成员身份登录。  
  
### <a name="to-recover-the-bam-portal-configuration-iis-70"></a>若要恢复 BAM 门户配置 (IIS 7.0)  
  
1.  在运行对话框中，在打开框中键入以下内容： `runas /user:` *computername*`\`*accountname* `cmd`，然后单击**确定**或按**Enter**。  
  
     *Accountname*必须是本地计算机上 administrators 组的成员。  
  
2.  出现提示时，键入的密码*accountname*，然后按**Enter**。  
  
3.  类型`cd %windir%\system32\inetsrv`，然后按**Enter**。  
  
4.  类型`appcmd restore backup “` *backupname*`”`，然后按**Enter**。  
  
     *Backupname*是以前使用创建的备份名称**Appcmd.exe**。 此备份必须存在于 **%windir%\system32\inetsrv\backup**目录。 备份不能用于还原的不同计算机上创建的密码。 如果 BAMAppPool 配置为默认值以外的身份下运行**NetworkService**帐户，您必须在下一步中所述单独配置的帐户和密码。  
  
5.  使用**Internet 信息服务 (IIS) 管理器**，选择**应用程序池**中**连接**窗格。  
  
6.  在中**应用程序池**窗格中，右键单击**BAMAppPool**，然后单击**高级设置**  
  
7.  在中**高级设置**对话框中，向下滚动到**进程模型**部分。 单击**标识**框。 这将导致一个用于显示框的右侧的省略号按钮。 单击**省略号**按钮。  
  
8.  在中**应用程序池标识**对话框中，单击**自定义帐户**按钮，然后单击**设置**按钮。  
  
9. 在中**设置凭据**对话框框中，输入帐户名和你想要用于 BAMAppPool 的密码。 应为输入帐户名称*计算机名*`\`*accountname*，或*域*`\`*accountname*. 单击**确定**以关闭**设置凭据**对话框。  
  
10. 单击**确定**以关闭**应用程序池标识**对话框。  
  
11. 单击**确定**以关闭**高级设置**对话框。  
  
12. 确认**BAMAppPool**的应用程序池列表中选择。 在中**操作**的右侧窗格**Internet 信息服务 (IIS) 管理器**屏幕上，在**应用程序池任务**，单击**启动**.  
  
## <a name="see-also"></a>请参阅  
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [BAM 门户](../core/bam-portal.md)