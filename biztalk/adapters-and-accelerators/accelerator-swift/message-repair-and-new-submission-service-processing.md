---
title: 消息修复和新提交服务处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages, MrsrRepair orchestration
- orchestrations, MrsrRepair orchestration
- InfoPath forms, valid forms
- messages, BAS
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
- messages, InfoPath forms
- Business Rule Engine
- MrsrRepair orchestration
- InfoPath forms, messages
- BAS, messages
ms.assetid: fe2ee009-bf63-4bc0-b231-ad8a2633719f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d527e789378a19fc22ef96677032f2f2d91c74d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377319"
---
# <a name="message-repair-and-new-submission-service-processing"></a>消息修复和新提交服务处理
MrsrRepair 业务流程将处理所有消息修复和新提交操作，包括以下处理：  

-   需要修复的消息  

-   未分析的消息  

-   MRSR 站点中创建的新消息  

## <a name="processing-messages-requiring-repair"></a>处理需要修复的消息  
 如果需要修复一条消息，业务流程是向你发出警报的传入消息来自拆装器。 如果角色功能设置为创建或修复，它只处理来自拆装器的消息。 MrsrRepair 业务流程订阅的消息从 MessageBox 中具有以下属性：  

```  
A4SWIFT_Failed==true AND  
BTS_Operation=="A4SWIFT_DasmMarkedAsFailed" AND  
A4SWIFT_SwiftBound==true  
```  

 用于消息修复和新提交的业务流程绑定到 Sts.Outbox.Location MrsrRepair 的入站的端口的接收位置。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序已安装此接收位置的默认值。 当用户提交回 MRSR 站点的消息，此接收位置提取消息，并将他们路由到 MrsrRepair 业务流程。  

 下表列出了有效[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体：  


| [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] 窗体 |       |       |              |              |       |
|-------------------------------------------------------------------------------|-------|-------|--------------|--------------|-------|
|                                     MT010                                     | MT011 | MT012 |    MT015     |    MT019     | MT020 |
|                                     MT021                                     | MT022 | MT023 |    MT028     |    MT029     | MT030 |
|                                     MT031                                     | MT032 | MT035 |    MT036     |    MT037     | MT039 |
|                                     MT041                                     | MT042 | MT043 |    MT044     |    MT045     | MT046 |
|                                     MT047                                     | MT048 | MT049 |    MT050     |    MT051     | MT052 |
|                                     MT055                                     | MT056 | MT057 |    MT059     |    MT061     | MT062 |
|                                     MT063                                     | MT064 | MT065 |    MT066     |    MT067     | MT068 |
|                                     MT069                                     | MT072 | MT073 |    MT074     |    MT075     | MT076 |
|                                     MT077                                     | MT081 | MT082 |    MT083     |    MT085     | MT087 |
|                                     MT090                                     | MT092 | MT094 |    MT102     |  MT102PLUS   | MT103 |
|                                   MT103Plus                                   | MT104 | MT105 |    MT106     |    MT107     | MT110 |
|                                     MT111                                     | MT112 | MT121 |    MT190     |    MT191     | MT192 |
|                                     MT195                                     | MT196 | MT198 |    MT199     |    MT200     | MT201 |
|                                     MT202                                     | MT203 | MT204 |    MT205     |    MT206     | MT207 |
|                                     MT210                                     | MT256 | MT290 |    MT291     |    MT292     | MT295 |
|                                     MT296                                     | MT298 | MT299 |    MT300     |    MT303     | MT304 |
|                                     MT305                                     | MT306 | MT307 |    MT308     |    MT320     | MT321 |
|                                     MT330                                     | MT340 | MT341 |    MT350     |    MT360     | MT361 |
|                                     MT362                                     | MT364 | MT365 |    MT380     |    MT381     | MT390 |
|                                     MT391                                     | MT392 | MT395 |    MT396     |    MT398     | MT399 |
|                                     MT400                                     | MT405 | MT410 |    MT412     |    MT416     | MT420 |
|                                     MT422                                     | MT430 | MT450 |    MT4555    |    MT456     | MT490 |
|                                     MT491                                     | MT492 | MT495 |    MT496     |    MT498     | MT499 |
|                                     MT500                                     | MT501 | MT502 |    MT503     |    MT504     | MT505 |
|                                     MT506                                     | MT507 | MT508 |    MT509     |    MT510     | MT513 |
|                                     MT514                                     | MT515 | MT516 |    MT517     |    MT518     | MT519 |
|                                     MT524                                     | MT526 | MT527 |    MT528     |    MT529     | MT535 |
|                                     MT536                                     | MT537 | MT538 |    MT540     |    MT541     | MT542 |
|                                     MT543                                     | MT544 | MT545 |    MT546     |    MT547     | MT548 |
|                                     MT549                                     | MT558 | MT559 |    MT564     |    MT565     | MT566 |
|                                     MT567                                     | MT568 | MT569 | MT574_IRSLST | MT574_W8BENO | MT575 |
|                                     MT576                                     | MT577 | MT578 |    MT579     |    MT581     | MT582 |
|                                     MT584                                     | MT586 | MT587 |    MT588     |    MT589     | MT590 |
|                                     MT591                                     | MT592 | MT595 |    MT596     |    MT598     | MT599 |
|                                     MT600                                     | MT601 | MT604 |    MT605     |    MT606     | MT607 |
|                                     MT643                                     | MT644 | MT645 |    MT646     |    MT649     | MT690 |
|                                     MT691                                     | MT692 | MT695 |    MT696     |    MT698     | MT699 |
|                                     MT700                                     | MT701 | MT705 |    MT707     |    MT710     | MT711 |
|                                     MT720                                     | MT721 | MT730 |    MT732     |    MT734     | MT740 |
|                                     MT742                                     | MT747 | MT750 |    MT752     |    MT754     | MT756 |
|                                     MT760                                     | MT767 | MT768 |    MT769     |    MT790     | MT791 |
|                                     MT792                                     | MT795 | MT796 |    MT798     |    MT799     |       |
|                                     MT800                                     | MT801 | MT802 |    MT810     |    MT812     | MT813 |
|                                     MT820                                     | MT821 | MT822 |    MT823     |    MT824     | MT890 |
|                                     MT891                                     | MT892 | MT895 |    MT896     |    MT898     | MT899 |
|                                     MT900                                     | MT910 | MT920 |    MT935     |    MT940     | MT941 |
|                                     MT942                                     | MT950 | MT960 |    MT961     |    MT962     | MT963 |
|                                     MT964                                     | MT965 | MT966 |    MT967     |    MT970     | MT971 |
|                                     MT972                                     | MT973 | MT985 |    Mt986     |    MT990     | MT991 |
|                                     MT992                                     | MT995 | MT996 |    MT998     |    MT999     |       |

## <a name="processing-unparsed-messages"></a>处理未分析的消息  
 如果无法分析一条消息，它设置相应的标记，然后将消息发送到 MRSR MrsrRepair 业务流程可确定适用于在修复站点收件箱[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]未分析的消息的窗体。 当业务流程接收消息时修复后时，它会设置 BTS。操作属性设置为"[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRCompleted"和[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed 属性设置为 False，然后将消息路由到 MessageBox。 这些属性确保修复未分析的消息不会再次进入消息修复进程。  

 未分析的修复形式被称为**未分析消息**。  

## <a name="processing-new-messages-created-in-mrsr"></a>处理在 MRSR 中创建的新消息  
 如果 MRSR 站点中创建 MrsrRepair 业务流程接收消息，业务流程向你发出警报的传入消息来自[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]（不反汇编程序） 和已签名消息。  

## <a name="common-operations"></a>常见的操作  
 MrsrRepair 业务流程执行一的系列常见操作的所有消息，无论它们需要修复的、 无法分析，或将新消息。 业务流程执行一个循环，执行常见操作的每个步骤的工作流，包括重新生成密钥验证、 创建、 修复和批准。 此业务流程使用无论部门和角色是什么。  

 这些常见的步骤包括：  

1. 将消息放在一个信封窗体。  

2. 将消息发送到 MRSR 站点。  

3. 从通过 Sts.Outbox.Location MRSR 站点 （在之后的用户操作） 接收的消息接收位置。 如果发生超时，业务流程处理超时值。如果用户是修复、 验证，或审核消息，而发生超时的时候[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]的修复收件箱，重置到修复阶段的工作流中返回的消息。  

   > [!NOTE]
   >  用于消息修复和新提交的业务流程绑定到 Sts.Outbox.Location MrsrRepair 的入站的端口的接收位置。 此接收位置必须绑定到其上安装的 MRSR 站点的服务器的 BizTalk 主机中运行。 该主机通常是 BizTalkServerApplication，但也可以是另一台主机。 如果它是另一台主机，必须验证主机绑定到的服务器具有 MRSR 站点上安装。  

4. 验证用户输入的签名正确的角色，并将存储该签名验证角色限制。  

5. 如果消息的内容已存储的上一步，比较接收从 MRSR 站点并存储消息的内容。 如果不存在匹配项，该业务流程将失败消息。  

6. 如果用户拒绝所做的更改将失败消息。  

7. 如果用户接受所做的更改，对消息执行 XSD 和 BRE 验证。  

8. 如果适用，将移动到下一步。  

## <a name="customizing-the-repair-orchestration"></a>自定义修复业务流程  
 可以添加预处理或后处理功能来自定义 MrsrRepair 业务流程。 例如，无法将业务流程添加到的预处理步骤，或添加现有的发送形状，以将属性升级之前的业务流程形状。 但是，无法创建或更改协议或与消息修复和新提交相关联的配置文件，因为 MrsrRepair 业务流程不会注意到它们。 无法添加新角色定义超出 repairer、 创建者、 验证程序或审批者。 也无法更改表的结构，或将功能添加到业务流程的核心。  

## <a name="business-rules-policies"></a>业务规则策略  
 修复过程中，修复业务流程调用 BizTalk 业务规则引擎 (BRE)，若要加载的消息类型，例如，MT103_Master_Policy.xml 的主策略。 业务流程传递 BRE，消息类型和正文。 消息的主策略包含一系列适用于该消息类型的所有其他策略。 BRE 加载为消息类型的所有策略。 这些策略包括 SWIFT_Reference_Policy、 SWIFT_PartyIdentifier_Policy、 网络规则策略和特定于消息类型的验证策略。 BRE 执行的所有策略中的组策略，而不考虑错误，列出并返回所有错误。