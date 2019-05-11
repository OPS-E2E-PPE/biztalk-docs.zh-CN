---
title: 无效的 AS2-To 标头接收 |Microsoft Docs
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
ms.openlocfilehash: e9acfbb11edabc26d1a01d36e545820892c65139
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330928"
---
# <a name="invalid-as2-to-header-received"></a><span data-ttu-id="69c42-102">无效的 AS2-To 标头接收</span><span class="sxs-lookup"><span data-stu-id="69c42-102">Invalid AS2-To header received</span></span>
## <a name="details"></a><span data-ttu-id="69c42-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="69c42-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="69c42-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="69c42-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="69c42-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="69c42-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="69c42-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="69c42-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="69c42-107">事件源</span><span class="sxs-lookup"><span data-stu-id="69c42-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="69c42-108">EDI</span><span class="sxs-lookup"><span data-stu-id="69c42-108">EDI</span></span> |
|    <span data-ttu-id="69c42-109">组件</span><span class="sxs-lookup"><span data-stu-id="69c42-109">Component</span></span>    |                                       <span data-ttu-id="69c42-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="69c42-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="69c42-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="69c42-111">Symbolic Name</span></span>  |                          <span data-ttu-id="69c42-112">InvalidAS2ToNameHeaderReceivedError</span><span class="sxs-lookup"><span data-stu-id="69c42-112">InvalidAS2ToNameHeaderReceivedError</span></span>                           |
|  <span data-ttu-id="69c42-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="69c42-113">Message Text</span></span>   |                      <span data-ttu-id="69c42-114">无效的 AS2-To 标头接收。</span><span class="sxs-lookup"><span data-stu-id="69c42-114">Invalid AS2-To header received.</span></span>  <span data-ttu-id="69c42-115">值： {0}</span><span class="sxs-lookup"><span data-stu-id="69c42-115">Value: {0}</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="69c42-116">解释</span><span class="sxs-lookup"><span data-stu-id="69c42-116">Explanation</span></span>  
 <span data-ttu-id="69c42-117">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为 as2-To 标头消息中不符合 AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="69c42-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the AS2-To header in the message did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="69c42-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="69c42-118">User Action</span></span>  
 <span data-ttu-id="69c42-119">若要解决此错误，请确保值中 AS2-到消息标头符合 AS2 RFC 4130 第 6.2 节中的规范。</span><span class="sxs-lookup"><span data-stu-id="69c42-119">To resolve this error, make sure that the value in the AS2-To header of the message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>