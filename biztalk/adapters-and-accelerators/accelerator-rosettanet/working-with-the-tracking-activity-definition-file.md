---
title: "使用跟踪活动定义文件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751b05f28682ecc0a0230fc924cf706d0531784d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-the-tracking-activity-definition-file"></a>使用跟踪活动定义文件
活动定义文件包含有关跟踪的信息中的过程和消息活动[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用此文件来管理跟踪中 BizTalk 业务活动监视 (BAM) 的数据。 定义文件是一个 XML 文件 (Tracking.xml)，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在\<*驱动器*>: files\microsoft BizTalk 2013 Accelerator RosettaNet \BAMTracking 文件夹。 Tracking.xml 中定义的活动可能足以满足你的需要。  
  
 有关跟踪活动、 视图和表的详细信息，请参阅[增强跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)。 有关 BAM 的详细信息，请参阅 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 帮助中的“业务活动监视 (BAM)”。  
  
## <a name="managing-tracking-views"></a>管理跟踪视图  
 不使用 BizTalk 跟踪配置文件编辑器[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]跟踪。 跟踪点无法自定义；不要更改活动定义。 但是，你可以管理 BAM 视图和部署。 若要执行此操作，可修改[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格 (Tracking.xls)，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]安装程序将安装在\<*驱动器*>: files\microsoft BizTalk 2013 Accelerator RosettaNet\BAMTracking 文件夹。 有关详细信息，请参阅下述“管理跟踪视图”。  
  
 如果 Tracking.xml 中定义的视图不能够满足你的需要，你可以按下述方法为 BAM 中跟踪的信息定义其他视图。  
  
#### <a name="to-create-different-tracking-views"></a>创建其他跟踪视图  
  
1.  单击 **“启动”**，再单击 **“运行”**。 输入**cmd**中运行对话框中，然后单击打开的文本框中**确定**。 在命令行对话框中，输入下面的代码，以取消部署 tracking.xml，然后单击**确定**:  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
    bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename>.xml"  
    ```  
  
2.  在[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，移动到*\<驱动器 >*: files\microsoft BizTalk 2013 Accelerator for RosettaNet \BAM 跟踪。 双击 Tracking.xls。  
  
3.  在业务活动监视中创建新视图。 有关如何在业务活动监视中创建新视图的信息，请参阅 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 帮助中的“管理业务活动监视”。  
  
4.  单击**BAM**，然后单击**导出到 XML**。 将移动到所需的位置，输入 （之外 Tracking.xml) 的文件名称，然后单击**保存**。  
  
    > [!IMPORTANT]
    >  当你在跟踪 XLS 文件中定义新的跟踪视图并从该跟踪 XLS 文件导出 XML 文件时，某些新字段名可能会稍做修改。 将你的自定义跟踪 XML 文件中的字段与 BTARN 安装程序所安装的标准 tracking.xml 字段进行查验，更正此问题。  
  
5.  部署新的跟踪 XML 文件。 若要执行此操作，请单击**启动**，然后单击**运行**。 输入**cmd**中运行对话框中，然后单击打开的文本框中**确定**。 在命令行对话框中，输入下面的代码，以部署新的跟踪文件，然后单击**确定**。 建议重命名跟踪 XML 文件，以便不会覆盖默认的 tracking.xml 文件。  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
    bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename>.xml"  
    ```  
  
 BAM 中跟踪的信息不包括消息内容，因为存储在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据库。  
  
 可以使用业务活动监视管理实用工具管理 BAM 跟踪的部署。 有关此实用工具的详细信息，请参阅 [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 帮助中的“使用业务活动监视管理实用工具”。  
  
## <a name="activity-fields"></a>活动字段  
 以下是活动定义文件中消息活动的字段：  
  
-   ActivityName  
  
-   类别  
  
-   ContentKey  
  
-   DestinationPartyName  
  
-   ErrorDescription  
  
-   HasError  
  
-   InReplyToMessageID  
  
-   IsReceived  
  
-   MessageTrackingID  
  
-   NoFPipInstance  
  
-   PipCode  
  
-   PipInstanceID  
  
-   PiPVersion  
  
-   SourcePartName  
  
-   时间戳  
  
 以下是活动定义文件中流程活动的字段：  
  
-   EndTime  
  
-   InitiatorPartyName  
  
-   IsInitiatorRole  
  
-   PipCode  
  
-   PipInstanceID  
  
-   PipName  
  
-   PipVersion  
  
-   ResponderPartyName  
  
-   StartTime  
  
-   状态  
  
## <a name="see-also"></a>另请参阅  
 [增强的跟踪](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)