---
title: 属性值不是有效的字符串 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78df6aca-26b5-4d49-93b0-71de19f5c9dd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4724142a547d390f4d3882bfcf4a485e43710c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394080"
---
# <a name="the-property-value-is-not-a-valid-string"></a><span data-ttu-id="c97e8-102">属性值不是有效的字符串</span><span class="sxs-lookup"><span data-stu-id="c97e8-102">The property value is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="c97e8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c97e8-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c97e8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c97e8-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c97e8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c97e8-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c97e8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c97e8-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c97e8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c97e8-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c97e8-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c97e8-108">EDI</span></span> |
|    <span data-ttu-id="c97e8-109">组件</span><span class="sxs-lookup"><span data-stu-id="c97e8-109">Component</span></span>    |                                    <span data-ttu-id="c97e8-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="c97e8-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="c97e8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c97e8-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="c97e8-112">InvalidPropertyValue</span><span class="sxs-lookup"><span data-stu-id="c97e8-112">InvalidPropertyValue</span></span>                                  |
|  <span data-ttu-id="c97e8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c97e8-113">Message Text</span></span>   |                        <span data-ttu-id="c97e8-114">属性值不是有效的字符串</span><span class="sxs-lookup"><span data-stu-id="c97e8-114">The property value is not a valid string</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="c97e8-115">解释</span><span class="sxs-lookup"><span data-stu-id="c97e8-115">Explanation</span></span>  
 <span data-ttu-id="c97e8-116">此错误/警告/信息事件表明在“批处理筛选器”对话框的某一行中为属性输入的值无效，因为该属性需要字符串值，但输入的值不是字符串。</span><span class="sxs-lookup"><span data-stu-id="c97e8-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a string value, but the value entered was not a string.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c97e8-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c97e8-117">User Action</span></span>  
 <span data-ttu-id="c97e8-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="c97e8-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="c97e8-119">请确保为字符串属性输入的值是字符串。</span><span class="sxs-lookup"><span data-stu-id="c97e8-119">Make sure that the value entered for a string property is a string.</span></span>