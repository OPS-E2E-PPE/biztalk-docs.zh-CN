---
title: "无效的 ASN.1 压缩解压缩处理过程中遇到的结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e5ebbd6-249a-4746-8ee6-cfb1f52ecc94
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 825889d3379a4cbc1dc61bc688eb5ffc28745a5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-asn1-compressed-structure-encountered-during-decompression-processing"></a><span data-ttu-id="49cca-102">解压缩处理期间遇到无效的 ASN.1 压缩结构</span><span class="sxs-lookup"><span data-stu-id="49cca-102">Invalid ASN.1 compressed structure encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="49cca-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="49cca-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="49cca-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="49cca-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="49cca-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="49cca-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="49cca-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="49cca-106">Event ID</span></span>|-|  
|<span data-ttu-id="49cca-107">事件源</span><span class="sxs-lookup"><span data-stu-id="49cca-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="49cca-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="49cca-108"> EDI</span></span>|  
|<span data-ttu-id="49cca-109">组件</span><span class="sxs-lookup"><span data-stu-id="49cca-109">Component</span></span>|<span data-ttu-id="49cca-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="49cca-110">AS2 Engine</span></span>|  
|<span data-ttu-id="49cca-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="49cca-111">Symbolic Name</span></span>|<span data-ttu-id="49cca-112">InvalidASN1CompressedStructureEncountered</span><span class="sxs-lookup"><span data-stu-id="49cca-112">InvalidASN1CompressedStructureEncountered</span></span>|  
|<span data-ttu-id="49cca-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="49cca-113">Message Text</span></span>|<span data-ttu-id="49cca-114">无效或缺少 ASN.1 压缩解压缩处理过程中遇到的标头</span><span class="sxs-lookup"><span data-stu-id="49cca-114">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="49cca-115">解释</span><span class="sxs-lookup"><span data-stu-id="49cca-115">Explanation</span></span>  
 <span data-ttu-id="49cca-116">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="49cca-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="49cca-117">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="49cca-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="49cca-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="49cca-118">User Action</span></span>  
 <span data-ttu-id="49cca-119">查看压缩数据的结构并检查是否对消息进行了篡改。</span><span class="sxs-lookup"><span data-stu-id="49cca-119">Review the structure of the compressed data and check for tampering with the message.</span></span>