---
title: 无效的 AS2-到处理过程中遇到的名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 84d848b5-b2a3-460d-85d4-c3576e4e3aaf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf17c8221686562ec6cc74578d646bb832d4ea22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330901"
---
# <a name="invalid-as2-to-name-encountered-during-processing"></a><span data-ttu-id="ac1f0-102">无效的 AS2-到处理过程中遇到的名称</span><span class="sxs-lookup"><span data-stu-id="ac1f0-102">Invalid AS2-To name encountered during processing</span></span>
## <a name="details"></a><span data-ttu-id="ac1f0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ac1f0-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ac1f0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ac1f0-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ac1f0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ac1f0-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ac1f0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ac1f0-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ac1f0-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ac1f0-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ac1f0-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ac1f0-108">EDI</span></span> |
|    <span data-ttu-id="ac1f0-109">组件</span><span class="sxs-lookup"><span data-stu-id="ac1f0-109">Component</span></span>    |                                       <span data-ttu-id="ac1f0-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="ac1f0-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="ac1f0-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ac1f0-111">Symbolic Name</span></span>  |                            <span data-ttu-id="ac1f0-112">InvalidAS2ToNameEncounteredError</span><span class="sxs-lookup"><span data-stu-id="ac1f0-112">InvalidAS2ToNameEncounteredError</span></span>                            |
|  <span data-ttu-id="ac1f0-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ac1f0-113">Message Text</span></span>   |             <span data-ttu-id="ac1f0-114">无效的 AS2-到处理过程中遇到的名称。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-114">Invalid AS2-To name encountered during processing.</span></span>  <span data-ttu-id="ac1f0-115">值： {0}</span><span class="sxs-lookup"><span data-stu-id="ac1f0-115">Value: {0}</span></span>             |
  
## <a name="explanation"></a><span data-ttu-id="ac1f0-116">解释</span><span class="sxs-lookup"><span data-stu-id="ac1f0-116">Explanation</span></span>  
 <span data-ttu-id="ac1f0-117">此错误/警告/信息事件表明的接收管道无法处理传入的交换或发送管道无法处理传出的交换，因为 as2-To 标头不符合AS2 RFC 4130 中的规范。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-117">This Error/Warning/Information event indicates that either the receive pipeline could not process the incoming interchange or the send pipeline could not process the outgoing interchange because the value of the AS2-To header did not conform to the specifications in AS2 RFC 4130.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ac1f0-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ac1f0-118">User Action</span></span>  
 <span data-ttu-id="ac1f0-119">若要解决此错误，请确保 AS2-To 中传入或传出消息的标头符合 AS2 RFC 4130 第 6.2 节中的规范。</span><span class="sxs-lookup"><span data-stu-id="ac1f0-119">To resolve this error, make sure that the AS2-To header in the incoming or outgoing message conforms to the specifications in section 6.2 of AS2 RFC 4130.</span></span>