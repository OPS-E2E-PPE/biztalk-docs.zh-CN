---
title: 解压缩处理过程中遇到无效 ASN.1 ZLib 压缩字段 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7caf047-badd-49e8-b955-554e5ec7511f
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a347f63325e1c93497d178ffcc486ff8bd1c4f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241861"
---
# <a name="invalid-asn1-zlib-compression-field-encountered-during-decompression-processing"></a><span data-ttu-id="efe8e-102">解压缩处理期间遇到无效的 ASN.1 ZLib 压缩字段</span><span class="sxs-lookup"><span data-stu-id="efe8e-102">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="efe8e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="efe8e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efe8e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="efe8e-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="efe8e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="efe8e-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="efe8e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="efe8e-106">Event ID</span></span>|-|  
|<span data-ttu-id="efe8e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="efe8e-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="efe8e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="efe8e-108"> EDI</span></span>|  
|<span data-ttu-id="efe8e-109">组件</span><span class="sxs-lookup"><span data-stu-id="efe8e-109">Component</span></span>|<span data-ttu-id="efe8e-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="efe8e-110">AS2 Engine</span></span>|  
|<span data-ttu-id="efe8e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="efe8e-111">Symbolic Name</span></span>|<span data-ttu-id="efe8e-112">InvalidOptionalZLibFieldEncountered</span><span class="sxs-lookup"><span data-stu-id="efe8e-112">InvalidOptionalZLibFieldEncountered</span></span>|  
|<span data-ttu-id="efe8e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="efe8e-113">Message Text</span></span>|<span data-ttu-id="efe8e-114">解压缩处理期间遇到无效的 ASN.1 ZLib 压缩字段</span><span class="sxs-lookup"><span data-stu-id="efe8e-114">Invalid ASN.1 ZLib compression field encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="efe8e-115">解释</span><span class="sxs-lookup"><span data-stu-id="efe8e-115">Explanation</span></span>  
 <span data-ttu-id="efe8e-116">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="efe8e-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="efe8e-117">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="efe8e-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efe8e-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="efe8e-118">User Action</span></span>  
 <span data-ttu-id="efe8e-119">查看压缩的数据并篡改的证据，检查结构。</span><span class="sxs-lookup"><span data-stu-id="efe8e-119">Review the structure of the compressed data and check for evidence of tampering.</span></span>