---
title: 用户尾部 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d783fd053281f487f6f97fa7c0d2b67879adac7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529710"
---
# <a name="user-trailers"></a><span data-ttu-id="2bde5-102">用户尾部</span><span class="sxs-lookup"><span data-stu-id="2bde5-102">User Trailers</span></span>
<span data-ttu-id="2bde5-103">用户尾部，除了 CHK 尾部是可选的当存在时，将按以下顺序发生：</span><span class="sxs-lookup"><span data-stu-id="2bde5-103">User trailers, except for the CHK trailer, are optional and when present, occur in the following order:</span></span>  
  
|<span data-ttu-id="2bde5-104">尾部代码</span><span class="sxs-lookup"><span data-stu-id="2bde5-104">Trailer code</span></span>|<span data-ttu-id="2bde5-105">“属性”</span><span class="sxs-lookup"><span data-stu-id="2bde5-105">Name</span></span>|  
|------------------|----------|  
|<span data-ttu-id="2bde5-106">MAC</span><span class="sxs-lookup"><span data-stu-id="2bde5-106">MAC</span></span>|<span data-ttu-id="2bde5-107">消息身份验证代码</span><span class="sxs-lookup"><span data-stu-id="2bde5-107">Message Authentication Code</span></span>|  
|<span data-ttu-id="2bde5-108">PAC</span><span class="sxs-lookup"><span data-stu-id="2bde5-108">PAC</span></span>|<span data-ttu-id="2bde5-109">专有身份验证代码</span><span class="sxs-lookup"><span data-stu-id="2bde5-109">Proprietary Authentication Code</span></span>|  
|<span data-ttu-id="2bde5-110">CHK</span><span class="sxs-lookup"><span data-stu-id="2bde5-110">CHK</span></span>|<span data-ttu-id="2bde5-111">校验和</span><span class="sxs-lookup"><span data-stu-id="2bde5-111">Checksum</span></span>|  
|<span data-ttu-id="2bde5-112">TNG</span><span class="sxs-lookup"><span data-stu-id="2bde5-112">TNG</span></span>|<span data-ttu-id="2bde5-113">培训</span><span class="sxs-lookup"><span data-stu-id="2bde5-113">Training</span></span>|  
|<span data-ttu-id="2bde5-114">PDE</span><span class="sxs-lookup"><span data-stu-id="2bde5-114">PDE</span></span>|<span data-ttu-id="2bde5-115">可能的重复发出</span><span class="sxs-lookup"><span data-stu-id="2bde5-115">Possible Duplicate Emission</span></span>|  
  
- <span data-ttu-id="2bde5-116">**消息身份验证代码 (MAC) 尾部。**</span><span class="sxs-lookup"><span data-stu-id="2bde5-116">**Message Authentication Code (MAC) Trailer.**</span></span> <span data-ttu-id="2bde5-117">允许接收的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2bde5-117">Allows authentication by the receiving user.</span></span> <span data-ttu-id="2bde5-118">MAC 尾部后跟一个身份验证结果。</span><span class="sxs-lookup"><span data-stu-id="2bde5-118">The MAC trailer is followed by an authentication result.</span></span> <span data-ttu-id="2bde5-119">此尾部是必需的 FIN 应用程序中的大多数用户的消息类别。</span><span class="sxs-lookup"><span data-stu-id="2bde5-119">This trailer is mandatory for most user-to-user message categories within the FIN application.</span></span>  
  
   <span data-ttu-id="2bde5-120">当使用 FIN 复制服务时，PAC 尾部 （如果存在） 遵循 MAC 尾部。</span><span class="sxs-lookup"><span data-stu-id="2bde5-120">When the FIN Copy Service is used, a PAC trailer (if present) follows the MAC trailer.</span></span> <span data-ttu-id="2bde5-121">下面的代码是 MAC 尾部的示例：</span><span class="sxs-lookup"><span data-stu-id="2bde5-121">The following code is an example of a MAC trailer:</span></span>  
  
  ```  
  {MAC:<authentication-result>}  
  where <authentication-result> = 8!h  
  ```  
  
