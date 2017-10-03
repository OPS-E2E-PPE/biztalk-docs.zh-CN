---
title: "升级 HL7 BizTalk 快捷键 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23b835317d46dfeded65de310f8a813d4ac86749
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a>升级 BizTalk Accelerator for HL7
概述[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]升级过程。 
  
<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a>升级之前需完成的操作  
  
-   运行升级的用户必须是 BizTalk 管理员组的成员。  
  
-   执行升级时，必须运行 SQL Server (MSSQLSERVER) 服务。  
  
-   不运行升级的无提示安装。  
  
-   当你升级时，安装程序将迁移现有[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]到较新版本的配置信息。  
  
-   当你升级时，注册表项和数据库会自动备份。  
  
-   中的文件*\<驱动器 >*: files\microsoft BizTalk\<版本 > Accelerator for HL7 文件夹将更新。  
  
> [!IMPORTANT]
>  升级不会创建为升级的文件中，新建一个文件夹，也不会更改现有文件夹的名称。  
  
<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a>支持的升级路径  
 下表列出了支持[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以升级的版本。 "是"意味着[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]可以升级版本。 "No"，则表示[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本无法升级。 如果[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本未列出，该版本无法升级。  

||[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]|BizTalk Server 2013|
|---|---|---|---|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2013|是|是|是|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2010|是|是|是|  

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a>升级步骤  
  
1.  升级[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。   
  
2.  备份[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]数据库和你 HL7 消息架构。  
  
3.  备份下的任何文件 ***\<驱动器 >*: files\microsoft BizTalk Accelerator for HL7**已更改的文件夹。 例如，备份 SDK 中的文件。  
  
4.  安装你的版本的相应更新[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:  
  
    -   如果从 BTAHL7 2010 升级，安装**HL72010Patch.msp**。  
  
    -   如果从 BTAHL7 2013 升级，安装**HL72013Patch.msp**。  
    
  
5.  运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]安装程序。 请参阅[为 HL7 安装 BizTalk Accelerator](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  
  
6.  部署新 BTAHL7V2*x*常见项目。  
  
7.  重新部署所有其他程序集。  
  
8.  重建引用一个或多个 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 程序集的任何项目或程序集。 使用**BTSTask.exe**中\<*驱动器*>: files\microsoft BizTalk Server\<版本 >，请手动重新部署这些项目。  
  
9. 重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 服务。  
  
<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a>在多服务器环境中升级  
 在多服务器[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]环境，升级所有[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s，然后再升级[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]所有服务器上。 请按以下顺序迁移服务器：  
  
-   承载 BizTalk 组的服务器  
  
-   各个处理节点  
  
-   BAM 门户服务器  
  
## <a name="see-also"></a>另请参阅  
 [安装适用于 HL7 BizTalk 快捷键](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)