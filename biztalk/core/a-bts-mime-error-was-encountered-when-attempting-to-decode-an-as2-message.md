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
ms.openlocfilehash: 096696f4420150cdd53f8fe561460d243c1bb018
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="a-bts-mime-error-was-encountered-when-attempting-to-decode-an-as2-message"></a><span data-ttu-id="f6cb6-102">尝试对 AS2 消息进行解码时遇到 BTS MIME 错误</span><span class="sxs-lookup"><span data-stu-id="f6cb6-102">A BTS MIME error was encountered when attempting to decode an AS2 message</span></span>
## <a name="details"></a><span data-ttu-id="f6cb6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6cb6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6cb6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6cb6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f6cb6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6cb6-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f6cb6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6cb6-106">Event ID</span></span>|-|  
|<span data-ttu-id="f6cb6-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f6cb6-107">Event Source</span></span>|<span data-ttu-id="f6cb6-108">BizTalk Server EDI</span><span class="sxs-lookup"><span data-stu-id="f6cb6-108">BizTalk Server EDI</span></span>|  
|<span data-ttu-id="f6cb6-109">组件</span><span class="sxs-lookup"><span data-stu-id="f6cb6-109">Component</span></span>|<span data-ttu-id="f6cb6-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="f6cb6-110">AS2 Engine</span></span>|  
|<span data-ttu-id="f6cb6-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6cb6-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="f6cb6-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6cb6-112">Message Text</span></span>|<span data-ttu-id="f6cb6-113">尝试对 AS2 消息进行解码时遇到 BTS MIME 错误。</span><span class="sxs-lookup"><span data-stu-id="f6cb6-113">A BTS MIME error was encountered when attempting to decode an AS2 message.</span></span>  <span data-ttu-id="f6cb6-114">AS2-从: {0}，AS2-到： {1}，MessageId: {2}，错误： {3}</span><span class="sxs-lookup"><span data-stu-id="f6cb6-114">AS2-From: {0}, AS2-To: {1}, MessageId: {2}, Error: {3}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6cb6-115">解释</span><span class="sxs-lookup"><span data-stu-id="f6cb6-115">Explanation</span></span>  
 <span data-ttu-id="f6cb6-116">使用 BizTalk MIME 组件处理 MIME 处理的一部分时遇到此错误。</span><span class="sxs-lookup"><span data-stu-id="f6cb6-116">This error is encountered when using the BizTalk MIME component to handle part of the MIME processing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6cb6-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6cb6-117">User Action</span></span>  
 <span data-ttu-id="f6cb6-118">完整错误消息提供有关遇到的 MIME 组件的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="f6cb6-118">The full error message provides the information about the problem encountered by the MIME component.</span></span> <span data-ttu-id="f6cb6-119">请参阅 （这是因为 AS2 组件将 BizTalk MIME 组件用于 MIME 处理的一部分） 问题诊断的 BTS MIME 错误信息。</span><span class="sxs-lookup"><span data-stu-id="f6cb6-119">Refer to the BTS MIME error information for diagnosis of the problem (this is because the AS2 components use the BizTalk MIME components for part of the MIME processing).</span></span>