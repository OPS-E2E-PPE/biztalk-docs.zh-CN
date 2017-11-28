---
title: "Batch 元素超过了配置的最大字符计数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ad12733-295a-43ba-8147-34c8716c2d37
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dac259db250a88e434efb649a2baf2e75b805a40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-batch-element-exceeded-the-maximum-configured-character-count"></a><span data-ttu-id="76b34-102">批处理元素已超过配置的最大字符数</span><span class="sxs-lookup"><span data-stu-id="76b34-102">The batch element exceeded the maximum configured character count</span></span>
## <a name="details"></a><span data-ttu-id="76b34-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="76b34-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76b34-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="76b34-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="76b34-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="76b34-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="76b34-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="76b34-106">Event ID</span></span>|-|  
|<span data-ttu-id="76b34-107">事件源</span><span class="sxs-lookup"><span data-stu-id="76b34-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="76b34-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="76b34-108"> EDI</span></span>|  
|<span data-ttu-id="76b34-109">组件</span><span class="sxs-lookup"><span data-stu-id="76b34-109">Component</span></span>|<span data-ttu-id="76b34-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="76b34-110">Batching Engine</span></span>|  
|<span data-ttu-id="76b34-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="76b34-111">Symbolic Name</span></span>|<span data-ttu-id="76b34-112">MessageExceededCharacterCount</span><span class="sxs-lookup"><span data-stu-id="76b34-112">MessageExceededCharacterCount</span></span>|  
|<span data-ttu-id="76b34-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="76b34-113">Message Text</span></span>|<span data-ttu-id="76b34-114">批处理元素已超过配置的最大字符数</span><span class="sxs-lookup"><span data-stu-id="76b34-114">The batch element exceeded the maximum configured character count</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="76b34-115">解释</span><span class="sxs-lookup"><span data-stu-id="76b34-115">Explanation</span></span>  
 <span data-ttu-id="76b34-116">此错误/警告/信息事件表明批处理业务流程无法生成经过批处理的交换，因为由批处理业务流程选取的批处理元素中的字符数已超过批处理发布条件的“交换中的最大字符数量”属性中指定的字符数。</span><span class="sxs-lookup"><span data-stu-id="76b34-116">This Error/Warning/Information event indicates that the batching orchestration could not generate the batched interchange because the number of characters in a batch element picked up by the batching orchestration exceeds the number of characters specified by the "Maximum number of characters in an interchange" property of the batch release criteria.</span></span> <span data-ttu-id="76b34-117">生成此错误消息的批处理元素将不是为批处理所选取的第一个批处理元素，但第一个批处理元素之后的批处理元素已进行批处理。</span><span class="sxs-lookup"><span data-stu-id="76b34-117">The batch element that generates this error message will not be the first batch element picked up for a batch, but a batch element after the first element has already been batched.</span></span> <span data-ttu-id="76b34-118">请注意，与最大数量相比，字符数并不包含信封中的字符数。</span><span class="sxs-lookup"><span data-stu-id="76b34-118">Note that the number of characters compared to the maximum does not include the number of characters in the envelope.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="76b34-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="76b34-119">User Action</span></span>  
 <span data-ttu-id="76b34-120">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="76b34-120">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="76b34-121">增加“作为交换接收方的参与方”的“EDI 属性”对话框的“交换批处理创建设置”页中“”属性。</span><span class="sxs-lookup"><span data-stu-id="76b34-121">Increase the "Maximum number of characters in an interchange" property in the Interchange Batch Creation Settings Page of the EDI Properties dialog box for the party as interchange receiver.</span></span> <span data-ttu-id="76b34-122">为此，您必须停止业务流程实例，增加属性中的最大字符数，然后重新启动业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="76b34-122">To do so, you must stop the orchestration instance, increase the maximum number of characters in the property, and then restart the orchestration instance.</span></span>  
  
2.  <span data-ttu-id="76b34-123">让发送方发送字符数低于最大字符数的事务集。</span><span class="sxs-lookup"><span data-stu-id="76b34-123">Have the sender send transaction sets that have fewer characters than the maximum number of characters.</span></span>