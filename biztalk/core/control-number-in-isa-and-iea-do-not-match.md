---
title: ISA 和 IEA 中的控制编号不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f9091ea-460b-464b-acd5-8dc0488b61e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1fa574e63444740e85cbdd9bf8ac411c495b24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016225"
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a><span data-ttu-id="a6202-102">ISA 和 IEA 中的控件编号不匹配</span><span class="sxs-lookup"><span data-stu-id="a6202-102">Control Number in ISA and IEA do not match</span></span>
## <a name="details"></a><span data-ttu-id="a6202-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a6202-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a6202-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a6202-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a6202-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a6202-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a6202-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a6202-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a6202-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a6202-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a6202-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a6202-108"> EDI</span></span> |
|    <span data-ttu-id="a6202-109">组件</span><span class="sxs-lookup"><span data-stu-id="a6202-109">Component</span></span>    |                                       <span data-ttu-id="a6202-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="a6202-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="a6202-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a6202-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="a6202-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="a6202-112">Message Text</span></span>   |                       <span data-ttu-id="a6202-113">ISA 和 IEA 中的控件编号不匹配</span><span class="sxs-lookup"><span data-stu-id="a6202-113">Control Number in ISA and IEA do not match</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="a6202-114">解释</span><span class="sxs-lookup"><span data-stu-id="a6202-114">Explanation</span></span>  
 <span data-ttu-id="a6202-115">此错误/警告/信息事件表明 AS2 接收管道无法处理传入的交换，因为交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="a6202-115">This Error/Warning/Information event indicates that the AS2 receive pipeline could not process the incoming interchange because the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a6202-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="a6202-116">User Action</span></span>  
 <span data-ttu-id="a6202-117">若要解决此错误，请确保交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有相同的值，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="a6202-117">To resolve this error, make sure that the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange have the same value, and then have the interchange resent.</span></span>