---
title: 更改要将重新生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- rekeyed fields
- Message Repair and New Submission, modifying fields
- Message Repair and New Submission, rekeyed fields
ms.assetid: aaf353f7-0e43-403e-b72a-88e5dd07f4ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0468a692ecb7099920fca1c4714feb8ee9c1dfce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378906"
---
# <a name="changing-fields-to-be-rekeyed"></a>更改要将重新生成
消息修复工作流，在验证步骤[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，以便验证程序必须重新输入，或重新生成密钥，该数据从多个字段中删除数据。 你可以自定义 RekeyVerify 中的哪些字段[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体需要进行重新生成。 这样做在 MrsrXpathConfig.xml 文件中，它位于\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR 文件夹。  
  
 MrsrXpathConfig.xml 文件包含一系列处理的消息类型的节点。 消息类型的每个节点包含一系列字段节点，每个字段一个。 你可以通过在文本编辑器中，（如记事本） 打开 MrsrXpathConfig.xml 和添加或删除要重新生成的字段\<路径\>字段节点。  
  
 \<路径\>节点包含有关消息类型和字段的路径。 例如，以下是中输入应用程序标头块的 MT103 消息的目标路径的条目：  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 它是最简单的方法添加新字段以进行重新生成复制和粘贴某个现有条目，然后，然后更改相关的路径。 例如，若要强制重新生成密钥的 MT103 消息的值日期货币 Interbank 结算量 32A 部分中的日期字段，使以下三个替换为前面的代码。 代码的其余部分保持不变。  
  
|将此替换|与此|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 有关重新生成密钥字段的详细信息，请参阅[消息修复和新提交中的特殊处理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)。