---
title: Integer 属性值不是有效整数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa97f3dd-4a01-4007-b23a-820cbebbc083
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5810c6c4bd17bde5b9afc004825a756e80bc35
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986694"
---
# <a name="the-integer-property-value-is-not-a-valid-integer"></a><span data-ttu-id="8fff5-102">integer 属性值不是有效整数</span><span class="sxs-lookup"><span data-stu-id="8fff5-102">The integer property value is not a valid integer</span></span>
## <a name="details"></a><span data-ttu-id="8fff5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="8fff5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8fff5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="8fff5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8fff5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="8fff5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8fff5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8fff5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8fff5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="8fff5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8fff5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="8fff5-108"> EDI</span></span> |
|    <span data-ttu-id="8fff5-109">组件</span><span class="sxs-lookup"><span data-stu-id="8fff5-109">Component</span></span>    |                                    <span data-ttu-id="8fff5-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="8fff5-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="8fff5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="8fff5-111">Symbolic Name</span></span>  |                              <span data-ttu-id="8fff5-112">InvalidIntegerPropertyValue</span><span class="sxs-lookup"><span data-stu-id="8fff5-112">InvalidIntegerPropertyValue</span></span>                               |
|  <span data-ttu-id="8fff5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="8fff5-113">Message Text</span></span>   |                   <span data-ttu-id="8fff5-114">integer 属性值不是有效整数</span><span class="sxs-lookup"><span data-stu-id="8fff5-114">The integer property value is not a valid integer</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="8fff5-115">解释</span><span class="sxs-lookup"><span data-stu-id="8fff5-115">Explanation</span></span>  
 <span data-ttu-id="8fff5-116">此错误/警告/信息事件表明在“批处理筛选器”对话框的某一行中为属性输入的值无效，因为该属性需要 integer 值，但输入的值不是 integer 值。</span><span class="sxs-lookup"><span data-stu-id="8fff5-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required an integer value, but the value entered was not an integer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8fff5-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="8fff5-117">User Action</span></span>  
 <span data-ttu-id="8fff5-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="8fff5-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="8fff5-119">确保为必须是 integer 的属性输入的值确实是 integer。</span><span class="sxs-lookup"><span data-stu-id="8fff5-119">Make sure that the value entered for a property that must be an integer is in fact an integer.</span></span>