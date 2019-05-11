---
title: 不能为此 XSD 类型完成 BitwiseAnd 比较 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bc2351-c002-458a-9d35-5fdcc91c6a0e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 069cb188ce6f6035b64298aaa90d6362d9500702
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362583"
---
# <a name="a-bitwiseand-comparison-cannot-be-done-for-this-xsd-type"></a><span data-ttu-id="91561-102">不能为此 XSD 类型完成 BitwiseAnd 比较</span><span class="sxs-lookup"><span data-stu-id="91561-102">A BitwiseAnd comparison cannot be done for this XSD type</span></span>
## <a name="details"></a><span data-ttu-id="91561-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="91561-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="91561-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="91561-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="91561-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="91561-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="91561-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="91561-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="91561-107">事件源</span><span class="sxs-lookup"><span data-stu-id="91561-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="91561-108">EDI</span><span class="sxs-lookup"><span data-stu-id="91561-108">EDI</span></span> |
|    <span data-ttu-id="91561-109">组件</span><span class="sxs-lookup"><span data-stu-id="91561-109">Component</span></span>    |                                       <span data-ttu-id="91561-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="91561-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="91561-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="91561-111">Symbolic Name</span></span>  |                             <span data-ttu-id="91561-112">Err_InvalidBitwiseComparision</span><span class="sxs-lookup"><span data-stu-id="91561-112">Err_InvalidBitwiseComparision</span></span>                              |
|  <span data-ttu-id="91561-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="91561-113">Message Text</span></span>   |               <span data-ttu-id="91561-114">对于此 XSD 类型，无法进行 BitwiseAnd 比较。</span><span class="sxs-lookup"><span data-stu-id="91561-114">A BitwiseAnd comparison cannot be done for this XSD type.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="91561-115">解释</span><span class="sxs-lookup"><span data-stu-id="91561-115">Explanation</span></span>  
 <span data-ttu-id="91561-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="91561-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="91561-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="91561-117">User Action</span></span>  
 <span data-ttu-id="91561-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 CSD 类型无法进行按位比较的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="91561-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an CSD type that can’t be bitwise compared.</span></span>