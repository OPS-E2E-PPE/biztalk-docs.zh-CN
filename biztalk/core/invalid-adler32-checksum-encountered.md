---
title: 无效的 Adler32 校验和遇到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa47a208-0f33-496e-8dbe-b50be9979bf2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3f6f3cbc822aa6e71a5789914ccdbcc5731db37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381431"
---
# <a name="invalid-adler32-checksum-encountered"></a><span data-ttu-id="f4960-102">无效的 Adler32 校验和时遇到</span><span class="sxs-lookup"><span data-stu-id="f4960-102">Invalid Adler32 checksum encountered</span></span>
## <a name="details"></a><span data-ttu-id="f4960-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f4960-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="f4960-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f4960-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="f4960-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f4960-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="f4960-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4960-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="f4960-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f4960-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f4960-108">EDI</span><span class="sxs-lookup"><span data-stu-id="f4960-108">EDI</span></span> |
|    <span data-ttu-id="f4960-109">组件</span><span class="sxs-lookup"><span data-stu-id="f4960-109">Component</span></span>    |                                       <span data-ttu-id="f4960-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="f4960-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="f4960-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f4960-111">Symbolic Name</span></span>  |                     <span data-ttu-id="f4960-112">InvalidAdler32ChecksumInCompressedMessageError</span><span class="sxs-lookup"><span data-stu-id="f4960-112">InvalidAdler32ChecksumInCompressedMessageError</span></span>                     |
|  <span data-ttu-id="f4960-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f4960-113">Message Text</span></span>   |                          <span data-ttu-id="f4960-114">无效的 Adler32 校验和时遇到</span><span class="sxs-lookup"><span data-stu-id="f4960-114">Invalid Adler32 checksum encountered</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="f4960-115">解释</span><span class="sxs-lookup"><span data-stu-id="f4960-115">Explanation</span></span>  
 <span data-ttu-id="f4960-116">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="f4960-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="f4960-117">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="f4960-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f4960-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="f4960-118">User Action</span></span>  
 <span data-ttu-id="f4960-119">利用**遇到无效的 Adler32 校验和**指示篡改的可能性非常高。</span><span class="sxs-lookup"><span data-stu-id="f4960-119">The use of **Invalid Adler32 checksum encountered** indicates a high probability of tampering.</span></span> <span data-ttu-id="f4960-120">如果您看到篡改检查**遇到无效的 Adler32 校验和**。</span><span class="sxs-lookup"><span data-stu-id="f4960-120">Check for tampering if you see **Invalid Adler32 checksum encountered**.</span></span>