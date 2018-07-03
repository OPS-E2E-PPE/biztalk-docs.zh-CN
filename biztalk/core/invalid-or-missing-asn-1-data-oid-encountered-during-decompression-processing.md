---
title: 解压缩处理期间遇到无效或缺失 ASN.1 数据 OID |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 243062ae-19df-4989-b8d9-109e789f8335
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4637490e507a28db197c28b2fc98dd9daa6b6042
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998566"
---
# <a name="invalid-or-missing-asn1-data-oid-encountered-during-decompression-processing"></a><span data-ttu-id="16734-102">解压缩处理期间 ASN.1 数据 OID 无效或缺失</span><span class="sxs-lookup"><span data-stu-id="16734-102">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="16734-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="16734-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="16734-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="16734-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="16734-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="16734-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="16734-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="16734-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="16734-107">事件源</span><span class="sxs-lookup"><span data-stu-id="16734-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="16734-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="16734-108"> EDI</span></span> |
|    <span data-ttu-id="16734-109">组件</span><span class="sxs-lookup"><span data-stu-id="16734-109">Component</span></span>    |                                       <span data-ttu-id="16734-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="16734-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="16734-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="16734-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="16734-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="16734-112">Message Text</span></span>   |     <span data-ttu-id="16734-113">解压缩处理期间 ASN.1 数据 OID 无效或缺失</span><span class="sxs-lookup"><span data-stu-id="16734-113">Invalid or missing ASN.1 Data OID encountered during decompression processing</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="16734-114">解释</span><span class="sxs-lookup"><span data-stu-id="16734-114">Explanation</span></span>  
 <span data-ttu-id="16734-115">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="16734-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="16734-116">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="16734-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="16734-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="16734-117">User Action</span></span>  
 <span data-ttu-id="16734-118">查看压缩数据的结构并检查是否对消息进行了篡改。</span><span class="sxs-lookup"><span data-stu-id="16734-118">Review the structure of the compressed data and check for tampering with the message.</span></span>