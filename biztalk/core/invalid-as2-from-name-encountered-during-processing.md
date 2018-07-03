---
title: 无效的 AS2-从处理过程中遇到的名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba658119-9171-4851-835c-72c188275b73
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30277473c0b5bdae8eeb3228b9f53275498842a4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975806"
---
# <a name="invalid-as2-from-name-encountered-during-processing"></a><span data-ttu-id="840b2-102">处理过程中遇到无效的 AS2-To 名称</span><span class="sxs-lookup"><span data-stu-id="840b2-102">Invalid AS2-From name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="840b2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="840b2-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="840b2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="840b2-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="840b2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="840b2-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="840b2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="840b2-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="840b2-107">事件源</span><span class="sxs-lookup"><span data-stu-id="840b2-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="840b2-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="840b2-108"> EDI</span></span> |
|    <span data-ttu-id="840b2-109">组件</span><span class="sxs-lookup"><span data-stu-id="840b2-109">Component</span></span>    |                                       <span data-ttu-id="840b2-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="840b2-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="840b2-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="840b2-111">Symbolic Name</span></span>  |                           <span data-ttu-id="840b2-112">InvalidAS2FromNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="840b2-112">InvalidAS2FromNameEncounteredError</span></span>                           |
|  <span data-ttu-id="840b2-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="840b2-113">Message Text</span></span>   |            <span data-ttu-id="840b2-114">处理过程中遇到无效的 AS2-From 名称。</span><span class="sxs-lookup"><span data-stu-id="840b2-114">Invalid AS2-From name encountered during processing.</span></span>  <span data-ttu-id="840b2-115">值： {0}</span><span class="sxs-lookup"><span data-stu-id="840b2-115">Value: {0}</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="840b2-116">解释</span><span class="sxs-lookup"><span data-stu-id="840b2-116">Explanation</span></span>  
 <span data-ttu-id="840b2-117">此错误/警告/信息事件表明接收管道无法处理传入的交换或者发送管道无法处理传出的交换，因为 AS2-From 标头的值不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="840b2-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-From header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="840b2-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="840b2-118">User Action</span></span>  
 <span data-ttu-id="840b2-119">若要解决此错误，请确保传入或传出消息中的 AS2-From 标头符合 AS2 RFC 4130 第 6.2 节中的规范，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="840b2-119">To resolve this error, make sure that the AS2-From header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>