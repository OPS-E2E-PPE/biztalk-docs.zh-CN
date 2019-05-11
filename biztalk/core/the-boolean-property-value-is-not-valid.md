---
title: 布尔属性值不是有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62b6c178-f8ea-451a-b2dc-9396c24c0f5b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10bece42e313e58940ba5af7be3b26d0e786268a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298837"
---
# <a name="the-boolean-property-value-is-not-valid"></a><span data-ttu-id="cbc28-102">布尔属性值无效</span><span class="sxs-lookup"><span data-stu-id="cbc28-102">The boolean property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="cbc28-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cbc28-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cbc28-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cbc28-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cbc28-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="cbc28-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cbc28-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cbc28-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cbc28-107">事件源</span><span class="sxs-lookup"><span data-stu-id="cbc28-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="cbc28-108">EDI</span><span class="sxs-lookup"><span data-stu-id="cbc28-108">EDI</span></span> |
|    <span data-ttu-id="cbc28-109">组件</span><span class="sxs-lookup"><span data-stu-id="cbc28-109">Component</span></span>    |                                    <span data-ttu-id="cbc28-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="cbc28-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="cbc28-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="cbc28-111">Symbolic Name</span></span>  |                              <span data-ttu-id="cbc28-112">InvalidBooleanPropertyValue</span><span class="sxs-lookup"><span data-stu-id="cbc28-112">InvalidBooleanPropertyValue</span></span>                               |
|  <span data-ttu-id="cbc28-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="cbc28-113">Message Text</span></span>   |                        <span data-ttu-id="cbc28-114">布尔属性值无效</span><span class="sxs-lookup"><span data-stu-id="cbc28-114">The boolean property value is not valid</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="cbc28-115">解释</span><span class="sxs-lookup"><span data-stu-id="cbc28-115">Explanation</span></span>  
 <span data-ttu-id="cbc28-116">此错误/警告/信息事件表明，输入批处理筛选器对话框中的某一行中的属性的值无效，因为该属性需要一个布尔值，但输入的值不是一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="cbc28-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a boolean value, but the value entered was not a boolean.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cbc28-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="cbc28-117">User Action</span></span>  
 <span data-ttu-id="cbc28-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="cbc28-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="cbc28-119">请确保为需要一个布尔值属性，输入的值实际上是一个布尔值。</span><span class="sxs-lookup"><span data-stu-id="cbc28-119">Make sure that the value entered for a property that requires a boolean value is in fact a boolean.</span></span>