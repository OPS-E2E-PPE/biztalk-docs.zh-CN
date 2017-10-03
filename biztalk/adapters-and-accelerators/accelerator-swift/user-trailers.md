---
title: "用户拖车安排 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dc2d7f2a3dd21d35bb33fa625f59aa27c04e656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="user-trailers"></a><span data-ttu-id="dd645-102">用户拖车安排</span><span class="sxs-lookup"><span data-stu-id="dd645-102">User Trailers</span></span>
<span data-ttu-id="dd645-103">用户预告片除外，选项尾端是可选的当存在时，将按以下顺序发生：</span><span class="sxs-lookup"><span data-stu-id="dd645-103">User trailers, except for the CHK trailer, are optional and when present, occur in the following order:</span></span>  
  
|<span data-ttu-id="dd645-104">电影预告片代码</span><span class="sxs-lookup"><span data-stu-id="dd645-104">Trailer code</span></span>|<span data-ttu-id="dd645-105">Name</span><span class="sxs-lookup"><span data-stu-id="dd645-105">Name</span></span>|  
|------------------|----------|  
|<span data-ttu-id="dd645-106">MAC</span><span class="sxs-lookup"><span data-stu-id="dd645-106">MAC</span></span>|<span data-ttu-id="dd645-107">消息验证代码</span><span class="sxs-lookup"><span data-stu-id="dd645-107">Message Authentication Code</span></span>|  
|<span data-ttu-id="dd645-108">PAC</span><span class="sxs-lookup"><span data-stu-id="dd645-108">PAC</span></span>|<span data-ttu-id="dd645-109">专有身份验证代码</span><span class="sxs-lookup"><span data-stu-id="dd645-109">Proprietary Authentication Code</span></span>|  
|<span data-ttu-id="dd645-110">选项</span><span class="sxs-lookup"><span data-stu-id="dd645-110">CHK</span></span>|<span data-ttu-id="dd645-111">Checksum</span><span class="sxs-lookup"><span data-stu-id="dd645-111">Checksum</span></span>|  
|<span data-ttu-id="dd645-112">TNG</span><span class="sxs-lookup"><span data-stu-id="dd645-112">TNG</span></span>|<span data-ttu-id="dd645-113">培训</span><span class="sxs-lookup"><span data-stu-id="dd645-113">Training</span></span>|  
|<span data-ttu-id="dd645-114">PDE</span><span class="sxs-lookup"><span data-stu-id="dd645-114">PDE</span></span>|<span data-ttu-id="dd645-115">可能的重复发出</span><span class="sxs-lookup"><span data-stu-id="dd645-115">Possible Duplicate Emission</span></span>|  
  
-   <span data-ttu-id="dd645-116">**消息身份验证代码 (MAC) 预告片。**</span><span class="sxs-lookup"><span data-stu-id="dd645-116">**Message Authentication Code (MAC) Trailer.**</span></span> <span data-ttu-id="dd645-117">允许接收用户的身份验证。</span><span class="sxs-lookup"><span data-stu-id="dd645-117">Allows authentication by the receiving user.</span></span> <span data-ttu-id="dd645-118">MAC 预告片跟身份验证结果。</span><span class="sxs-lookup"><span data-stu-id="dd645-118">The MAC trailer is followed by an authentication result.</span></span> <span data-ttu-id="dd645-119">此预告片是 FIN 应用程序中的大多数用户和用户消息类别必需的。</span><span class="sxs-lookup"><span data-stu-id="dd645-119">This trailer is mandatory for most user-to-user message categories within the FIN application.</span></span>  
  
     <span data-ttu-id="dd645-120">当使用 FIN 复制服务时，PAC 尾部 （如果有） 将遵循 MAC 预告片。</span><span class="sxs-lookup"><span data-stu-id="dd645-120">When the FIN Copy Service is used, a PAC trailer (if present) follows the MAC trailer.</span></span> <span data-ttu-id="dd645-121">下面的代码演示了 MAC 尾部：</span><span class="sxs-lookup"><span data-stu-id="dd645-121">The following code is an example of a MAC trailer:</span></span>  
  
    ```  
    {MAC:<authentication-result>}  
    where <authentication-result> = 8!h  
    ```  
  
