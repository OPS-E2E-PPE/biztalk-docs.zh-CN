---
title: "解压缩处理过程中遇到无效或缺少 ASN.1 数据 OID |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243062ae-19df-4989-b8d9-109e789f8335
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da26bfb0ff76ec8b78e6572dba14631ff84fd9f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-or-missing-asn1-data-oid-encountered-during-decompression-processing"></a><span data-ttu-id="f8723-102">解压缩处理期间 ASN.1 数据 OID 无效或缺失</span><span class="sxs-lookup"><span data-stu-id="f8723-102">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="f8723-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f8723-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f8723-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f8723-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f8723-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f8723-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f8723-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f8723-106">Event ID</span></span>|-|  
|<span data-ttu-id="f8723-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f8723-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f8723-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f8723-108"> EDI</span></span>|  
|<span data-ttu-id="f8723-109">组件</span><span class="sxs-lookup"><span data-stu-id="f8723-109">Component</span></span>|<span data-ttu-id="f8723-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="f8723-110">AS2 Engine</span></span>|  
|<span data-ttu-id="f8723-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f8723-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="f8723-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="f8723-112">Message Text</span></span>|<span data-ttu-id="f8723-113">解压缩处理期间 ASN.1 数据 OID 无效或缺失</span><span class="sxs-lookup"><span data-stu-id="f8723-113">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f8723-114">解释</span><span class="sxs-lookup"><span data-stu-id="f8723-114">Explanation</span></span>  
 <span data-ttu-id="f8723-115">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="f8723-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="f8723-116">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="f8723-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f8723-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="f8723-117">User Action</span></span>  
 <span data-ttu-id="f8723-118">查看压缩数据的结构并检查是否对消息进行了篡改。</span><span class="sxs-lookup"><span data-stu-id="f8723-118">Review the structure of the compressed data and check for tampering with the message.</span></span>