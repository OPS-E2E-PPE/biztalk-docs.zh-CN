---
title: 因为 UNB1.1 中的编码信息不匹配的实际编码不受支持的字符集 |Microsoft Docs
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
ms.openlocfilehash: ea2b1cd0831bb0194c9a5290c2c724bdd46c1714
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388968"
---
# <a name="character-set-not-supported-because-the-encoding-information-in-unb11-does-not-match-the-actual-encoding"></a><span data-ttu-id="809b3-102">字符集不受支持，因为 UNB1.1 中的编码信息不匹配的实际编码</span><span class="sxs-lookup"><span data-stu-id="809b3-102">Character set not supported because the encoding information in UNB1.1 does not match the actual encoding</span></span>
## <a name="details"></a><span data-ttu-id="809b3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="809b3-103">Details</span></span>  
  
|                 |                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="809b3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="809b3-104">Product Name</span></span>   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                  |
| <span data-ttu-id="809b3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="809b3-105">Product Version</span></span> |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                              |
|    <span data-ttu-id="809b3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="809b3-106">Event ID</span></span>     |                                                                          -                                                                          |
|  <span data-ttu-id="809b3-107">事件源</span><span class="sxs-lookup"><span data-stu-id="809b3-107">Event Source</span></span>   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="809b3-108">EDI</span><span class="sxs-lookup"><span data-stu-id="809b3-108">EDI</span></span>                                |
|    <span data-ttu-id="809b3-109">组件</span><span class="sxs-lookup"><span data-stu-id="809b3-109">Component</span></span>    |                                                                     <span data-ttu-id="809b3-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="809b3-110">EDI Engine</span></span>                                                                      |
|  <span data-ttu-id="809b3-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="809b3-111">Symbolic Name</span></span>  |                                                                          -                                                                          |
|  <span data-ttu-id="809b3-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="809b3-112">Message Text</span></span>   | <span data-ttu-id="809b3-113">不支持字符集。</span><span class="sxs-lookup"><span data-stu-id="809b3-113">Character set not supported.</span></span> <span data-ttu-id="809b3-114">可能是由于 UNB1.1 中的编码信息与交换中的实际编码不匹配。</span><span class="sxs-lookup"><span data-stu-id="809b3-114">It could be due to the fact that encoding information in UNB1.1 does not match the actual encoding of the interchange.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="809b3-115">解释</span><span class="sxs-lookup"><span data-stu-id="809b3-115">Explanation</span></span>  
 <span data-ttu-id="809b3-116">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为交换中使用的字符不符合交换的字段 UNB1.1 中标识的字符集。</span><span class="sxs-lookup"><span data-stu-id="809b3-116">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the characters used in the interchange did not conform to the character set identified in field UNB1.1 of the interchange.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="809b3-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="809b3-117">User Action</span></span>  
 <span data-ttu-id="809b3-118">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="809b3-118">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="809b3-119">更改交换中使用的字符，以便这些字符符合交换的字段 UNB1.1 中指定的字符集。</span><span class="sxs-lookup"><span data-stu-id="809b3-119">Change the characters used in the interchange so they conform to the character set specified in field UNB1.1 of the interchange.</span></span>  
  
-   <span data-ttu-id="809b3-120">更改交换的字段 UNB1.1 中指定的字符集，以便交换中的所有字符都是该字符集的一部分。</span><span class="sxs-lookup"><span data-stu-id="809b3-120">Change the character set specified in field UNB1.1 of the interchange, so all characters in the interchange are part of the character set.</span></span>