-   <span data-ttu-id="dd645-122">**专有身份验证代码 (PAC) 预告片。**</span><span class="sxs-lookup"><span data-stu-id="dd645-122">**Proprietary Authentication Code (PAC) Trailer.**</span></span> <span data-ttu-id="dd645-123">仅在使用双重身份验证选项时，将 FIN 复制服务中使用 PAC 预告片。</span><span class="sxs-lookup"><span data-stu-id="dd645-123">The PAC trailer is used within the FIN Copy service only when using the double authentication option.</span></span> <span data-ttu-id="dd645-124">如果存在，块 5 的 FIN 用户和用户消息后，MAC 尾端立即包括 PAC 预告片。</span><span class="sxs-lookup"><span data-stu-id="dd645-124">Block 5 of FIN user-to-user messages include the PAC trailer immediately after the MAC trailer, if present.</span></span> <span data-ttu-id="dd645-125">如果存在，此结果的消息，115，字段的值的块 4 的提取字段计算和\<身份验证结果 > 的 MAC 电影预告片复制服务以使用双重身份验证。</span><span class="sxs-lookup"><span data-stu-id="dd645-125">This result is calculated on the extracted fields of Block 4 of the message, the value of field 115, if present, and the \<authentication-result> of the MAC trailer for Copy Services with double authentication.</span></span>  
  
     <span data-ttu-id="dd645-126">因此，PAC 计算中包含的结束块指示器 （CrLf-） 和字段的定义如下：</span><span class="sxs-lookup"><span data-stu-id="dd645-126">As a result, the end-of-block indicator (CrLf-) is included in the PAC calculation and the fields are defined as follows:</span></span>  
  
    -   <span data-ttu-id="dd645-127">前四个字符都是 CrLf:</span><span class="sxs-lookup"><span data-stu-id="dd645-127">The first four characters are CrLf:</span></span>  
  
    -   <span data-ttu-id="dd645-128">字段和分隔符都存在，即 32A: 20，:，依次类推。</span><span class="sxs-lookup"><span data-stu-id="dd645-128">The field and the delimiter are present, that is, 32A:, 20:, and so on.</span></span>  
  
    -   <span data-ttu-id="dd645-129">所有的子字段和其分隔符存在。</span><span class="sxs-lookup"><span data-stu-id="dd645-129">All subfields and their delimiters are present.</span></span>  
  
     <span data-ttu-id="dd645-130">下面的代码演示了 PAC 预告片格式：</span><span class="sxs-lookup"><span data-stu-id="dd645-130">The following code is an example of the PAC trailer format:</span></span>  
  
    ```  
    {PAC:[<authentication-result>]}  
    where <authentication-result> is mandatory on input messages only and  
    <authentication-result> = 8!h  
    ```  
  
-   <span data-ttu-id="dd645-131">**选项 （校验和） 预告片 （对于所有 FIN 消息是必需的）**</span><span class="sxs-lookup"><span data-stu-id="dd645-131">**CHK (Checksum) Trailer (mandatory for all FIN messages)**</span></span>  
  
     <span data-ttu-id="dd645-132">选项电影预告片对于所有 FIN 消息是必需的和计算根据接收方的地址 (第 9 个字符的 12 个字符替换为*X* plus 文本块)。</span><span class="sxs-lookup"><span data-stu-id="dd645-132">The CHK trailer is mandatory for all FIN messages and is computed based upon the receiver's address (12 characters with the ninth character replaced by *X* plus the text block).</span></span> <span data-ttu-id="dd645-133">此预告片允许系统以及 CBT 以检查该消息未损坏，由于系统故障或未检测到的传输错误。</span><span class="sxs-lookup"><span data-stu-id="dd645-133">This trailer allows the system and the CBT to check that messages are not corrupted due to a system malfunction or an undetected transmission error.</span></span>  
  
     <span data-ttu-id="dd645-134">下面的代码演示了选项预告片格式：</span><span class="sxs-lookup"><span data-stu-id="dd645-134">The following code is an example of the CHK trailer format:</span></span>  
  
    ```  
    {CHK:<checksum-result>}  
    where <checksum-result> = 12!h  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dd645-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd645-135">See Also</span></span>  
 [<span data-ttu-id="dd645-136">使用架构</span><span class="sxs-lookup"><span data-stu-id="dd645-136">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)