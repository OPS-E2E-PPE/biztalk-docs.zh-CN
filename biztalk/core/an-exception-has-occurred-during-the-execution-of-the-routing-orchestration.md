---
title: 路由业务流程执行期间发生了异常 |Microsoft Docs
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
ms.openlocfilehash: c20f6f35c6ea8bcbe4f7f3dd02fd3ff4831f4217
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359955"
---
# <a name="an-exception-has-occurred-during-the-execution-of-the-routing-orchestration"></a><span data-ttu-id="1465d-102">路由业务流程执行期间出现异常</span><span class="sxs-lookup"><span data-stu-id="1465d-102">An exception has occurred during the execution of the routing orchestration</span></span>
## <a name="details"></a><span data-ttu-id="1465d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1465d-103">Details</span></span>  
  
|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1465d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1465d-104">Product Name</span></span>   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="1465d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1465d-105">Product Version</span></span> |                   [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                   |
|    <span data-ttu-id="1465d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1465d-106">Event ID</span></span>     |                                               -                                                |
|  <span data-ttu-id="1465d-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1465d-107">Event Source</span></span>   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1465d-108">EDI</span><span class="sxs-lookup"><span data-stu-id="1465d-108">EDI</span></span>     |
|    <span data-ttu-id="1465d-109">组件</span><span class="sxs-lookup"><span data-stu-id="1465d-109">Component</span></span>    |                                        <span data-ttu-id="1465d-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="1465d-110">Batching Engine</span></span>                                         |
|  <span data-ttu-id="1465d-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1465d-111">Symbolic Name</span></span>  |                                 <span data-ttu-id="1465d-112">ExceptionOccuredDuringRouting</span><span class="sxs-lookup"><span data-stu-id="1465d-112">ExceptionOccuredDuringRouting</span></span>                                  |
|  <span data-ttu-id="1465d-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1465d-113">Message Text</span></span>   | <span data-ttu-id="1465d-114">路由业务流程执行期间出现异常。</span><span class="sxs-lookup"><span data-stu-id="1465d-114">An exception has occured during the execution of the routing Orchestration.</span></span> <span data-ttu-id="1465d-115">错误消息 = {0}</span><span class="sxs-lookup"><span data-stu-id="1465d-115">ErrorMessage = {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="1465d-116">解释</span><span class="sxs-lookup"><span data-stu-id="1465d-116">Explanation</span></span>  
 <span data-ttu-id="1465d-117">此错误/警告/信息事件表明，路由业务流程无法正确处理，每个 XML 批元素副本因为 ErrorMessage 字段中指出的错误条件。</span><span class="sxs-lookup"><span data-stu-id="1465d-117">This Error/Warning/Information event indicates that the routing orchestration could not process each copy of the XML batch element correctly because of the error condition indicated in ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1465d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="1465d-118">User Action</span></span>  
 <span data-ttu-id="1465d-119">若要解决此错误，确定 ErrorMessage 字段中为的错误条件，解决错误，并重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="1465d-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and resubmit the message.</span></span>