---
title: 在批处理业务流程的批提交期间出现异常 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c58b2fa9-d036-4e09-a0f8-77a2f983881a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6140a6684f0548f2c9acfd0682b8bb42b025df89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388287"
---
# <a name="an-exception-has-occurred-during-the-batch-submission-in-the-batching-orchestration"></a><span data-ttu-id="4b778-102">在批处理业务流程的批提交期间出现异常</span><span class="sxs-lookup"><span data-stu-id="4b778-102">An exception has occurred during the batch submission in the batching orchestration</span></span>
## <a name="details"></a><span data-ttu-id="4b778-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="4b778-103">Details</span></span>  
  
|                 |                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4b778-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="4b778-104">Product Name</span></span>   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                  |
| <span data-ttu-id="4b778-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="4b778-105">Product Version</span></span> |                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                              |
|    <span data-ttu-id="4b778-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="4b778-106">Event ID</span></span>     |                                                          -                                                          |
|  <span data-ttu-id="4b778-107">事件源</span><span class="sxs-lookup"><span data-stu-id="4b778-107">Event Source</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="4b778-108">EDI</span><span class="sxs-lookup"><span data-stu-id="4b778-108">EDI</span></span>                |
|    <span data-ttu-id="4b778-109">组件</span><span class="sxs-lookup"><span data-stu-id="4b778-109">Component</span></span>    |                                                   <span data-ttu-id="4b778-110">批处理引擎</span><span class="sxs-lookup"><span data-stu-id="4b778-110">Batching Engine</span></span>                                                   |
|  <span data-ttu-id="4b778-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="4b778-111">Symbolic Name</span></span>  |                                                  <span data-ttu-id="4b778-112">ExceptionOccured</span><span class="sxs-lookup"><span data-stu-id="4b778-112">ExceptionOccured</span></span>                                                   |
|  <span data-ttu-id="4b778-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="4b778-113">Message Text</span></span>   | <span data-ttu-id="4b778-114">在批处理业务流程的批提交期间出现异常。</span><span class="sxs-lookup"><span data-stu-id="4b778-114">An exception has occured during the batch submission in the batching Orchestration.</span></span> <span data-ttu-id="4b778-115">批处理 Id = {0}，ErrorMessage {1}</span><span class="sxs-lookup"><span data-stu-id="4b778-115">Batch Id= {0}, ErrorMessage {1}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4b778-116">解释</span><span class="sxs-lookup"><span data-stu-id="4b778-116">Explanation</span></span>  
 <span data-ttu-id="4b778-117">此错误/警告/信息事件表示，批处理业务流程无法添加批处理元素到批因为 ErrorMessage 字段中指出了错误条件。</span><span class="sxs-lookup"><span data-stu-id="4b778-117">This Error/Warning/Information event indicates that the batching orchestration could not add a batch element to a batch because of the error condition indicated in the ErrorMessage field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b778-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="4b778-118">User Action</span></span>  
 <span data-ttu-id="4b778-119">若要解决此错误，请确定 ErrorMessage 字段中的错误条件，解决此错误，然后重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="4b778-119">To resolve this error, determine what the error condition is from the ErrorMessage field, resolve the error, and then resubmit the message.</span></span>