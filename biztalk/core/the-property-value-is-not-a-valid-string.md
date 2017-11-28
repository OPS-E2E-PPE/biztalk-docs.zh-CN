---
title: "属性值不是有效字符串 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78df6aca-26b5-4d49-93b0-71de19f5c9dd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7dfcceba7944226f801101818c2bf8c96ac42ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-property-value-is-not-a-valid-string"></a><span data-ttu-id="f6484-102">属性值不是有效的字符串</span><span class="sxs-lookup"><span data-stu-id="f6484-102">The property value is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="f6484-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6484-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6484-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6484-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f6484-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6484-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f6484-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6484-106">Event ID</span></span>|-|  
|<span data-ttu-id="f6484-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f6484-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f6484-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f6484-108"> EDI</span></span>|  
|<span data-ttu-id="f6484-109">组件</span><span class="sxs-lookup"><span data-stu-id="f6484-109">Component</span></span>|<span data-ttu-id="f6484-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="f6484-110">Batching Engine</span></span>|  
|<span data-ttu-id="f6484-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6484-111">Symbolic Name</span></span>|<span data-ttu-id="f6484-112">InvalidPropertyValue</span><span class="sxs-lookup"><span data-stu-id="f6484-112">InvalidPropertyValue</span></span>|  
|<span data-ttu-id="f6484-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6484-113">Message Text</span></span>|<span data-ttu-id="f6484-114">属性值不是有效的字符串</span><span class="sxs-lookup"><span data-stu-id="f6484-114">The property value is not a valid string</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6484-115">解释</span><span class="sxs-lookup"><span data-stu-id="f6484-115">Explanation</span></span>  
 <span data-ttu-id="f6484-116">此错误/警告/信息事件表明在“批处理筛选器”对话框的某一行中为属性输入的值无效，因为该属性需要字符串值，但输入的值不是字符串。</span><span class="sxs-lookup"><span data-stu-id="f6484-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a string value, but the value entered was not a string.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6484-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6484-117">User Action</span></span>  
 <span data-ttu-id="f6484-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="f6484-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="f6484-119">请确保为字符串属性输入的值是字符串。</span><span class="sxs-lookup"><span data-stu-id="f6484-119">Make sure that the value entered for a string property is a string.</span></span>