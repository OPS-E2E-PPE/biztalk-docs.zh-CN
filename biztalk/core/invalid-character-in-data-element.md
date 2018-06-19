---
title: 数据元素中的包含无效字符 |Microsoft 文档
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
ms.openlocfilehash: cc805fbede667013b56088b3d2c29913157c2fe5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257109"
---
# <a name="invalid-character-in-data-element"></a><span data-ttu-id="85c60-102">数据元素中包含无效字符</span><span class="sxs-lookup"><span data-stu-id="85c60-102">Invalid character in data element</span></span>
## <a name="details"></a><span data-ttu-id="85c60-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="85c60-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85c60-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="85c60-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="85c60-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="85c60-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="85c60-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="85c60-106">Event ID</span></span>|-|  
|<span data-ttu-id="85c60-107">事件源</span><span class="sxs-lookup"><span data-stu-id="85c60-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="85c60-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="85c60-108"> EDI</span></span>|  
|<span data-ttu-id="85c60-109">组件</span><span class="sxs-lookup"><span data-stu-id="85c60-109">Component</span></span>|<span data-ttu-id="85c60-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="85c60-110">EDI Engine</span></span>|  
|<span data-ttu-id="85c60-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="85c60-111">Symbolic Name</span></span>|<span data-ttu-id="85c60-112">X12DeInvalidCharacterInDataElementDescription</span><span class="sxs-lookup"><span data-stu-id="85c60-112">X12DeInvalidCharacterInDataElementDescription</span></span>|  
|<span data-ttu-id="85c60-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="85c60-113">Message Text</span></span>|<span data-ttu-id="85c60-114">数据元素中包含无效字符</span><span class="sxs-lookup"><span data-stu-id="85c60-114">Invalid character in data element</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="85c60-115">解释</span><span class="sxs-lookup"><span data-stu-id="85c60-115">Explanation</span></span>  
 <span data-ttu-id="85c60-116">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为某个数据元素的值不符合 EDI 架构中指定的此值。</span><span class="sxs-lookup"><span data-stu-id="85c60-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of a data element did not conform to the value specified in the EDI schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="85c60-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="85c60-117">User Action</span></span>  
 <span data-ttu-id="85c60-118">若要解决此错误，请确保数据元素中的值符合 EDI 架构，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="85c60-118">To resolve this error, make sure that the value in the data element conforms to the EDI schema, and then have the interchange resent.</span></span>