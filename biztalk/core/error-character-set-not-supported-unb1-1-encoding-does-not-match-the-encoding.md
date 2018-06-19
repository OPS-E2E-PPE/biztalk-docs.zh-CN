---
title: 不支持因为 UNB1.1 中的编码信息不匹配的实际编码的字符集 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 085ea8e3-e0d8-45bd-9985-6787b00e4d5a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41a6eafbb0e71de5f13e792361cdc0d1fc338088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239901"
---
# <a name="character-set-not-supported-because-the-encoding-information-in-unb11-does-not-match-the-actual-encoding"></a><span data-ttu-id="2d976-102">字符集不受支持，因为 UNB1.1 中的编码信息与实际编码不匹配</span><span class="sxs-lookup"><span data-stu-id="2d976-102">Character set not supported because the encoding information in UNB1.1 does not match the actual encoding</span></span>
## <a name="details"></a><span data-ttu-id="2d976-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="2d976-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2d976-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="2d976-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="2d976-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="2d976-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="2d976-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2d976-106">Event ID</span></span>|-|  
|<span data-ttu-id="2d976-107">事件源</span><span class="sxs-lookup"><span data-stu-id="2d976-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2d976-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="2d976-108"> EDI</span></span>|  
|<span data-ttu-id="2d976-109">组件</span><span class="sxs-lookup"><span data-stu-id="2d976-109">Component</span></span>|<span data-ttu-id="2d976-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="2d976-110">EDI Engine</span></span>|  
|<span data-ttu-id="2d976-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="2d976-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="2d976-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="2d976-112">Message Text</span></span>|<span data-ttu-id="2d976-113">不支持字符集。</span><span class="sxs-lookup"><span data-stu-id="2d976-113">Character set not supported.</span></span> <span data-ttu-id="2d976-114">可能是由于 UNB1.1 中的编码信息与交换中的实际编码不匹配。</span><span class="sxs-lookup"><span data-stu-id="2d976-114">It could be due to the fact that encoding information in UNB1.1 does not match the actual encoding of the interchange.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2d976-115">解释</span><span class="sxs-lookup"><span data-stu-id="2d976-115">Explanation</span></span>  
 <span data-ttu-id="2d976-116">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为交换中使用的字符不符合交换的字段 UNB1.1 中标识的字符集。</span><span class="sxs-lookup"><span data-stu-id="2d976-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the characters used in the interchange did not conform to the character set identified in field UNB1.1 of the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2d976-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="2d976-117">User Action</span></span>  
 <span data-ttu-id="2d976-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="2d976-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="2d976-119">更改交换中使用的字符，以便这些字符符合交换的字段 UNB1.1 中指定的字符集。</span><span class="sxs-lookup"><span data-stu-id="2d976-119">Change the characters used in the interchange so they conform to the character set specified in field UNB1.1 of the interchange.</span></span>  
  
-   <span data-ttu-id="2d976-120">更改交换的字段 UNB1.1 中指定的字符集，以便交换中的所有字符都是该字符集的一部分。</span><span class="sxs-lookup"><span data-stu-id="2d976-120">Change the character set specified in field UNB1.1 of the interchange, so all characters in the interchange are part of the character set.</span></span>