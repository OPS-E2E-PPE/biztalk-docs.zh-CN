---
title: Integer 属性值不是有效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31d4e9a7-4336-40f1-997a-9f79d86b26d2
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c99c9830087c7a0659466cfaad589aea3cf41b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258644"
---
# <a name="the-integer-property-value-is-not-valid"></a><span data-ttu-id="3e986-102">Integer 属性值无效</span><span class="sxs-lookup"><span data-stu-id="3e986-102">The integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="3e986-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3e986-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="3e986-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3e986-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="3e986-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3e986-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="3e986-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3e986-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="3e986-107">事件源</span><span class="sxs-lookup"><span data-stu-id="3e986-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3e986-108">EDI</span><span class="sxs-lookup"><span data-stu-id="3e986-108">EDI</span></span> |
|    <span data-ttu-id="3e986-109">组件</span><span class="sxs-lookup"><span data-stu-id="3e986-109">Component</span></span>    |                                       <span data-ttu-id="3e986-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="3e986-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="3e986-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="3e986-111">Symbolic Name</span></span>  |                                   <span data-ttu-id="3e986-112">Err_InvalidInteger</span><span class="sxs-lookup"><span data-stu-id="3e986-112">Err_InvalidInteger</span></span>                                   |
|  <span data-ttu-id="3e986-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="3e986-113">Message Text</span></span>   |                        <span data-ttu-id="3e986-114">integer 属性值无效。</span><span class="sxs-lookup"><span data-stu-id="3e986-114">The integer property value is not valid.</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="3e986-115">解释</span><span class="sxs-lookup"><span data-stu-id="3e986-115">Explanation</span></span>  
 <span data-ttu-id="3e986-116">此错误/警告/信息事件表明 BizTalk Server 在尝试决定是否批处理消息时无法比较上下文属性。</span><span class="sxs-lookup"><span data-stu-id="3e986-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3e986-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="3e986-117">User Action</span></span>  
 <span data-ttu-id="3e986-118">若要解决此错误，请确保在活动的批处理中提供的筛选器没有指定 XSD 类型为 integer 且值无效的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="3e986-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of integer with an invalid value.</span></span>