---
title: 协议解析失败，协议基于上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58fccd84-579c-4b5e-872b-33730d4079e8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2cac1ea6e940385fceac541df96582f93eb058e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008166"
---
# <a name="agreement-resolution-based-on-the-context-properties-for-protocol-has-failed"></a><span data-ttu-id="09f4f-102">基于协议上下文属性的协议解析失败</span><span class="sxs-lookup"><span data-stu-id="09f4f-102">Agreement Resolution based on the context properties for Protocol has failed</span></span>
## <a name="details"></a><span data-ttu-id="09f4f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="09f4f-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="09f4f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="09f4f-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="09f4f-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="09f4f-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="09f4f-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="09f4f-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="09f4f-107">事件源</span><span class="sxs-lookup"><span data-stu-id="09f4f-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="09f4f-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="09f4f-108"> EDI</span></span> |
|    <span data-ttu-id="09f4f-109">组件</span><span class="sxs-lookup"><span data-stu-id="09f4f-109">Component</span></span>    |                                       <span data-ttu-id="09f4f-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="09f4f-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="09f4f-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="09f4f-111">Symbolic Name</span></span>  |                    <span data-ttu-id="09f4f-112">AgreementResolutionContextPropertiesLookupFailed</span><span class="sxs-lookup"><span data-stu-id="09f4f-112">AgreementResolutionContextPropertiesLookupFailed</span></span>                    |
|  <span data-ttu-id="09f4f-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="09f4f-113">Message Text</span></span>   |   <span data-ttu-id="09f4f-114">基于上下文属性的协议解析{0}协议已失败。</span><span class="sxs-lookup"><span data-stu-id="09f4f-114">Agreement Resolution based on the context properties for {0} Protocol has failed.</span></span>    |
  
## <a name="explanation"></a><span data-ttu-id="09f4f-115">解释</span><span class="sxs-lookup"><span data-stu-id="09f4f-115">Explanation</span></span>  
 <span data-ttu-id="09f4f-116">此错误/警告/信息事件表明 BizTalk Server 无法基于客户提供的上下文属性解析为协议。</span><span class="sxs-lookup"><span data-stu-id="09f4f-116">This Error/Warning/Information event indicates BizTalk Server was not able to resolve to an Agreement based on the context properties that are provided by the customer.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="09f4f-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="09f4f-117">User Action</span></span>  
 <span data-ttu-id="09f4f-118">若要解决此错误，请作为 BizTalk 消息的一部分提供上下文属性，以便可以进行协议解析。</span><span class="sxs-lookup"><span data-stu-id="09f4f-118">To resolve this error, please provide the context properties as part of the BizTalk message such that Agreement Resolution can happen.</span></span>