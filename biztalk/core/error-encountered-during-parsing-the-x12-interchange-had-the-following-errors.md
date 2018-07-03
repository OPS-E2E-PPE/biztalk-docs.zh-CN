---
title: 在解析过程中遇到错误。 X12 交换发生以下错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c1085d4-75ef-4f63-84c9-287a4a61274a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48acca94e1a32f32a296c5128e25404572f688af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968334"
---
# <a name="error-encountered-during-parsing-the-x12-interchange-had-the-following-errors"></a><span data-ttu-id="b07d2-103">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="b07d2-103">Error encountered during parsing.</span></span> <span data-ttu-id="b07d2-104">X12 交换发生了以下错误</span><span class="sxs-lookup"><span data-stu-id="b07d2-104">The X12 interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="b07d2-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="b07d2-105">Details</span></span>  
  
|                 |                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b07d2-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="b07d2-106">Product Name</span></span>   |                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| <span data-ttu-id="b07d2-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="b07d2-107">Product Version</span></span> |                                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                       |
|    <span data-ttu-id="b07d2-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b07d2-108">Event ID</span></span>     |                                                                   -                                                                    |
|  <span data-ttu-id="b07d2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b07d2-109">Event Source</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b07d2-110"> EDI</span><span class="sxs-lookup"><span data-stu-id="b07d2-110"> EDI</span></span>                         |
|    <span data-ttu-id="b07d2-111">组件</span><span class="sxs-lookup"><span data-stu-id="b07d2-111">Component</span></span>    |                                                               <span data-ttu-id="b07d2-112">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="b07d2-112">EDI Engine</span></span>                                                               |
|  <span data-ttu-id="b07d2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b07d2-113">Symbolic Name</span></span>  |                                                       <span data-ttu-id="b07d2-114">X12InterchangeReceiveError</span><span class="sxs-lookup"><span data-stu-id="b07d2-114">X12InterchangeReceiveError</span></span>                                                       |
|  <span data-ttu-id="b07d2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b07d2-115">Message Text</span></span>   | <span data-ttu-id="b07d2-116">在解析过程中遇到错误。</span><span class="sxs-lookup"><span data-stu-id="b07d2-116">Error encountered during parsing.</span></span> <span data-ttu-id="b07d2-117">X12 交换具有 id{0}，发送方 id '{1}，接收方 id{2}发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="b07d2-117">The X12 interchange with id '{0}', with sender id '{1}', receiver id '{2}' had the following errors:</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b07d2-118">解释</span><span class="sxs-lookup"><span data-stu-id="b07d2-118">Explanation</span></span>  
 <span data-ttu-id="b07d2-119">此错误/警告/信息事件表明由于在交换中指出的错误，在分析传入的 X12 交换时 EDI 接收管道遇到错误。</span><span class="sxs-lookup"><span data-stu-id="b07d2-119">This Error/Warning/Information event indicates that the EDI receive pipeline encountered an error when parsing an incoming X12 interchange because of the stated errors in the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b07d2-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="b07d2-120">User Action</span></span>  
 <span data-ttu-id="b07d2-121">若要解决此错误，请使用错误消息中的信息来标识交换中的错误，然后在产品帮助中确定问题解决方案。</span><span class="sxs-lookup"><span data-stu-id="b07d2-121">To resolve this error, use the information in the error message to identify the error in the interchange and then determine the problem resolution in the product help.</span></span>