---
title: Byte 属性值不是有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8599688-9f05-4983-8850-9ac1479ce9cc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ef443c74c47883d04bcad2c1da5bb9423f7c01d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977848"
---
# <a name="the-byte-property-value-is-not-valid"></a><span data-ttu-id="f1d74-102">byte 属性值无效</span><span class="sxs-lookup"><span data-stu-id="f1d74-102">The byte property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="f1d74-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f1d74-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f1d74-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f1d74-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f1d74-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f1d74-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f1d74-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f1d74-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f1d74-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f1d74-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f1d74-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f1d74-108"> EDI</span></span> |
|    <span data-ttu-id="f1d74-109">组件</span><span class="sxs-lookup"><span data-stu-id="f1d74-109">Component</span></span>    |                                    <span data-ttu-id="f1d74-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="f1d74-110">Batching Engine</span></span>                                     |
|  <span data-ttu-id="f1d74-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f1d74-111">Symbolic Name</span></span>  |                                <span data-ttu-id="f1d74-112">InvalidBytePropertyValue</span><span class="sxs-lookup"><span data-stu-id="f1d74-112">InvalidBytePropertyValue</span></span>                                |
|  <span data-ttu-id="f1d74-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f1d74-113">Message Text</span></span>   |                          <span data-ttu-id="f1d74-114">byte 属性值无效</span><span class="sxs-lookup"><span data-stu-id="f1d74-114">The byte property value is not valid</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="f1d74-115">解释</span><span class="sxs-lookup"><span data-stu-id="f1d74-115">Explanation</span></span>  
 <span data-ttu-id="f1d74-116">此错误/警告/信息事件表明，输入批处理筛选器对话框中的某一行中的属性的值无效，因为该属性需要一个字节值，但输入的值不是一个字节。</span><span class="sxs-lookup"><span data-stu-id="f1d74-116">This Error/Warning/Information event indicates that a value entered for a property in a row of the Batch Filter dialog box was invalid, because the property required a byte value, but the value entered was not a byte.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f1d74-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f1d74-117">User Action</span></span>  
 <span data-ttu-id="f1d74-118">若要解决此错误，请从“EDI 属性”对话框的“交换批处理创建设置”页中打开“批处理筛选器”对话框。</span><span class="sxs-lookup"><span data-stu-id="f1d74-118">To resolve this error, open the Batch Filter dialog box from within the Interchange Batch Creation Settings page of the EDI Properties dialog box.</span></span> <span data-ttu-id="f1d74-119">请确保输入需要的字节值的属性的值实际上是一个字节。</span><span class="sxs-lookup"><span data-stu-id="f1d74-119">Make sure that the value entered for a property that requires a byte value is in fact a byte.</span></span>