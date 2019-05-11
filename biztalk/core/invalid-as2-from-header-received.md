---
title: 无效的 AS2-From 标头接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d773e09-8526-4533-9066-8e743e65a688
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 935995719473c8ff7977b47ec8b6971229b1a795
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381425"
---
# <a name="invalid-as2-from-header-received"></a><span data-ttu-id="9fc83-102">无效的 AS2-From 标头接收</span><span class="sxs-lookup"><span data-stu-id="9fc83-102">Invalid AS2-From header received</span></span>
## <a name="details"></a><span data-ttu-id="9fc83-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9fc83-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9fc83-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9fc83-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9fc83-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9fc83-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9fc83-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9fc83-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9fc83-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9fc83-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9fc83-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9fc83-108">EDI</span></span> |
|    <span data-ttu-id="9fc83-109">组件</span><span class="sxs-lookup"><span data-stu-id="9fc83-109">Component</span></span>    |                                       <span data-ttu-id="9fc83-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="9fc83-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="9fc83-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9fc83-111">Symbolic Name</span></span>  |                         <span data-ttu-id="9fc83-112">InvalidAS2FromNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="9fc83-112">InvalidAS2FromNameHeaderReceivedError</span></span>                          |
|  <span data-ttu-id="9fc83-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="9fc83-113">Message Text</span></span>   |                     <span data-ttu-id="9fc83-114">无效的 AS2-From 标头接收。</span><span class="sxs-lookup"><span data-stu-id="9fc83-114">Invalid AS2-From header received.</span></span>  <span data-ttu-id="9fc83-115">值： {0}</span><span class="sxs-lookup"><span data-stu-id="9fc83-115">Value: {0}</span></span>                      |
  
## <a name="explanation"></a><span data-ttu-id="9fc83-116">解释</span><span class="sxs-lookup"><span data-stu-id="9fc83-116">Explanation</span></span>  
 <span data-ttu-id="9fc83-117">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为 as2-From 标头消息中不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="9fc83-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-From header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9fc83-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="9fc83-118">User Action</span></span>  
 <span data-ttu-id="9fc83-119">若要解决此错误，请确保在 AS2 中的值的消息标头符合 AS2 RFC 4130 6.2 节中的规范，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="9fc83-119">To resolve this error, make sure that the value in the AS2-From header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>