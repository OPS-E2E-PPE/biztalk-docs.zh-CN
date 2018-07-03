---
title: 数据元素中的无效字符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db7e2c72-f2cc-4157-aa26-062d2cc1210b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2461a5542daaf701c90a76d26c31b72095d5aef
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010022"
---
# <a name="invalid-character-in-data-element"></a><span data-ttu-id="be7c5-102">数据元素中的无效字符</span><span class="sxs-lookup"><span data-stu-id="be7c5-102">Invalid character in data element</span></span>
## <a name="details"></a><span data-ttu-id="be7c5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="be7c5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="be7c5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="be7c5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="be7c5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="be7c5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="be7c5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="be7c5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="be7c5-107">事件源</span><span class="sxs-lookup"><span data-stu-id="be7c5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="be7c5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="be7c5-108"> EDI</span></span> |
|    <span data-ttu-id="be7c5-109">组件</span><span class="sxs-lookup"><span data-stu-id="be7c5-109">Component</span></span>    |                                       <span data-ttu-id="be7c5-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="be7c5-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="be7c5-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="be7c5-111">Symbolic Name</span></span>  |                     <span data-ttu-id="be7c5-112">X12DeInvalidCharacterInDataElementDescription</span><span class="sxs-lookup"><span data-stu-id="be7c5-112">X12DeInvalidCharacterInDataElementDescription</span></span>                      |
|  <span data-ttu-id="be7c5-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="be7c5-113">Message Text</span></span>   |                           <span data-ttu-id="be7c5-114">数据元素中的无效字符</span><span class="sxs-lookup"><span data-stu-id="be7c5-114">Invalid character in data element</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="be7c5-115">解释</span><span class="sxs-lookup"><span data-stu-id="be7c5-115">Explanation</span></span>  
 <span data-ttu-id="be7c5-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为某个数据元素的值不符合 EDI 架构中指定的此值。</span><span class="sxs-lookup"><span data-stu-id="be7c5-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a data element did not conform to the value specified in the EDI schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be7c5-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="be7c5-117">User Action</span></span>  
 <span data-ttu-id="be7c5-118">若要解决此错误，请确保数据元素中的值符合 EDI 架构，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="be7c5-118">To resolve this error, make sure that the value in the data element conforms to the EDI schema, and then have the interchange resent.</span></span>