---
title: 不是有效的字符串属性名称。 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a0641e4-1267-44a0-8777-bd6e2baf1088
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 944d9a4722f0c97ab09b66159bc04fc4715e01ef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989854"
---
# <a name="the-property-name-is-not-a-valid-string"></a><span data-ttu-id="237e2-102">属性名称不是有效字符串</span><span class="sxs-lookup"><span data-stu-id="237e2-102">The property name is not a valid string</span></span>
## <a name="details"></a><span data-ttu-id="237e2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="237e2-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="237e2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="237e2-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="237e2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="237e2-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="237e2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="237e2-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="237e2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="237e2-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="237e2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="237e2-108"> EDI</span></span> |
|    <span data-ttu-id="237e2-109">组件</span><span class="sxs-lookup"><span data-stu-id="237e2-109">Component</span></span>    |                                    <span data-ttu-id="237e2-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="237e2-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="237e2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="237e2-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="237e2-112">InvalidPropertyName</span><span class="sxs-lookup"><span data-stu-id="237e2-112">InvalidPropertyName</span></span>                                   |
|  <span data-ttu-id="237e2-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="237e2-113">Message Text</span></span>   |                        <span data-ttu-id="237e2-114">属性名称不是有效字符串</span><span class="sxs-lookup"><span data-stu-id="237e2-114">The property name is not a valid string</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="237e2-115">解释</span><span class="sxs-lookup"><span data-stu-id="237e2-115">Explanation</span></span>  
 <span data-ttu-id="237e2-116">此错误/警告/信息事件表明，在批处理筛选器对话框中为属性输入的名称无效，因为属性名称不是一个字符串，根据需要。</span><span class="sxs-lookup"><span data-stu-id="237e2-116">This Error/Warning/Information event indicates that the name entered for a property in the Batch Filter dialog box was invalid, because the property name was not a string, as required.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="237e2-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="237e2-117">User Action</span></span>  
 <span data-ttu-id="237e2-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="237e2-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="237e2-119">确保所有属性名称都是字符串。</span><span class="sxs-lookup"><span data-stu-id="237e2-119">Make sure that all property names are strings.</span></span>