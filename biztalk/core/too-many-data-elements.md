---
title: 数据元素太多 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5000577d-5748-4e81-a394-86b2a780d70f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2e4668c4afacfdb9ac646d7d889320f45bcff14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992910"
---
# <a name="too-many-data-elements"></a><span data-ttu-id="9a358-102">数据元素太多</span><span class="sxs-lookup"><span data-stu-id="9a358-102">Too many data elements</span></span>
## <a name="details"></a><span data-ttu-id="9a358-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9a358-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9a358-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9a358-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9a358-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9a358-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9a358-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9a358-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9a358-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9a358-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9a358-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="9a358-108"> EDI</span></span> |
|    <span data-ttu-id="9a358-109">组件</span><span class="sxs-lookup"><span data-stu-id="9a358-109">Component</span></span>    |                                       <span data-ttu-id="9a358-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9a358-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="9a358-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9a358-111">Symbolic Name</span></span>  |                          <span data-ttu-id="9a358-112">X12DeTooManyDataElementsDescription</span><span class="sxs-lookup"><span data-stu-id="9a358-112">X12DeTooManyDataElementsDescription</span></span>                           |
|  <span data-ttu-id="9a358-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9a358-113">Message Text</span></span>   |                                 <span data-ttu-id="9a358-114">数据元素太多</span><span class="sxs-lookup"><span data-stu-id="9a358-114">Too many data elements</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="9a358-115">解释</span><span class="sxs-lookup"><span data-stu-id="9a358-115">Explanation</span></span>  
 <span data-ttu-id="9a358-116">此错误/警告/信息事件表明接收管道无法处理传入的交换或发送管道无法处理传入的交换，因为交换中的某个段包含的数据元素多于文档架构或服务架构所允许的数据元素。</span><span class="sxs-lookup"><span data-stu-id="9a358-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because a segment in the interchange contained more data elements than allowed by the document schema or the service schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a358-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="9a358-117">User Action</span></span>  
 <span data-ttu-id="9a358-118">若要解决此错误，请让交换的发送方确保该段包含所需数量的数据元素，如有必要从该段中删除多余的数据元素，直到该段符合架构。</span><span class="sxs-lookup"><span data-stu-id="9a358-118">To resolve this error, have the sender of the interchange ensure that segments include the required number of data elements, removing excess data elements from the segment if necessary, until the segment conforms to the schema.</span></span>