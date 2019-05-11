---
title: BRE 部署实用工具 |Microsoft Docs
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
ms.openlocfilehash: d59a06b55e4d30e9e87a68adbf830dad38578f3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378971"
---
# <a name="bre-deployment-utility"></a>BRE 部署实用工具
您可以使用 BRE 部署实用工具来发布和部署业务规则引擎 (BRE) 的词汇和策略所需的 SWIFT 架构。 启用消息类型的 BRE 验证需要发布和部署这些词汇和策略。  
  
 您还可以通过使用 SWIFT 标准发布指南 (SRGs) 来标识所需的规则，然后使用 Microsoft 部署业务规则[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]业务规则编辑器工具来部署词汇和策略。 但是，使用 BRE 部署实用工具要容易得多。  
  
 BRE 部署实用工具完成以下任务：  
  
- 检查你指定的已部署程序集并确定部署的程序集的消息架构。  
  
- 将发布[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml 并[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml 词汇所需的 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]处理的业务规则。  
  
- 发布和部署的 SWIFT 基本策略 （引用策略、 参与方标识符策略和网络规则策略） 与消息架构相关联。  
  
- 发布和部署主策略以及与每个消息架构相关联的验证策略。  
  
- 生成日志文件，该值指示所需的所有步骤。 此文件是在 BREDeploymentLog.txt \<*驱动器*\>: \Documents and Settings\All Users\Application Data 文件夹。  
  
  > [!NOTE]
  >  BRE 部署实用工具不部署 BIC Master 策略和 BIC 验证策略。 您必须部署这些使用规则引擎部署向导。  
  > 
  > [!NOTE]
  >  如果已安装[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]中的非默认目录 (C:\Program Files\Microsoft 以外[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)])，或在 64 位计算机上工作，BRE 部署实用工具将无法正常工作之前更改中的路径BREDeployment.exe.config 文件。 此配置文件位于\<*驱动器*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools 文件夹。 若要更新该实用程序的配置，在记事本中，打开 BREDeployment.exe.config 和更改的基本策略、 架构和词汇目录的文件夹。  
  
  此外可以使用部署实用工具来逆转此过程中，取消部署和取消发布的策略和词汇。 此实用工具已同时部署和取消部署功能。  
  
### <a name="to-use-the-bre-deployment-utility"></a>若要使用 BRE 部署实用工具  
  
1.  单击**启动**，依次指向**程序**，指向**Microsoft BizTalk Accelerator for SWIFT**，然后单击**BRE 部署实用工具**。  
  
2.  BRE 部署实用工具中单击**浏览**。  
  
3.  选择部署的程序集或程序集要发布和部署词汇和策略，然后单击**确定**。  
  
4.  单击**部署**。  
  
    > [!NOTE]
    >  根据使用该程序集部署的架构，BRE 部署实用工具都要通过确定相关的规则并将其发布与 BRE 一起使用的过程。 完成后，BRE 部署实用工具将显示以下消息：**完成部署后**。 使用业务规则编辑器来验证成功的部署。  
  
    > [!NOTE]
    >  若要取消部署策略和词汇，请单击**Undeploy**。 取消部署过程取消 A4SWIFT_CodeLists.xml 和 A4SWIFT_Functions.xml 词汇，可能由其他已部署的策略未部署。  
  
5.  找到\<*驱动器*\>: \Documents and Settings\All Users\Application Data，若要确认该实用程序创建日志文件 BREDeploymentLog.txt。  
  
    > [!NOTE]
    >  可以使用文本编辑器以确认每个部署步骤来打开日志文件。  
  
## <a name="see-also"></a>请参阅  
 [工具](../../adapters-and-accelerators/accelerator-swift/tools.md)