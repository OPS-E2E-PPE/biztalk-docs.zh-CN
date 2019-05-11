---
title: 由于结构无效，无 transactionSet 或 UNE，Edifact 交换 Xml 序列化失败 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ce1c219-f2ed-46c1-ae4b-8a4206f7cd01
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f55bb6d0f5959a53781e7f48e69b89762a104377
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388919"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-transactionset-or-une"></a><span data-ttu-id="693b1-102">由于结构无效，无 transactionSet 或 UNE，Edifact 交换 Xml 序列化失败</span><span class="sxs-lookup"><span data-stu-id="693b1-102">Edifact interchange Xml serialization failed due to invalid structure, no transactionSet or UNE</span></span>
## <a name="details"></a><span data-ttu-id="693b1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="693b1-103">Details</span></span>  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="693b1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="693b1-104">Product Name</span></span>   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="693b1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="693b1-105">Product Version</span></span> |                               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    <span data-ttu-id="693b1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="693b1-106">Event ID</span></span>     |                                                            -                                                            |
|  <span data-ttu-id="693b1-107">事件源</span><span class="sxs-lookup"><span data-stu-id="693b1-107">Event Source</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="693b1-108">EDI</span><span class="sxs-lookup"><span data-stu-id="693b1-108">EDI</span></span>                  |
|    <span data-ttu-id="693b1-109">组件</span><span class="sxs-lookup"><span data-stu-id="693b1-109">Component</span></span>    |                                                       <span data-ttu-id="693b1-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="693b1-110">EDI Engine</span></span>                                                        |
|  <span data-ttu-id="693b1-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="693b1-111">Symbolic Name</span></span>  |                                            <span data-ttu-id="693b1-112">EfactTransactionSetOrUneNotFound</span><span class="sxs-lookup"><span data-stu-id="693b1-112">EfactTransactionSetOrUneNotFound</span></span>                                             |
|  <span data-ttu-id="693b1-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="693b1-113">Message Text</span></span>   | <span data-ttu-id="693b1-114">由于结构无效，Edifact 交换 Xml 序列化失败。</span><span class="sxs-lookup"><span data-stu-id="693b1-114">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="693b1-115">查找 TransactionSet 或 UNE，但没有找到</span><span class="sxs-lookup"><span data-stu-id="693b1-115">Looking for TransactionSet or UNE, but not found</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="693b1-116">解释</span><span class="sxs-lookup"><span data-stu-id="693b1-116">Explanation</span></span>  
 <span data-ttu-id="693b1-117">此错误/警告/信息事件表明 EDI 接收管道无法处理传入的 EDIFACT 交换，因为第一个段既不是 UNA 段也不是 UNB 段。</span><span class="sxs-lookup"><span data-stu-id="693b1-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process the incoming EDIFACT interchange because the first segment was neither a UNA or a UNB segment.</span></span> <span data-ttu-id="693b1-118">UNA 段是可选的；UNB 段是必需的。</span><span class="sxs-lookup"><span data-stu-id="693b1-118">The UNA segment is optional; the UNB segment is mandatory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="693b1-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="693b1-119">User Action</span></span>  
 <span data-ttu-id="693b1-120">若要解决此错误，请确保交换的发送方结构化消息，以便组中的事务集后面跟随另一个事务集或 UNE 段。</span><span class="sxs-lookup"><span data-stu-id="693b1-120">To resolve this error, ensure that the sender of the interchange structures the message such that a transaction set in a group is either followed by another transaction set or a UNE segment.</span></span> <span data-ttu-id="693b1-121">然后，让发送方重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="693b1-121">Have the sender then resend the interchange.</span></span>