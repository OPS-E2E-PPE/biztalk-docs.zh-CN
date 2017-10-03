---
title: "如何备份 BAM 门户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cea02e6-e387-4048-a1f3-d7c3c562f470
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e7308e54505c795e35ffa2fbb2d287c1a49ec4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-the-bam-portal"></a>如何备份 BAM 门户
如果您使用业务活动监视 (BAM)，则作为备份 BizTalk Server 工作的一部分，必须备份 BAM 门户。 如果没有使用 BAM，则此过程为可选。  
  
 备份过程的某些部分会因您所备份的 Internet 信息服务 (IIS) 版本的不同而有显著的不同。 IIS 6.0 允许您分别备份应用程序池配置和网站配置，您可以使用密码对配置备份文件进行加密。  
  
 IIS 7.0 将应用程序池和网站的配置设置保存到单个文件，applicationHost.config。未加密的 applicationHost.config 文件，但帐户密码，如果有的话，进行加密的文件中。 使用你要备份的计算机中的证书执行加密。 此配置不能还原到它源自以外的计算机。  
  
 不能备份 BAM 门户配置过程，使用 IIS 7.0 管理器;必须使用**Appcmd.exe**命令行工具。 有关 Appcmd 的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=147497](http://go.microsoft.com/fwlink/?LinkId=147497)。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a>若要备份 BAM 门户 (IIS 7.0)  
  
1.  单击 **“启动”**，再单击 **“运行”**。  
  
2.  在运行对话框中，在打开的框中，键入以下内容： `runas /user:` *computername*`\`*accountname* `cmd`，然后单击**确定**或按**Enter**。  
  
     *Accountname*必须是本地计算机上 administrators 组的成员。  
  
3.  出现提示时，键入的密码*accountname*，然后按**Enter**。  
  
4.  类型`cd %windir%\system32\inetsrv`，然后按**Enter**。  
  
5.  类型`appcmd add backup “` *backupname*`”`，然后按**Enter**。  
  
     无需输入备份名称。 如果未设置，它将自动生成。 自动生成的备份名称的一个示例是“20090224T123302”。  
  
     若要查看现有配置备份的列表，请键入`appcmd list backup`，然后按**Enter**。 由用户创建的备份保存在**%windir%\system32\inetsrv\backup**目录。 若要查看提供的备份选项的列表**appcmd.exe**，类型`appcmd backup /?`，然后按**Enter**。  
  
## <a name="see-also"></a>另请参阅  
 [备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md)   
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [BAM 门户](../core/bam-portal.md)