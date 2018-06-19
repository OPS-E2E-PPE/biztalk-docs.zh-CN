---
title: 无效的 AS2-到接收的标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56cd16b3-511b-4716-8806-817f174f0b0e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 750166045224754c05e4345c2e57e16950b89c9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256997"
---
# <a name="invalid-as2-to-header-received"></a><span data-ttu-id="ac0e3-102">收到的 AS2-To 头部无效</span><span class="sxs-lookup"><span data-stu-id="ac0e3-102">Invalid AS2-To header received</span></span>
## <a name="details"></a><span data-ttu-id="ac0e3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ac0e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ac0e3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ac0e3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="ac0e3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ac0e3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="ac0e3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ac0e3-106">Event ID</span></span>|-|  
|<span data-ttu-id="ac0e3-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ac0e3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ac0e3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="ac0e3-108"> EDI</span></span>|  
|<span data-ttu-id="ac0e3-109">组件</span><span class="sxs-lookup"><span data-stu-id="ac0e3-109">Component</span></span>|<span data-ttu-id="ac0e3-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="ac0e3-110">AS2 Engine</span></span>|  
|<span data-ttu-id="ac0e3-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ac0e3-111">Symbolic Name</span></span>|<span data-ttu-id="ac0e3-112">InvalidAS2ToNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="ac0e3-112">InvalidAS2ToNameHeaderReceivedError</span></span>|  
|<span data-ttu-id="ac0e3-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ac0e3-113">Message Text</span></span>|<span data-ttu-id="ac0e3-114">收到的 AS2-To 头部无效。</span><span class="sxs-lookup"><span data-stu-id="ac0e3-114">Invalid AS2-To header received.</span></span>  <span data-ttu-id="ac0e3-115">值： {0}</span><span class="sxs-lookup"><span data-stu-id="ac0e3-115">Value: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ac0e3-116">解释</span><span class="sxs-lookup"><span data-stu-id="ac0e3-116">Explanation</span></span>  
 <span data-ttu-id="ac0e3-117">此错误/警告/信息事件表明接收管道无法处理传入的交换，因为消息中 AS2-To 标头的值不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="ac0e3-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-To header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ac0e3-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ac0e3-118">User Action</span></span>  
 <span data-ttu-id="ac0e3-119">若要解决此错误，请确保消息中 AS2-To 标头的值符合 AS2 RFC 4130 第 6.2 节中的规范。</span><span class="sxs-lookup"><span data-stu-id="ac0e3-119">To resolve this error, make sure that the value in the AS2-To header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>