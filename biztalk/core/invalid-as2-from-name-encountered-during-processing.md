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
ms.openlocfilehash: c9d007b4c20a21606b83395ef1a4d2226cca8508
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381381"
---
# <a name="invalid-as2-from-name-encountered-during-processing"></a><span data-ttu-id="a85bb-102">无效的 AS2-从处理过程中遇到的名称</span><span class="sxs-lookup"><span data-stu-id="a85bb-102">Invalid AS2-From name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="a85bb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a85bb-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="a85bb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a85bb-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="a85bb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a85bb-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="a85bb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a85bb-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="a85bb-107">事件源</span><span class="sxs-lookup"><span data-stu-id="a85bb-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="a85bb-108">EDI</span><span class="sxs-lookup"><span data-stu-id="a85bb-108">EDI</span></span> |
|    <span data-ttu-id="a85bb-109">组件</span><span class="sxs-lookup"><span data-stu-id="a85bb-109">Component</span></span>    |                                       <span data-ttu-id="a85bb-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="a85bb-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="a85bb-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="a85bb-111">Symbolic Name</span></span>  |                           <span data-ttu-id="a85bb-112">InvalidAS2FromNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="a85bb-112">InvalidAS2FromNameEncounteredError</span></span>                           |
|  <span data-ttu-id="a85bb-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="a85bb-113">Message Text</span></span>   |            <span data-ttu-id="a85bb-114">无效的 AS2-从处理过程中遇到的名称。</span><span class="sxs-lookup"><span data-stu-id="a85bb-114">Invalid AS2-From name encountered during processing.</span></span>  <span data-ttu-id="a85bb-115">值： {0}</span><span class="sxs-lookup"><span data-stu-id="a85bb-115">Value: {0}</span></span>            |
  
## <a name="explanation"></a><span data-ttu-id="a85bb-116">解释</span><span class="sxs-lookup"><span data-stu-id="a85bb-116">Explanation</span></span>  
 <span data-ttu-id="a85bb-117">此错误/警告/信息事件表明的接收管道无法处理传入的交换或发送管道无法处理传出的交换，因为 as2-From 标头不符合AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="a85bb-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-From header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a85bb-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="a85bb-118">User Action</span></span>  
 <span data-ttu-id="a85bb-119">若要解决此错误，请确保 AS2-From 中传入或传出消息的标头符合 AS2 RFC 4130 第，6.2 节中的规范，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="a85bb-119">To resolve this error, make sure that the AS2-From header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130, and then have the message resent.</span></span>