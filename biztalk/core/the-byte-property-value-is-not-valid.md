---
title: "字节属性值不是有效 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8599688-9f05-4983-8850-9ac1479ce9cc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5789ae17b5127b58de45e5c4764b4ef490c43f1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-byte-property-value-is-not-valid"></a><span data-ttu-id="261a5-102">byte 属性值无效</span><span class="sxs-lookup"><span data-stu-id="261a5-102">The byte property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="261a5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="261a5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="261a5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="261a5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="261a5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="261a5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="261a5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="261a5-106">Event ID</span></span>|-|  
|<span data-ttu-id="261a5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="261a5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="261a5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="261a5-108"> EDI</span></span>|  
|<span data-ttu-id="261a5-109">组件</span><span class="sxs-lookup"><span data-stu-id="261a5-109">Component</span></span>|<span data-ttu-id="261a5-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="261a5-110">Batching Engine</span></span>|  
|<span data-ttu-id="261a5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="261a5-111">Symbolic Name</span></span>|<span data-ttu-id="261a5-112">InvalidBytePropertyValue</span><span class="sxs-lookup"><span data-stu-id="261a5-112">InvalidBytePropertyValue</span></span>|  
|<span data-ttu-id="261a5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="261a5-113">Message Text</span></span>|<span data-ttu-id="261a5-114">byte 属性值无效</span><span class="sxs-lookup"><span data-stu-id="261a5-114">The byte property value is not valid</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="261a5-115">解释</span><span class="sxs-lookup"><span data-stu-id="261a5-115">Explanation</span></span>  
 <span data-ttu-id="261a5-116">此错误/警告/信息事件指示，输入批处理筛选器对话框中的行中的属性的值无效，因为属性所需的字节值，但输入的值不为一个字节。</span><span class="sxs-lookup"><span data-stu-id="261a5-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a byte value, but the value entered was not a byte.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="261a5-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="261a5-117">User Action</span></span>  
 <span data-ttu-id="261a5-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="261a5-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="261a5-119">请确保输入需要的字节值的属性的值实际上是一个字节。</span><span class="sxs-lookup"><span data-stu-id="261a5-119">Make sure that the value entered for a property that requires a byte value is in fact a byte.</span></span>