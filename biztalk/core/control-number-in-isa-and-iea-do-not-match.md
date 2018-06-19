---
title: 在 ISA 和 IEA 控制编号不匹配 |Microsoft 文档
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
ms.openlocfilehash: cd2f86d767b6065a6aeaa02f887dc8b6bd056fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237901"
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a><span data-ttu-id="86277-102">ISA 和 IEA 中的控件编号不匹配</span><span class="sxs-lookup"><span data-stu-id="86277-102">Control Number in ISA and IEA do not match</span></span>
## <a name="details"></a><span data-ttu-id="86277-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="86277-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="86277-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="86277-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="86277-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="86277-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="86277-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="86277-106">Event ID</span></span>|-|  
|<span data-ttu-id="86277-107">事件源</span><span class="sxs-lookup"><span data-stu-id="86277-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="86277-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="86277-108"> EDI</span></span>|  
|<span data-ttu-id="86277-109">组件</span><span class="sxs-lookup"><span data-stu-id="86277-109">Component</span></span>|<span data-ttu-id="86277-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="86277-110">AS2 Engine</span></span>|  
|<span data-ttu-id="86277-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="86277-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="86277-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="86277-112">Message Text</span></span>|<span data-ttu-id="86277-113">ISA 和 IEA 中的控件编号不匹配</span><span class="sxs-lookup"><span data-stu-id="86277-113">Control Number in ISA and IEA do not match</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="86277-114">解释</span><span class="sxs-lookup"><span data-stu-id="86277-114">Explanation</span></span>  
 <span data-ttu-id="86277-115">此错误/警告/信息事件表明 AS2 接收管道无法处理传入的交换，因为交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="86277-115">This Error/Warning/Information event indicates that the AS2 receive pipeline could not process the incoming interchange because the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="86277-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="86277-116">User Action</span></span>  
 <span data-ttu-id="86277-117">若要解决此错误，请确保交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有相同的值，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="86277-117">To resolve this error, make sure that the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange have the same value, and then have the interchange resent.</span></span>