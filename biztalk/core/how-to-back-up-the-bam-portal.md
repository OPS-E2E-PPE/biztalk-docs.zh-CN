---
title: 如何备份 BAM 门户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cea02e6-e387-4048-a1f3-d7c3c562f470
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbfa35fd3adc6fbbcba247fbc5c093a52c05f044
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387096"
---
# <a name="how-to-back-up-the-bam-portal"></a>如何备份 BAM 门户
如果使用业务活动监视 (BAM)，必须备份 BAM 门户作为备份 BizTalk server 的一部分。 如果您没有使用 BAM，则此过程是可选的。  
  
 具体取决于哪个版本的 Internet 信息服务 (IIS) 备份，备份过程的某些部分与明显不同。 IIS 6.0 允许您分别备份应用程序池配置和 web 站点配置，并可以对配置备份文件使用的密码进行加密。  
  
 IIS 7.0 将应用程序池和网站的配置设置保存到单个文件，applicationHost.config。未加密的 applicationHost.config 文件，但帐户密码，如果有的话，在加密文件。 使用您要备份的计算机中的证书执行加密。 此配置无法还原到它源自以外的计算机。  
  
 不能备份 BAM 门户配置使用 IIS 7.0 管理器;必须使用**Appcmd.exe**命令行工具。 有关 Appcmd 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=147497 ](http://go.microsoft.com/fwlink/?LinkId=147497)。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的管理员组的成员身份登录。  
  
### <a name="to-back-up-the-bam-portal-iis-70"></a>若要备份 BAM 门户 (IIS 7.0)  
  
1.  单击 **“启动”**，再单击 **“运行”**。  
  
2.  在运行对话框中，在打开框中键入以下内容： `runas /user:` *computername*`\`*accountname* `cmd`，然后单击**确定**或按**Enter**。  
  
     *Accountname*必须是本地计算机上 administrators 组的成员。  
  
3.  出现提示时，键入的密码*accountname*，然后按**Enter**。  
  
4.  类型`cd %windir%\system32\inetsrv`，然后按**Enter**。  
  
5.  类型`appcmd add backup “` *backupname*`”`，然后按**Enter**。  
  
     无需输入备份名称。 如果未设置，它将自动生成。 自动生成的备份名称的一个示例是"20090224T123302。  
  
     若要查看现有配置备份的列表，请键入`appcmd list backup`，然后按**Enter**。 由用户创建的备份保存在 **%windir%\system32\inetsrv\backup**目录。 若要查看提供的备份选项的列表**appcmd.exe**，类型`appcmd backup /?`，然后按**Enter**。  
  
## <a name="see-also"></a>请参阅  
 [备份运行 BizTalk Server 的计算机](../core/backing-up-a-computer-running-biztalk-server.md)   
 [恢复运行 BizTalk Server 的计算机](../core/recovering-a-computer-running-biztalk-server.md)   
 [BAM 门户](../core/bam-portal.md)