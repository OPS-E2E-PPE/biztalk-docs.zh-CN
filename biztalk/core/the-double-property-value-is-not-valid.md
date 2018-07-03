---
title: Double 属性值不是有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5e799d8-5fbb-4262-9d1f-4954ba0e0237
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c6a7ef649b9c7e7d04806f86c00bfc3cc6f59f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981318"
---
# <a name="the-double-property-value-is-not-valid"></a><span data-ttu-id="56693-102">double 属性值无效</span><span class="sxs-lookup"><span data-stu-id="56693-102">The double property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="56693-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="56693-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="56693-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="56693-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="56693-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="56693-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="56693-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="56693-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="56693-107">事件源</span><span class="sxs-lookup"><span data-stu-id="56693-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="56693-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="56693-108"> EDI</span></span> |
|    <span data-ttu-id="56693-109">组件</span><span class="sxs-lookup"><span data-stu-id="56693-109">Component</span></span>    |                                    <span data-ttu-id="56693-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="56693-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="56693-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="56693-111">Symbolic Name</span></span>  |                               <span data-ttu-id="56693-112">InvalidDoublePropertyValue</span><span class="sxs-lookup"><span data-stu-id="56693-112">InvalidDoublePropertyValue</span></span>                               |
|  <span data-ttu-id="56693-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="56693-113">Message Text</span></span>   |                         <span data-ttu-id="56693-114">double 属性值无效</span><span class="sxs-lookup"><span data-stu-id="56693-114">The double property value is not valid</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="56693-115">解释</span><span class="sxs-lookup"><span data-stu-id="56693-115">Explanation</span></span>  
 <span data-ttu-id="56693-116">此错误/警告/信息事件表明在“批处理筛选器”对话框的某一行中为属性输入的值无效，因为该属性需要双精度值，但输入的值不是双精度值。</span><span class="sxs-lookup"><span data-stu-id="56693-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a double value, but the value entered was not a double.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="56693-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="56693-117">User Action</span></span>  
 <span data-ttu-id="56693-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="56693-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="56693-119">请确保为需要双精度值的属性输入的值确实是双精度值。</span><span class="sxs-lookup"><span data-stu-id="56693-119">Make sure that the value entered for a property that requires a double is in fact a double.</span></span>