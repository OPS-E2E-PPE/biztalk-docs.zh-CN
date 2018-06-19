---
title: BRE 部署实用工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5868172b566a12ab6299e0eaabe12fa2153bfb97
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966811"
---
# <a name="bre-deployment-utility"></a>BRE 部署实用工具
你可以使用 BRE 部署实用工具进行发布和部署的业务规则引擎 (BRE) 词汇和 SWIFT 架构所需的策略。 启用消息类型的 BRE 验证需要发布和部署这些词汇和策略。  
  
 您还可以通过使用 SWIFT 标准版本指南 (SRGs) 以标识所需的规则，然后使用部署业务规则[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务规则编辑器工具，将部署的词汇和策略。 但是，使用 BRE 部署实用工具是要容易得多。  
  
 BRE 部署实用工具完成以下任务：  
  
-   检查你指定的部署程序集，并确定你的程序集部署的消息架构。  
  
-   发布[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml 和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml 词汇所需的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]处理的业务规则。  
  
-   发布和部署 SWIFT 基 （引用策略、 方标识符策略和网络规则策略） 与关联的策略的消息架构。  
  
-   发布和部署的主策略和与每个消息架构关联的验证策略。  
  
-   生成日志文件，该值指示所需的所有步骤。 此文件是在 BREDeploymentLog.txt \<*驱动器*\>: \Documents and Settings\All Users\Application 数据文件夹。  
  
    > [!NOTE]
    >  BRE 部署实用工具不部署 BIC Master 策略和 BIC 验证策略。 你必须部署这些使用规则引擎部署向导。  
  
    > [!NOTE]
    >  如果你已安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]在非默认的目录 (C:\Program Files\Microsoft 以外[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)])，或你正在 64 位计算机上，BRE 部署实用工具将无法正常工作之前更改中的路径BREDeployment.exe.config 文件。 此配置文件位于\<*驱动器*\>: files\microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools 文件夹。 若要更新该实用程序的配置，在记事本中，打开 BREDeployment.exe.config 和更改的基本策略、 架构和词汇目录的文件夹。  
  
 你可以使用部署实用工具要反转此过程中，取消部署和取消发布的策略和词汇。 该实用工具已两者进行部署，并取消部署功能。  
  
### <a name="to-use-the-bre-deployment-utility"></a>若要使用 BRE 部署实用工具  
  
1.  单击**启动**，指向**程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。  
  
2.  在 BRE 部署实用程序中，单击**浏览**。  
  
3.  选择部署的程序集或程序集要发布和部署的词汇和策略，然后单击**确定**。  
  
4.  单击**部署**。  
  
    > [!NOTE]
    >  根据使用该程序集部署的架构，BRE 部署实用工具将经历标识相关的规则，并将其发布以用于 BRE 的过程。 完成后，BRE 部署实用工具，则显示以下消息：**部署已完成**。 使用业务规则编辑器来验证成功部署。  
  
    > [!NOTE]
    >  若要取消部署的策略和词汇表，请单击**取消部署后再次**。 取消部署过程取消 A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇，可能由其他部署策略未部署。  
  
5.  找到\<*驱动器*\>: \Documents and Settings\All Users\Application 数据，以确认该实用程序创建日志文件 BREDeploymentLog.txt。  
  
    > [!NOTE]
    >  可以通过使用文本编辑器以确认每个部署步骤来打开日志文件。  
  
## <a name="see-also"></a>另请参阅  
 [工具](../../adapters-and-accelerators/accelerator-swift/tools.md)