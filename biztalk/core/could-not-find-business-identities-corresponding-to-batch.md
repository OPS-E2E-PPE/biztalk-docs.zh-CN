---
title: 找不到与批相对应的业务标识 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9baf11-e9c6-482d-a47d-aa99852939bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d9d49d4fe30f8e3dd85f32c17e834f45550024d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354356"
---
# <a name="could-not-find-business-identities-corresponding-to-batch"></a><span data-ttu-id="16234-102">找不到与批相对应的业务标识</span><span class="sxs-lookup"><span data-stu-id="16234-102">Could not find Business Identities corresponding to batch</span></span>
## <a name="details"></a><span data-ttu-id="16234-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="16234-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="16234-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="16234-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="16234-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="16234-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="16234-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="16234-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="16234-107">事件源</span><span class="sxs-lookup"><span data-stu-id="16234-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="16234-108">EDI</span><span class="sxs-lookup"><span data-stu-id="16234-108">EDI</span></span> |
|    <span data-ttu-id="16234-109">组件</span><span class="sxs-lookup"><span data-stu-id="16234-109">Component</span></span>    |                                       <span data-ttu-id="16234-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="16234-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="16234-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="16234-111">Symbolic Name</span></span>  |                               <span data-ttu-id="16234-112">IdentitiesNotFoundForBatch</span><span class="sxs-lookup"><span data-stu-id="16234-112">IdentitiesNotFoundForBatch</span></span>                               |
|  <span data-ttu-id="16234-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="16234-113">Message Text</span></span>   |             <span data-ttu-id="16234-114">找不到与批相对应的业务标识{0}。</span><span class="sxs-lookup"><span data-stu-id="16234-114">Could not find Business Identities corresponding to batch {0}.</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="16234-115">解释</span><span class="sxs-lookup"><span data-stu-id="16234-115">Explanation</span></span>  
 <span data-ttu-id="16234-116">此错误/警告/信息事件表明 BizTalk Server 无法处理批处理消息，因为没有足够的数据。</span><span class="sxs-lookup"><span data-stu-id="16234-116">This Error/Warning/Information event indicates BizTalk Server was not able to process a batch message because of insufficient data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16234-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="16234-117">User Action</span></span>  
 <span data-ttu-id="16234-118">若要解决此错误，请确保具有给定 Id 的批处理所包含协议的协议属性中存在，并且为协议指定了正确的业务标识。</span><span class="sxs-lookup"><span data-stu-id="16234-118">To resolve this error, ensure that a batch with the given Id is present in the Agreement properties of the containing Agreement and proper business identities are specified for the agreement.</span></span>