- <span data-ttu-id="2bde5-122">**专有身份验证代码 (PAC) 尾部。**</span><span class="sxs-lookup"><span data-stu-id="2bde5-122">**Proprietary Authentication Code (PAC) Trailer.**</span></span> <span data-ttu-id="2bde5-123">仅当使用两次身份验证选项时，将 FIN 复制服务中使用 PAC 尾部。</span><span class="sxs-lookup"><span data-stu-id="2bde5-123">The PAC trailer is used within the FIN Copy service only when using the double authentication option.</span></span> <span data-ttu-id="2bde5-124">如果存在，块 5 的 FIN 用户和用户消息 MAC 尾部后立即包含 PAC 尾部。</span><span class="sxs-lookup"><span data-stu-id="2bde5-124">Block 5 of FIN user-to-user messages include the PAC trailer immediately after the MAC trailer, if present.</span></span> <span data-ttu-id="2bde5-125">此结果进行计算的消息，第 115，字段的值的块 4 提取的字段 （如果存在） 和\<身份验证结果\>MAC 尾部的复制服务使用两次身份验证。</span><span class="sxs-lookup"><span data-stu-id="2bde5-125">This result is calculated on the extracted fields of Block 4 of the message, the value of field 115, if present, and the \<authentication-result\> of the MAC trailer for Copy Services with double authentication.</span></span>  
  
   <span data-ttu-id="2bde5-126">因此，结束块指示符 （CrLf-） 包含在 PAC 计算和的字段定义，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2bde5-126">As a result, the end-of-block indicator (CrLf-) is included in the PAC calculation and the fields are defined as follows:</span></span>  
  
  - <span data-ttu-id="2bde5-127">前四个字符是 CrLf:</span><span class="sxs-lookup"><span data-stu-id="2bde5-127">The first four characters are CrLf:</span></span>  
  
  - <span data-ttu-id="2bde5-128">字段和分隔符都存在，即 32A:，20:，依此类推。</span><span class="sxs-lookup"><span data-stu-id="2bde5-128">The field and the delimiter are present, that is, 32A:, 20:, and so on.</span></span>  
  
  - <span data-ttu-id="2bde5-129">所有子字段和分隔符存在。</span><span class="sxs-lookup"><span data-stu-id="2bde5-129">All subfields and their delimiters are present.</span></span>  
  
    <span data-ttu-id="2bde5-130">以下代码是 PAC 尾部格式示例：</span><span class="sxs-lookup"><span data-stu-id="2bde5-130">The following code is an example of the PAC trailer format:</span></span>  
  
  ```  
  {PAC:[<authentication-result>]}  
  where <authentication-result> is mandatory on input messages only and  
  <authentication-result> = 8!h  
  ```  
  
- <span data-ttu-id="2bde5-131">**CHK （校验和） 尾部 （对于所有 FIN 消息是必需的）**</span><span class="sxs-lookup"><span data-stu-id="2bde5-131">**CHK (Checksum) Trailer (mandatory for all FIN messages)**</span></span>  
  
   <span data-ttu-id="2bde5-132">CHK 尾部是必需的所有 FIN 消息的根据接收方的地址计算得出 (第 9 个字符的 12 个字符替换为*X*以及文本块)。</span><span class="sxs-lookup"><span data-stu-id="2bde5-132">The CHK trailer is mandatory for all FIN messages and is computed based upon the receiver's address (12 characters with the ninth character replaced by *X* plus the text block).</span></span> <span data-ttu-id="2bde5-133">此尾部允许系统和 CBT 检查由于系统工作不正常或未检测到的传输错误消息不已损坏。</span><span class="sxs-lookup"><span data-stu-id="2bde5-133">This trailer allows the system and the CBT to check that messages are not corrupted due to a system malfunction or an undetected transmission error.</span></span>  
  
   <span data-ttu-id="2bde5-134">以下代码是 CHK 尾部格式示例：</span><span class="sxs-lookup"><span data-stu-id="2bde5-134">The following code is an example of the CHK trailer format:</span></span>  
  
  ```  
  {CHK:<checksum-result>}  
  where <checksum-result> = 12!h  
  ```  
  
## <a name="see-also"></a><span data-ttu-id="2bde5-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bde5-135">See Also</span></span>  
 [<span data-ttu-id="2bde5-136">处理架构</span><span class="sxs-lookup"><span data-stu-id="2bde5-136">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)