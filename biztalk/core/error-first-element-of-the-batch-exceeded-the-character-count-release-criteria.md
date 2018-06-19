---
title: 批处理的第一个元素超过了所字符计数发布条件设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b06f8f-247d-4e93-8c4e-5e86e4ad70c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 746fbfabb2fe411310735f66c6d8a8398a94a5dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241549"
---
# <a name="the-first-element-of-the-batch-exceeded-the-character-count-release-criteria-set"></a><span data-ttu-id="14312-102">批的第一个元素超出了字符计数释放条件集</span><span class="sxs-lookup"><span data-stu-id="14312-102">The first element of the batch exceeded the character count release criteria set</span></span>
## <a name="details"></a><span data-ttu-id="14312-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="14312-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="14312-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="14312-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="14312-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="14312-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="14312-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="14312-106">Event ID</span></span>|-|  
|<span data-ttu-id="14312-107">事件源</span><span class="sxs-lookup"><span data-stu-id="14312-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="14312-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="14312-108"> EDI</span></span>|  
|<span data-ttu-id="14312-109">组件</span><span class="sxs-lookup"><span data-stu-id="14312-109">Component</span></span>|<span data-ttu-id="14312-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="14312-110">Batching Engine</span></span>|  
|<span data-ttu-id="14312-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="14312-111">Symbolic Name</span></span>|<span data-ttu-id="14312-112">FirstElementExceededCharCount</span><span class="sxs-lookup"><span data-stu-id="14312-112">FirstElementExceededCharCount</span></span>|  
|<span data-ttu-id="14312-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="14312-113">Message Text</span></span>|<span data-ttu-id="14312-114">批处理的第一个元素超出了字符计数释放条件集。</span><span class="sxs-lookup"><span data-stu-id="14312-114">The first element of the batch exceeded the character count release criteria set.</span></span> <span data-ttu-id="14312-115">请更改字符计数释放条件，以便能处理此消息。</span><span class="sxs-lookup"><span data-stu-id="14312-115">Please change the character count release criteria to be able to process this message.</span></span> <span data-ttu-id="14312-116">该消息需要在修改设置后重新发送到批处理系统</span><span class="sxs-lookup"><span data-stu-id="14312-116">The message will need to be resent to the batching system after the settings are modified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="14312-117">解释</span><span class="sxs-lookup"><span data-stu-id="14312-117">Explanation</span></span>  
 <span data-ttu-id="14312-118">此错误/警告/信息事件表明批处理业务流程无法生成批处理的交换，因为由批处理业务流程选取的第一个批处理元素中的字符数已超过批处理发布条件的“交换中的最大字符数量”属性中指定的字符数。</span><span class="sxs-lookup"><span data-stu-id="14312-118">This Error/Warning/Information event indicates that the batching orchestration could not generate the batched interchange because the number of characters in the first batch element picked up by the batching orchestration exceeded the number of characters specified by the "Maximum number of characters in an interchange" property of the batch release criteria.</span></span> <span data-ttu-id="14312-119">请注意，与最大数量相比，字符数并不包含信封中的字符数。</span><span class="sxs-lookup"><span data-stu-id="14312-119">Note that the number of characters compared to the maximum does not include the number of characters in the envelope.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="14312-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="14312-120">User Action</span></span>  
 <span data-ttu-id="14312-121">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="14312-121">To resolve this error, do one of the following:</span></span>  
  
1.  <span data-ttu-id="14312-122">增加“作为交换接收方的参与方”的“EDI 属性”对话框的“交换批处理创建设置”页中“”属性。</span><span class="sxs-lookup"><span data-stu-id="14312-122">Increase the "Maximum number of characters in an interchange" property in the Interchange Batch Creation Settings Page of the EDI Properties dialog box for the party as interchange receiver.</span></span> <span data-ttu-id="14312-123">为此，您必须停止业务流程实例，增加属性中的最大字符数，然后重新启动业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="14312-123">To do so, you must stop the orchestration instance, increase the maximum number of characters in the property, and then restart the orchestration instance.</span></span> <span data-ttu-id="14312-124">让发送方重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="14312-124">Have the sender resend the message.</span></span>  
  
2.  <span data-ttu-id="14312-125">让发送方发送字符数低于最大字符数的事务集。</span><span class="sxs-lookup"><span data-stu-id="14312-125">Have the sender send transaction sets that have fewer characters than the maximum number of characters.</span></span>