---
title: 在升级批处理业务流程的执行期间出现了异常 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2221a498-98aa-43ab-bc4e-34dcbd92dcf0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0789853ba253d7d8e51c34a6c1d1ce64829f8d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006662"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-upgrade-batch-orchestration"></a><span data-ttu-id="c0a86-102">在升级批业务流程的执行期间出现异常</span><span class="sxs-lookup"><span data-stu-id="c0a86-102">An exception has occurred during the execution of the upgrade batch orchestration</span></span>
## <a name="details"></a><span data-ttu-id="c0a86-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c0a86-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c0a86-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c0a86-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c0a86-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c0a86-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c0a86-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c0a86-106">Event ID</span></span>|-|  
|<span data-ttu-id="c0a86-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c0a86-107">Event Source</span></span>|<span data-ttu-id="c0a86-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="c0a86-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="c0a86-109">组件</span><span class="sxs-lookup"><span data-stu-id="c0a86-109">Component</span></span>|<span data-ttu-id="c0a86-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="c0a86-110">Batching Engine</span></span>|  
|<span data-ttu-id="c0a86-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c0a86-111">Symbolic Name</span></span>|<span data-ttu-id="c0a86-112">ExceptionOccuredDuringUpgrade</span><span class="sxs-lookup"><span data-stu-id="c0a86-112">ExceptionOccuredDuringUpgrade</span></span>|  
|<span data-ttu-id="c0a86-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c0a86-113">Message Text</span></span>|<span data-ttu-id="c0a86-114">在执行升级批处理业务流程期间发生了异常。</span><span class="sxs-lookup"><span data-stu-id="c0a86-114">An exception has occurred during the execution of the upgrade batch Orchestration.</span></span> <span data-ttu-id="c0a86-115">ErrorMessage = {0}</span><span class="sxs-lookup"><span data-stu-id="c0a86-115">ErrorMessage = {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c0a86-116">解释</span><span class="sxs-lookup"><span data-stu-id="c0a86-116">Explanation</span></span>  
 <span data-ttu-id="c0a86-117">此错误/警告/信息事件表明升级批处理业务流程无法正确处理消息，因为在 ErrorMessage 字段中指明了错误条件。</span><span class="sxs-lookup"><span data-stu-id="c0a86-117">The Error/Warning/Information event indicates that the upgrade batch orchestration could not process the message correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c0a86-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="c0a86-118">User Action</span></span>  
 <span data-ttu-id="c0a86-119">若要解决此错误，请确定 ErrorMessage 字段中的错误条件，解决此错误，然后重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="c0a86-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>