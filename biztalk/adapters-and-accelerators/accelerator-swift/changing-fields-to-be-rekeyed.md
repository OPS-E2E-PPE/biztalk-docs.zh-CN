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
# <a name="changing-fields-to-be-rekeyed"></a><span data-ttu-id="bb5ac-102">更改要将重新生成</span><span class="sxs-lookup"><span data-stu-id="bb5ac-102">Changing Fields to Be Rekeyed</span></span>
<span data-ttu-id="bb5ac-103">消息修复工作流，在验证步骤[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，以便验证程序必须重新输入，或重新生成密钥，该数据从多个字段中删除数据。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-103">In the verification step of a message repair workflow, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] removes the data from a number of fields so that the verifier must re-enter, or rekey, that data.</span></span> <span data-ttu-id="bb5ac-104">你可以自定义 RekeyVerify 中的哪些字段[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]窗体需要进行重新生成。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-104">You can customize which fields in the RekeyVerify [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] form need to be rekeyed.</span></span> <span data-ttu-id="bb5ac-105">这样做在 MrsrXpathConfig.xml 文件中，它位于\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-105">You do so in the MrsrXpathConfig.xml file, which is located in the \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR folder.</span></span>  
  
 <span data-ttu-id="bb5ac-106">MrsrXpathConfig.xml 文件包含一系列处理的消息类型的节点。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-106">The MrsrXpathConfig.xml file contains a series of nodes for the message type processed.</span></span> <span data-ttu-id="bb5ac-107">消息类型的每个节点包含一系列字段节点，每个字段一个。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-107">Each message-type node contains a series of field nodes, one for each field.</span></span> <span data-ttu-id="bb5ac-108">你可以通过在文本编辑器中，（如记事本） 打开 MrsrXpathConfig.xml 和添加或删除要重新生成的字段\<路径\>字段节点。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-108">You can change the fields to be rekeyed by opening MrsrXpathConfig.xml in a text editor, such as Notepad, and adding or removing a \<path\> node for the field.</span></span>  
  
 <span data-ttu-id="bb5ac-109">\<路径\>节点包含有关消息类型和字段的路径。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-109">The \<path\> node contains paths for the message type and the field.</span></span> <span data-ttu-id="bb5ac-110">例如，以下是中输入应用程序标头块的 MT103 消息的目标路径的条目：</span><span class="sxs-lookup"><span data-stu-id="bb5ac-110">For example, the entry for the Destination Path in the Input Application Header Block of an MT103 message is the following:</span></span>  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 <span data-ttu-id="bb5ac-111">它是最简单的方法添加新字段以进行重新生成复制和粘贴某个现有条目，然后，然后更改相关的路径。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-111">It is easiest to add a new field to be rekeyed by copying and then pasting an existing entry, and then changing the relevant paths.</span></span> <span data-ttu-id="bb5ac-112">例如，若要强制重新生成密钥的 MT103 消息的值日期货币 Interbank 结算量 32A 部分中的日期字段，使以下三个替换为前面的代码。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-112">For example, to force rekey of the Date field in the Value Date Currency Interbank Settled Amount 32A section of an MT103 message, make the following three replacements to the preceding code.</span></span> <span data-ttu-id="bb5ac-113">代码的其余部分保持不变。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-113">The rest of the code remains the same.</span></span>  
  
|<span data-ttu-id="bb5ac-114">将此替换</span><span class="sxs-lookup"><span data-stu-id="bb5ac-114">Replace this</span></span>|<span data-ttu-id="bb5ac-115">与此</span><span class="sxs-lookup"><span data-stu-id="bb5ac-115">With this</span></span>|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 <span data-ttu-id="bb5ac-116">有关重新生成密钥字段的详细信息，请参阅[消息修复和新提交中的特殊处理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="bb5ac-116">For more information about rekeying fields, see [Special Processing in Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md).</span></span>