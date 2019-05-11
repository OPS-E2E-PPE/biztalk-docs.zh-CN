---
title: 使用跟踪活动定义文件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f528125d0fe25139dbd7b8e4a2a2792f42d9264
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379109"
---
# <a name="working-with-the-tracking-activity-definition-file"></a>使用跟踪活动定义文件
活动定义文件包含有关跟踪的信息在 Microsoft® 流程和消息活动[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 使用此文件来管理数据跟踪在 BizTalk 业务活动监视 (BAM)。 定义文件是一个 XML 文件 (Tracking.xml)，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装\<*驱动器*\>: files\microsoft BizTalk 2013 Accelerator for RosettaNet \BAMTracking 文件夹。 Tracking.xml 中定义的活动可能足以满足您的要求。  
  
 有关跟踪活动、 视图和表的详细信息，请参阅[增强跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)。 有关 BAM 的详细信息，请参阅"业务活动监视 (BAM)"BizTalk Server 帮助中。  
  
## <a name="managing-tracking-views"></a>管理跟踪视图  
 不使用与 BizTalk 跟踪配置文件编辑器[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]跟踪。 跟踪点不是可自定义;不要更改活动定义。 但是，你可以管理 BAM 视图和部署。 若要执行此操作，你修改[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格 (Tracking.xls)，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装\<*驱动器*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking 文件夹。 有关详细信息，请参阅"管理跟踪视图"下面。  
  
 如果 Tracking.xml 中定义的视图不满足需求，可以定义不同的视图，如下所示在 BAM 中跟踪的信息。  
  
#### <a name="to-create-different-tracking-views"></a>若要创建其他跟踪视图  
  
1. 单击 **“启动”**，再单击 **“运行”**。 输入**cmd**的运行对话框，然后单击打开的文本框中**确定**。 在命令行对话框中，输入以下代码取消部署 tracking.xml，然后单击**确定**:  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
2. 在中[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，转到*\<驱动器\>*: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM 跟踪。 双击 Tracking.xls。  
  
3. 在业务活动监视中创建一个新的视图。 有关如何执行此操作的信息，请参阅"管理业务活动监视"BizTalk Server 帮助中。  
  
4. 单击**BAM**，然后单击**导出到 XML**。 将移动到所需的位置，输入文件的名称 （不能是 Tracking.xml)，并单击**保存**。  
  
   > [!IMPORTANT]
   >  当您在跟踪 XLS 文件中定义新的跟踪视图并从该跟踪 XLS 文件导出 XML 文件时，一些新字段名称可能略有修改。 更正此错误： 验证字段中你的自定义跟踪 XML 文件是否符合由 BTARN 安装程序安装的标准 tracking.xml 字段。  
  
5. 部署新的跟踪 XML 文件。 若要执行此操作，请单击**启动**，然后单击**运行**。 输入**cmd**的运行对话框，然后单击打开的文本框中**确定**。 在命令行对话框中，输入以下代码以部署新的跟踪文件，然后单击**确定**。 建议，以便不会覆盖默认的 tracking.xml 文件重命名跟踪 XML 文件。  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
   在 BAM 中跟踪的信息不包括消息内容，因为存储在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据库。  
  
   你可以管理 BAM 跟踪使用业务活动监视管理实用程序的部署。 有关此实用工具的详细信息，请参阅"使用业务活动监视管理实用工具"BizTalk Server 帮助中。  
  
## <a name="activity-fields"></a>活动字段  
 活动定义文件中的消息活动的字段如下所示：  
  
- ActivityName  
  
- Category  
  
- ContentKey  
  
- DestinationPartyName  
  
- ErrorDescription  
  
- HasError  
  
- InReplyToMessageID  
  
- IsReceived  
  
- MessageTrackingID  
  
- NoFPipInstance  
  
- PipCode  
  
- PipInstanceID  
  
- PiPVersion  
  
- SourcePartName  
  
- 时间戳  
  
  活动定义文件中流程活动的字段如下所示：  
  
- EndTime  
  
- InitiatorPartyName  
  
- IsInitiatorRole  
  
- PipCode  
  
- PipInstanceID  
  
- PipName  
  
- PipVersion  
  
- ResponderPartyName  
  
- StartTime  
  
- “登录属性”  
  
## <a name="see-also"></a>请参阅  
 [增强的跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [管理配置、证书、数据库和安全性](manage-configuration-certificates-databases-security.md)