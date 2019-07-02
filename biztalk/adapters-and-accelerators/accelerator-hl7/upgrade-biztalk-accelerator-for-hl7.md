---
title: 升级 BizTalk Accelerator for HL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bb5bbc8f1b17f47ab6463eab33cfc9fee62cc6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286398"
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a>升级 BizTalk Accelerator for HL7
概述[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]升级过程。 

<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a>升级之前  

- 运行升级的用户必须是 BizTalk Administrators 组的成员。  

- 当你执行升级时，必须运行 SQL Server (MSSQLSERVER) 服务。  

- 不要运行无提示安装中升级。  

- 安装程序升级时，迁移现有[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]到较新版本的配置信息。  

- 升级时，注册表项和数据库会自动备份。  

- 中的文件 *\<驱动器\>* : \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7 文件夹进行更新。  

> [!IMPORTANT]
>  升级不会创建为升级后的文件中，新建一个文件夹，也不会更改现有文件夹的名称。  

<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a>支持的升级路径  
 下表列出了受支持[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以升级的版本。 "是"表示[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本可以升级。 "否"表示[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本无法升级。 如果[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]版本未列出，该版本无法升级。  


|                                                                                              | [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] | BizTalk Server 2013 |
|----------------------------------------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------|---------------------|
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2013 |                         是                          |                          是                          |         否          |
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2010 |                          否                          |                          是                          |         是         |

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a>升级步骤  

1. 升级[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。   

2. 备份[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]数据库和你 HL7 消息架构。  

3. 备份下的任何文件 * **\<驱动器\>*:\Program Files\Microsoft BizTalk Accelerator for HL7**已更改的文件夹。 例如，在 SDK 中的文件备份。  

4. 安装你的版本的相应更新[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:  

   -   如果从 BTAHL7 2010 进行升级，安装**HL72010Patch.msp**。  

   -   如果从 BTAHL7 2013 升级，安装**HL72013Patch.msp**。  


5. 运行[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]安装程序。 请参阅[安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。  

6. 部署新 BTAHL7V2*x*常见的项目。  

7. 重新部署所有其他程序集。  

8. 重新生成任何项目或具有对一个或多个引用的程序集[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]程序集。 使用**BTSTask.exe**中\<*驱动器*\>: \Program Files\Microsoft BizTalk Server\<版本\>，请手动重新部署这些项目。  

9. 重新启动 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 服务。  

<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a>在多服务器环境中升级  
 在多服务器[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]环境、 升级[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s，然后再升级[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]所有服务器上。 按以下顺序将服务器迁移：  

-   承载 BizTalk 组的服务器  

-   每个处理节点  

-   BAM 门户服务器  

## <a name="see-also"></a>请参阅  
 [安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)