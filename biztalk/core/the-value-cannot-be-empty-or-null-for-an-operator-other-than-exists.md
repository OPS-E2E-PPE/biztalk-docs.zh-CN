---
title: 值不能为空或为 null Exists 之外的运算符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44de42c8-eab7-4b13-b55a-d33eabe75c52
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da58cdbb1ba351d5f9500587facc99026a503176
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977326"
---
# <a name="the-value-cannot-be-empty-or-null-for-an-operator-other-than-exists"></a><span data-ttu-id="871a8-102">对于除 Exists 之外的运算符来说，值不能为空或为 Null</span><span class="sxs-lookup"><span data-stu-id="871a8-102">The value cannot be empty or null for an operator other than Exists</span></span>
## <a name="details"></a><span data-ttu-id="871a8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="871a8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="871a8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="871a8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="871a8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="871a8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="871a8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="871a8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="871a8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="871a8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="871a8-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="871a8-108"> EDI</span></span> |
|    <span data-ttu-id="871a8-109">组件</span><span class="sxs-lookup"><span data-stu-id="871a8-109">Component</span></span>    |                                    <span data-ttu-id="871a8-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="871a8-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="871a8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="871a8-111">Symbolic Name</span></span>  |                                <span data-ttu-id="871a8-112">ValueCannotBeNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="871a8-112">ValueCannotBeNullOrEmpty</span></span>                                |
|  <span data-ttu-id="871a8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="871a8-113">Message Text</span></span>   |          <span data-ttu-id="871a8-114">对于除 Exists 之外的运算符来说，值不能为空或为 Null</span><span class="sxs-lookup"><span data-stu-id="871a8-114">The value cannot be empty or null for an operator other than Exists</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="871a8-115">解释</span><span class="sxs-lookup"><span data-stu-id="871a8-115">Explanation</span></span>  
 <span data-ttu-id="871a8-116">此错误/警告/信息事件表明在“批处理筛选器”对话框的某一行中为属性输入的值无效，因为该运算符不是 Exists，但输入的值为空或为 Null。</span><span class="sxs-lookup"><span data-stu-id="871a8-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the operator was not Exists, but the value entered was either empty or null.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="871a8-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="871a8-117">User Action</span></span>  
 <span data-ttu-id="871a8-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="871a8-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="871a8-119">确保当某一行的运算符不是 Exists 时，输入的值不为空或不为 Null。</span><span class="sxs-lookup"><span data-stu-id="871a8-119">Make sure that if the operator for a row is not Exists, the value entered is neither empty nor null.</span></span>