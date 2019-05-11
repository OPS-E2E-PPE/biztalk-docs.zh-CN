---
title: 解压缩处理期间遇到无效的 ASN.1 压缩结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e5ebbd6-249a-4746-8ee6-cfb1f52ecc94
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d545b1b2418546bc27adb89674a57d9c915d0e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381395"
---
# <a name="invalid-asn1-compressed-structure-encountered-during-decompression-processing"></a><span data-ttu-id="c0e0a-102">解压缩处理期间遇到无效的 ASN.1 压缩结构</span><span class="sxs-lookup"><span data-stu-id="c0e0a-102">Invalid ASN.1 compressed structure encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="c0e0a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c0e0a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c0e0a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c0e0a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c0e0a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c0e0a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c0e0a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c0e0a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c0e0a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c0e0a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c0e0a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c0e0a-108">EDI</span></span> |
|    <span data-ttu-id="c0e0a-109">组件</span><span class="sxs-lookup"><span data-stu-id="c0e0a-109">Component</span></span>    |                                       <span data-ttu-id="c0e0a-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="c0e0a-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="c0e0a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c0e0a-111">Symbolic Name</span></span>  |                       <span data-ttu-id="c0e0a-112">InvalidASN1CompressedStructureEncountered</span><span class="sxs-lookup"><span data-stu-id="c0e0a-112">InvalidASN1CompressedStructureEncountered</span></span>                        |
|  <span data-ttu-id="c0e0a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c0e0a-113">Message Text</span></span>   | <span data-ttu-id="c0e0a-114">ASN.1 压缩头部解压缩处理期间遇到无效或缺失</span><span class="sxs-lookup"><span data-stu-id="c0e0a-114">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c0e0a-115">解释</span><span class="sxs-lookup"><span data-stu-id="c0e0a-115">Explanation</span></span>  
 <span data-ttu-id="c0e0a-116">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="c0e0a-116">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="c0e0a-117">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="c0e0a-117">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c0e0a-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="c0e0a-118">User Action</span></span>  
 <span data-ttu-id="c0e0a-119">查看压缩数据的结构并检查是否对消息进行了篡改。</span><span class="sxs-lookup"><span data-stu-id="c0e0a-119">Review the structure of the compressed data and check for tampering with the message.</span></span>