---
title: 段应具有至少两个字符的名称具有 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f80bbc4a-151a-4094-8640-1944e8812730
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: def67be8b1c146bd6da37b669a71f2be15e22e2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985958"
---
# <a name="segment-should-have-a-name-with-at-least-two-characters"></a><span data-ttu-id="61f37-102">段的名称应具有至少两个字符</span><span class="sxs-lookup"><span data-stu-id="61f37-102">Segment should have a name with at least two characters</span></span>
## <a name="details"></a><span data-ttu-id="61f37-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="61f37-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="61f37-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="61f37-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="61f37-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="61f37-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="61f37-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="61f37-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="61f37-107">事件源</span><span class="sxs-lookup"><span data-stu-id="61f37-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="61f37-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="61f37-108"> EDI</span></span> |
|    <span data-ttu-id="61f37-109">组件</span><span class="sxs-lookup"><span data-stu-id="61f37-109">Component</span></span>    |                                       <span data-ttu-id="61f37-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="61f37-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="61f37-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="61f37-111">Symbolic Name</span></span>  |                             <span data-ttu-id="61f37-112">SchemaCode103EInvalidTagLength</span><span class="sxs-lookup"><span data-stu-id="61f37-112">SchemaCode103EInvalidTagLength</span></span>                             |
|  <span data-ttu-id="61f37-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="61f37-113">Message Text</span></span>   |                 <span data-ttu-id="61f37-114">段的名称应该至少 2 个字符</span><span class="sxs-lookup"><span data-stu-id="61f37-114">Segment should have a name with at least 2 characters</span></span>                  |
  
## <a name="explanation"></a><span data-ttu-id="61f37-115">解释</span><span class="sxs-lookup"><span data-stu-id="61f37-115">Explanation</span></span>  
 <span data-ttu-id="61f37-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为交换中某个段的名称没有至少两个字符。</span><span class="sxs-lookup"><span data-stu-id="61f37-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the name of a segment in the interchange does not have at least two characters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="61f37-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="61f37-117">User Action</span></span>  
 <span data-ttu-id="61f37-118">若要解决此错误，请让交换的发送方确保交换中每个段的名称至少具有两个字符。</span><span class="sxs-lookup"><span data-stu-id="61f37-118">To resolve this error, have the sender of the interchange ensure that the name of each segment in the interchange has at least two characters, and then resend the interchange.</span></span>