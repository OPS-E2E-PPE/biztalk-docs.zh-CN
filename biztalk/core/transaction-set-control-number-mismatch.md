---
title: 事务集控制编号不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c4b0c3f-f3be-4c2c-8719-8e40aa7122b9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4c20eb6853827709731c41631a38225214424d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021971"
---
# <a name="transaction-set-control-number-mismatch"></a><span data-ttu-id="30254-102">事务集控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="30254-102">Transaction Set Control Number Mismatch</span></span>
## <a name="details"></a><span data-ttu-id="30254-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="30254-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="30254-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="30254-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="30254-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="30254-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="30254-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="30254-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="30254-107">事件源</span><span class="sxs-lookup"><span data-stu-id="30254-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="30254-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="30254-108"> EDI</span></span> |
|    <span data-ttu-id="30254-109">组件</span><span class="sxs-lookup"><span data-stu-id="30254-109">Component</span></span>    |                                       <span data-ttu-id="30254-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="30254-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="30254-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="30254-111">Symbolic Name</span></span>  |                         <span data-ttu-id="30254-112">X12TsControlNumberMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="30254-112">X12TsControlNumberMismatchDescription</span></span>                          |
|  <span data-ttu-id="30254-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="30254-113">Message Text</span></span>   |                        <span data-ttu-id="30254-114">事务集控制编号不匹配</span><span class="sxs-lookup"><span data-stu-id="30254-114">Transaction Set Control Number Mismatch</span></span>                         |
  
## <a name="explanation"></a><span data-ttu-id="30254-115">解释</span><span class="sxs-lookup"><span data-stu-id="30254-115">Explanation</span></span>  
 <span data-ttu-id="30254-116">此错误/警告/信息事件表明 EDI 接收管道拒绝了传入的事务集，因为事务集的 SE02 字段中包含的控制编号与 ST02 字段中的控制编号不匹配。</span><span class="sxs-lookup"><span data-stu-id="30254-116">This Error/Warning/Information event indicates that the EDI receive pipeline rejected the incoming transaction set because the control number contained in the SE02 field of the transaction set did not match the control number in the ST02 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="30254-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="30254-117">User Action</span></span>  
 <span data-ttu-id="30254-118">若要解决此错误，请让事务集的发送方更改所拒绝事务集的 SE02 字段中的控制编号，使其与 ST02 字段中的控制编号相同，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="30254-118">To resolve this error, have the sender of the transaction set change the control number in the SE02 field of the rejected transaction set to be the same as the control number in the ST02 field, and then resend the interchange.</span></span>