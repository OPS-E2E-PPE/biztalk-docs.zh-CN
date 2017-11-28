---
title: "当尝试进行解码 AS2 消息时遇到 BTS MIME 错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65cb5ece-78e4-4b83-b126-4d8c588b2c61
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 660a9e3a6ca5834448dd64815b031e00a0b2942a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="060c2-102">尝试对 AS2 消息进行解码时遇到 BTS MIME 错误</span><span class="sxs-lookup"><span data-stu-id="060c2-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="060c2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="060c2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="060c2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="060c2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="060c2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="060c2-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="060c2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="060c2-106">Event ID</span></span>|-|  
|<span data-ttu-id="060c2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="060c2-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="060c2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="060c2-108"> EDI</span></span>|  
|<span data-ttu-id="060c2-109">组件</span><span class="sxs-lookup"><span data-stu-id="060c2-109">Component</span></span>|<span data-ttu-id="060c2-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="060c2-110">AS2 Engine</span></span>|  
|<span data-ttu-id="060c2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="060c2-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="060c2-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="060c2-112">Message Text</span></span>|<span data-ttu-id="060c2-113">尝试对 AS2 消息进行解码时遇到 BTS MIME 错误。</span><span class="sxs-lookup"><span data-stu-id="060c2-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="060c2-114">AS2-从: {0}，AS2-到： {1}，MessageId: {2}，错误： {3}</span><span class="sxs-lookup"><span data-stu-id="060c2-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="060c2-115">解释</span><span class="sxs-lookup"><span data-stu-id="060c2-115">Explanation</span></span>  
 <span data-ttu-id="060c2-116">使用 BizTalk MIME 组件处理 MIME 处理的一部分时遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="060c2-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="060c2-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="060c2-117">User Action</span></span>  
 <span data-ttu-id="060c2-118">完整错误消息提供有关遇到的 MIME 组件的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="060c2-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="060c2-119">请参阅 （这是因为 AS2 组件将 BizTalk MIME 组件用于 MIME 处理的一部分） 问题诊断的 BTS MIME 错误信息。</span><span class="sxs-lookup"><span data-stu-id="060c2-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>