---
title: "更改要将重新生成字段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rekeyed fields
- Message Repair and New Submission, modifying fields
- Message Repair and New Submission, rekeyed fields
ms.assetid: aaf353f7-0e43-403e-b72a-88e5dd07f4ac
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc47d080b43b7679e76b9c6f8a0d8de1216daeaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="changing-fields-to-be-rekeyed"></a>更改字段以将重新生成
消息修复工作流，在验证步骤[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]从多个字段中删除数据，以便验证程序必须重新输入，或重新生成密钥，该数据。 你可以自定义 RekeyVerify 中的哪些字段[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体需要将重新生成。 这样做在 MrsrXpathConfig.xml 文件中，它位于\<*驱动器*>: files\microsoft BizTalk Accelerator for SWIFT\MRSR 文件夹。  
  
 MrsrXpathConfig.xml 文件包含一系列处理的消息类型的节点。 每个消息类型节点包含一系列字段节点，每个字段一个。 你可以更改要通过在文本编辑器中，（如记事本） 打开 MrsrXpathConfig.xml 和添加或删除要重新生成的字段\<路径 > 字段的节点。  
  
 \<路径 > 节点所包含的消息类型和字段的路径。 例如，将为以下 MT103 消息的输入应用程序标头块中的目标路径条目：  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 它是最简单的方法添加新字段以将重新生成，方法是通过复制，然后粘贴现有条目，然后将更改相关的路径。 例如，若要强制重新生成密钥的 MT103 消息的值日期货币 Interbank 结算量 32A 部分中的日期字段，请为以下三个替换到前面的代码。 代码的其余部分保持不变。  
  
|将此替换|与此|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 有关重新生成密钥字段的详细信息，请参阅[消息修复和新的提交中的特殊处理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)。