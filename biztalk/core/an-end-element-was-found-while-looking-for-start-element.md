---
title: 查找 Start 元素时发现一个 End 元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7690744-a795-47cc-bc66-a0314a4cc320
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e200f4ffd8d822a5c2bb1a0bad74a60e84a408a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992425"
---
# <a name="an-end-element-was-found-while-looking-for-start-element"></a><span data-ttu-id="7092a-102">查找 Start 元素时发现一个 End 元素</span><span class="sxs-lookup"><span data-stu-id="7092a-102">An End Element was found while looking for Start Element</span></span>
## <a name="details"></a><span data-ttu-id="7092a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7092a-103">Details</span></span>  
  
|                 |                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7092a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7092a-104">Product Name</span></span>   |        [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]         |
| <span data-ttu-id="7092a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7092a-105">Product Version</span></span> |                    [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                     |
|    <span data-ttu-id="7092a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7092a-106">Event ID</span></span>     |                                                 -                                                 |
|  <span data-ttu-id="7092a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7092a-107">Event Source</span></span>   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="7092a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="7092a-108"> EDI</span></span>       |
|    <span data-ttu-id="7092a-109">组件</span><span class="sxs-lookup"><span data-stu-id="7092a-109">Component</span></span>    |                                            <span data-ttu-id="7092a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7092a-110">EDI Engine</span></span>                                             |
|  <span data-ttu-id="7092a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7092a-111">Symbolic Name</span></span>  |                             <span data-ttu-id="7092a-112">EndElementFoundWhenLookingForStartElement</span><span class="sxs-lookup"><span data-stu-id="7092a-112">EndElementFoundWhenLookingForStartElement</span></span>                             |
|  <span data-ttu-id="7092a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="7092a-113">Message Text</span></span>   | <span data-ttu-id="7092a-114">名称的 EndElement{0}具有名称查找的 StartElement 时已发现{1}，在深度 {2}</span><span class="sxs-lookup"><span data-stu-id="7092a-114">An EndElement with name {0} was found, while looking for StartElement with name {1}, at depth {2}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7092a-115">解释</span><span class="sxs-lookup"><span data-stu-id="7092a-115">Explanation</span></span>  
 <span data-ttu-id="7092a-116">此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 XML 消息（分析后）或传出的 XML 消息（序列化前），因为 XML 消息未通过验证。</span><span class="sxs-lookup"><span data-stu-id="7092a-116">This Error/Warning/Information event indicates that BizTalk Server could not process an incoming XML message (after parsing) or an outgoing XML message (before serialization) because the XML message failed validation.</span></span> <span data-ttu-id="7092a-117">XML 消息不包含标头或数据元素的结束标记。</span><span class="sxs-lookup"><span data-stu-id="7092a-117">The XML message did not contain an end tag for a header or data element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7092a-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="7092a-118">User Action</span></span>  
 <span data-ttu-id="7092a-119">若要解决此错误，请向 XML 消息中添加相应的结束标记或尾部，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="7092a-119">To resolve this error, add the appropriate end tag or trailer to the XML message, and then resend the message.</span></span>