---
title: "不是有效字符串的属性名称。 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a0641e4-1267-44a0-8777-bd6e2baf1088
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 787d38dce9336eefa3715b5edd09db2cc426332b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-property-name-is-not-a-valid-string"></a><span data-ttu-id="c57ce-102">不是有效字符串的属性名称。</span><span class="sxs-lookup"><span data-stu-id="c57ce-102">The property name is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="c57ce-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c57ce-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c57ce-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c57ce-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c57ce-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c57ce-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c57ce-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c57ce-106">Event ID</span></span>|-|  
|<span data-ttu-id="c57ce-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c57ce-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c57ce-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c57ce-108"> EDI</span></span>|  
|<span data-ttu-id="c57ce-109">组件</span><span class="sxs-lookup"><span data-stu-id="c57ce-109">Component</span></span>|<span data-ttu-id="c57ce-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="c57ce-110">Batching Engine</span></span>|  
|<span data-ttu-id="c57ce-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c57ce-111">Symbolic Name</span></span>|<span data-ttu-id="c57ce-112">InvalidPropertyName</span><span class="sxs-lookup"><span data-stu-id="c57ce-112">InvalidPropertyName</span></span>|  
|<span data-ttu-id="c57ce-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c57ce-113">Message Text</span></span>|<span data-ttu-id="c57ce-114">不是有效字符串的属性名称。</span><span class="sxs-lookup"><span data-stu-id="c57ce-114">The property name is not a valid string</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c57ce-115">解释</span><span class="sxs-lookup"><span data-stu-id="c57ce-115">Explanation</span></span>  
 <span data-ttu-id="c57ce-116">此错误/警告/信息事件指示，输入批处理筛选器对话框中的属性的名称无效，因为属性名称不是一个字符串，根据需要。</span><span class="sxs-lookup"><span data-stu-id="c57ce-116">This Error/Warning/Information event indicates that the name entered for a property in the Batch Filter dialog box was invalid, because the property name was not a string, as required.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c57ce-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c57ce-117">User Action</span></span>  
 <span data-ttu-id="c57ce-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="c57ce-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="c57ce-119">确保所有属性名称都是字符串。</span><span class="sxs-lookup"><span data-stu-id="c57ce-119">Make sure that all property names are strings.</span></span>