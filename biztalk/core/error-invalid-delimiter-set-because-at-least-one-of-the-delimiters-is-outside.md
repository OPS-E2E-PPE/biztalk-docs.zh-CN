---
title: 分隔符无效设置，因为至少一个分隔符超出允许的范围是 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70722adc1a099d340b862d38574b44391954aa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241453"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a><span data-ttu-id="7c70e-102">分隔符设置无效，因为至少有一个分隔符在允许的范围之外</span><span class="sxs-lookup"><span data-stu-id="7c70e-102">Invalid delimiter set because at least one of the delimiters is outside the allowed range</span></span>
## <a name="details"></a><span data-ttu-id="7c70e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7c70e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7c70e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7c70e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7c70e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7c70e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="7c70e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7c70e-106">Event ID</span></span>|-|  
|<span data-ttu-id="7c70e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7c70e-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7c70e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7c70e-108"> EDI</span></span>|  
|<span data-ttu-id="7c70e-109">组件</span><span class="sxs-lookup"><span data-stu-id="7c70e-109">Component</span></span>|<span data-ttu-id="7c70e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7c70e-110">EDI Engine</span></span>|  
|<span data-ttu-id="7c70e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7c70e-111">Symbolic Name</span></span>|<span data-ttu-id="7c70e-112">DelimiterOutOfRange</span><span class="sxs-lookup"><span data-stu-id="7c70e-112">DelimiterOutOfRange</span></span>|  
|<span data-ttu-id="7c70e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7c70e-113">Message Text</span></span>|<span data-ttu-id="7c70e-114">无效的分隔符设置 {0}，至少有一个分隔符超出了允许的 0 到 127 范围</span><span class="sxs-lookup"><span data-stu-id="7c70e-114">Invalid delimiter set {0}, atleast one of the delimiters is outside the allowed range of 0 through 127</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7c70e-115">解释</span><span class="sxs-lookup"><span data-stu-id="7c70e-115">Explanation</span></span>  
 <span data-ttu-id="7c70e-116">此错误/警告/信息事件指示接收管道无法交换中的一个或多个分隔符是 ASCII 字符集中的值的范围设置处理传入的交换。</span><span class="sxs-lookup"><span data-stu-id="7c70e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because one or more separators in the interchange was outside the range of values in the ASCII character set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7c70e-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7c70e-117">User Action</span></span>  
 <span data-ttu-id="7c70e-118">若要解决此错误，请确保交换中的每个分隔符都在 ASCII 字符集中，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="7c70e-118">To resolve this error, make sure that each separator in the interchange is in the ASCII character set, and then have the interchange resent.</span></span>