---
title: Float 属性值不是有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79327dc6-fc5e-4290-9663-16bb64970d4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7f0752a05b9e692a002c80332032337230decb9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975070"
---
# <a name="the-float-property-value-is-not-valid"></a><span data-ttu-id="0a0a3-102">float 属性值无效</span><span class="sxs-lookup"><span data-stu-id="0a0a3-102">The float property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="0a0a3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0a0a3-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0a0a3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0a0a3-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0a0a3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0a0a3-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0a0a3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0a0a3-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0a0a3-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0a0a3-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a0a3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0a0a3-108"> EDI</span></span> |
|    <span data-ttu-id="0a0a3-109">组件</span><span class="sxs-lookup"><span data-stu-id="0a0a3-109">Component</span></span>    |                                    <span data-ttu-id="0a0a3-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="0a0a3-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="0a0a3-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0a0a3-111">Symbolic Name</span></span>  |                               <span data-ttu-id="0a0a3-112">InvalidFloatPropertyValue</span><span class="sxs-lookup"><span data-stu-id="0a0a3-112">InvalidFloatPropertyValue</span></span>                                |
|  <span data-ttu-id="0a0a3-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0a0a3-113">Message Text</span></span>   |                         <span data-ttu-id="0a0a3-114">float 属性值无效</span><span class="sxs-lookup"><span data-stu-id="0a0a3-114">The float property value is not valid</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="0a0a3-115">解释</span><span class="sxs-lookup"><span data-stu-id="0a0a3-115">Explanation</span></span>  
 <span data-ttu-id="0a0a3-116">此错误/警告/信息事件表明在“批处理筛选器”对话框的某一行中为属性输入的值无效，因为该属性需要 float 值，但输入的值不是 float 值。</span><span class="sxs-lookup"><span data-stu-id="0a0a3-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a float value, but the value entered was not a float.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a0a3-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0a0a3-117">User Action</span></span>  
 <span data-ttu-id="0a0a3-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="0a0a3-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="0a0a3-119">请确保为需要 float 值的属性输入的值确实是 float 值。</span><span class="sxs-lookup"><span data-stu-id="0a0a3-119">Make sure that the value entered for a property that requires a float is in fact a float.</span></span>