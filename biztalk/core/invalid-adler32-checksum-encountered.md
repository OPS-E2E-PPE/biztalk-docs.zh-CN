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
ms.openlocfilehash: acaa60e9d6f1bda4161832cb5ddb34c4e2e9ae93
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987262"
---
# <a name="invalid-adler32-checksum-encountered"></a><span data-ttu-id="b45af-102">遇到无效的 Adler32 校验和</span><span class="sxs-lookup"><span data-stu-id="b45af-102">Invalid Adler32 checksum encountered</span></span>
## <a name="details"></a><span data-ttu-id="b45af-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b45af-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="b45af-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b45af-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="b45af-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b45af-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="b45af-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b45af-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="b45af-107">事件源</span><span class="sxs-lookup"><span data-stu-id="b45af-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b45af-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="b45af-108"> EDI</span></span> |
|    <span data-ttu-id="b45af-109">组件</span><span class="sxs-lookup"><span data-stu-id="b45af-109">Component</span></span>    |                                       <span data-ttu-id="b45af-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="b45af-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="b45af-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="b45af-111">Symbolic Name</span></span>  |                     <span data-ttu-id="b45af-112">InvalidAdler32ChecksumInCompressedMessageError</span><span class="sxs-lookup"><span data-stu-id="b45af-112">InvalidAdler32ChecksumInCompressedMessageError</span></span>                     |
|  <span data-ttu-id="b45af-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="b45af-113">Message Text</span></span>   |                          <span data-ttu-id="b45af-114">遇到无效的 Adler32 校验和</span><span class="sxs-lookup"><span data-stu-id="b45af-114">Invalid Adler32 checksum encountered</span></span>                          |
  
## <a name="explanation"></a><span data-ttu-id="b45af-115">解释</span><span class="sxs-lookup"><span data-stu-id="b45af-115">Explanation</span></span>  
 <span data-ttu-id="b45af-116">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="b45af-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="b45af-117">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="b45af-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b45af-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="b45af-118">User Action</span></span>  
 <span data-ttu-id="b45af-119">利用**遇到无效的 Adler32 校验和**指示篡改的可能性非常高。</span><span class="sxs-lookup"><span data-stu-id="b45af-119">The use of **Invalid Adler32 checksum encountered** indicates a high probability of tampering.</span></span> <span data-ttu-id="b45af-120">如果您看到篡改检查**遇到无效的 Adler32 校验和**。</span><span class="sxs-lookup"><span data-stu-id="b45af-120">Check for tampering if you see **Invalid Adler32 checksum encountered**.</span></span>