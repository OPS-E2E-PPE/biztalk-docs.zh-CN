---
title: 在路由的业务流程的执行期间出现了异常 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68ec8921-ba05-496e-8dcc-fd8994fcb8b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e865ec091330a863cb2bab90bbafd9b891edb05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229965"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a><span data-ttu-id="a5ddd-102">在路由业务流程的执行期间出现异常</span><span class="sxs-lookup"><span data-stu-id="a5ddd-102">An exception has occurred during the execution of the routing orchestration</span></span>
## <a name="details"></a><span data-ttu-id="a5ddd-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a5ddd-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5ddd-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a5ddd-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a5ddd-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a5ddd-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="a5ddd-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a5ddd-106">Event ID</span></span>|-|  
|<span data-ttu-id="a5ddd-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a5ddd-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a5ddd-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="a5ddd-108"> EDI</span></span>|  
|<span data-ttu-id="a5ddd-109">组件</span><span class="sxs-lookup"><span data-stu-id="a5ddd-109">Component</span></span>|<span data-ttu-id="a5ddd-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="a5ddd-110">Batching Engine</span></span>|  
|<span data-ttu-id="a5ddd-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a5ddd-111">Symbolic Name</span></span>|<span data-ttu-id="a5ddd-112">ExceptionOccuredDuringRouting</span><span class="sxs-lookup"><span data-stu-id="a5ddd-112">ExceptionOccuredDuringRouting</span></span>|  
|<span data-ttu-id="a5ddd-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="a5ddd-113">Message Text</span></span>|<span data-ttu-id="a5ddd-114">在执行路由业务流程期间发生异常。</span><span class="sxs-lookup"><span data-stu-id="a5ddd-114">An exception has occured during the execution of the routing Orchestration.</span></span> <span data-ttu-id="a5ddd-115">ErrorMessage = {0}</span><span class="sxs-lookup"><span data-stu-id="a5ddd-115">ErrorMessage = {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a5ddd-116">解释</span><span class="sxs-lookup"><span data-stu-id="a5ddd-116">Explanation</span></span>  
 <span data-ttu-id="a5ddd-117">此错误/警告/信息事件表明路由业务流程无法正确处理每个 XML 批处理元素的副本，因为 ErrorMessage 字段中指出了错误条件。</span><span class="sxs-lookup"><span data-stu-id="a5ddd-117">This Error/Warning/Information event indicates that the routing orchestration could not process each copy of the XML batch element correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a5ddd-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="a5ddd-118">User Action</span></span>  
 <span data-ttu-id="a5ddd-119">若要解决此错误，确定哪种错误条件从 ErrorMessage 字段，解决错误，然后重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="a5ddd-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and resubmit the message.</span></span>