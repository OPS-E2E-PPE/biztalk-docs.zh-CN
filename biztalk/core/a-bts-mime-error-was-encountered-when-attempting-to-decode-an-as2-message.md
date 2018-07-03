---
title: 尝试进行解码的 AS2 消息时遇到 BTS MIME 错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629e09e950a6c49263230f23725002eee9be905b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985918"
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="e0a80-102">尝试对 AS2 消息进行解码时遇到 BTS MIME 错误</span><span class="sxs-lookup"><span data-stu-id="e0a80-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="e0a80-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e0a80-103">Details</span></span>  
  
|                 |                                                                                                                                    |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="e0a80-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e0a80-104">Product Name</span></span>   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                         |
| <span data-ttu-id="e0a80-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e0a80-105">Product Version</span></span> |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                     |
|    <span data-ttu-id="e0a80-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e0a80-106">Event ID</span></span>     |                                                                 -                                                                  |
|  <span data-ttu-id="e0a80-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e0a80-107">Event Source</span></span>   |                                                         <span data-ttu-id="e0a80-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="e0a80-108">BizTalk Server EDI</span></span>                                                         |
|    <span data-ttu-id="e0a80-109">组件</span><span class="sxs-lookup"><span data-stu-id="e0a80-109">Component</span></span>    |                                                             <span data-ttu-id="e0a80-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="e0a80-110">AS2 Engine</span></span>                                                             |
|  <span data-ttu-id="e0a80-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e0a80-111">Symbolic Name</span></span>  |                                                                 -                                                                  |
|  <span data-ttu-id="e0a80-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="e0a80-112">Message Text</span></span>   | <span data-ttu-id="e0a80-113">尝试对 AS2 消息进行解码时遇到 BTS MIME 错误。</span><span class="sxs-lookup"><span data-stu-id="e0a80-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="e0a80-114">AS2-从： {0}，AS2-到： {1}，MessageId: {2}，错误： {3}</span><span class="sxs-lookup"><span data-stu-id="e0a80-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="e0a80-115">解释</span><span class="sxs-lookup"><span data-stu-id="e0a80-115">Explanation</span></span>  
 <span data-ttu-id="e0a80-116">使用 BizTalk MIME 组件处理 MIME 处理的一部分时遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="e0a80-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e0a80-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e0a80-117">User Action</span></span>  
 <span data-ttu-id="e0a80-118">完整的错误消息提供了有关 MIME 组件所遇到的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="e0a80-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="e0a80-119">请参阅 BTS MIME 错误信息有关的问题的诊断 （这是因为 AS2 组件对 MIME 处理的一部分使用 BizTalk MIME 组件）。</span><span class="sxs-lookup"><span data-stu-id="e0a80-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>