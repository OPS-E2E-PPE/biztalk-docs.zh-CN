---
title: 无效或缺失的 ASN.1 压缩标头解压缩处理期间遇到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e59afea-436c-42c0-b424-0b72dd9db9a8
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f1329fd8afd46ad48d014a173dd1680d12462e2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348009"
---
# <a name="invalid-or-missing-asn1-compressed-header-encountered-during-decompression-processing"></a><span data-ttu-id="7de79-102">ASN.1 压缩头部解压缩处理期间遇到无效或缺失</span><span class="sxs-lookup"><span data-stu-id="7de79-102">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="7de79-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7de79-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7de79-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7de79-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7de79-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7de79-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7de79-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7de79-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7de79-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7de79-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7de79-108">EDI</span><span class="sxs-lookup"><span data-stu-id="7de79-108">EDI</span></span> |
|    <span data-ttu-id="7de79-109">组件</span><span class="sxs-lookup"><span data-stu-id="7de79-109">Component</span></span>    |                                       <span data-ttu-id="7de79-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="7de79-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="7de79-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7de79-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="7de79-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="7de79-112">Message Text</span></span>   | <span data-ttu-id="7de79-113">ASN.1 压缩头部解压缩处理期间遇到无效或缺失</span><span class="sxs-lookup"><span data-stu-id="7de79-113">Invalid or missing ASN.1 compressed header encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7de79-114">解释</span><span class="sxs-lookup"><span data-stu-id="7de79-114">Explanation</span></span>  
 <span data-ttu-id="7de79-115">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="7de79-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="7de79-116">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="7de79-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7de79-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="7de79-117">User Action</span></span>  
 <span data-ttu-id="7de79-118">查看压缩数据的结构并检查是否对消息进行了篡改。</span><span class="sxs-lookup"><span data-stu-id="7de79-118">Review the structure of the compressed data and check for tampering with the message.</span></span>