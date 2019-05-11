---
title: 解压缩处理期间遇到无效或缺失 ASN.1 数据长度字段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd08648d-77b9-42a3-a50e-fd87eb36758a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 712edc0bec0f2323901a2006065c5a28ad2c3ab4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388762"
---
# <a name="invalid-or-missing-asn1-data-length-field-encountered-during-decompression-processing"></a><span data-ttu-id="38bca-102">解压缩处理期间 ASN.1 数据长度字段无效或缺失</span><span class="sxs-lookup"><span data-stu-id="38bca-102">Invalid or missing ASN.1 Data Length field encountered during decompression processing</span></span>
## <a name="details"></a><span data-ttu-id="38bca-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="38bca-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="38bca-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="38bca-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="38bca-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="38bca-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="38bca-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="38bca-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="38bca-107">事件源</span><span class="sxs-lookup"><span data-stu-id="38bca-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="38bca-108">EDI</span><span class="sxs-lookup"><span data-stu-id="38bca-108">EDI</span></span> |
|    <span data-ttu-id="38bca-109">组件</span><span class="sxs-lookup"><span data-stu-id="38bca-109">Component</span></span>    |                                       <span data-ttu-id="38bca-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="38bca-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="38bca-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="38bca-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="38bca-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="38bca-112">Message Text</span></span>   | <span data-ttu-id="38bca-113">解压缩处理期间 ASN.1 数据长度字段无效或缺失</span><span class="sxs-lookup"><span data-stu-id="38bca-113">Invalid or missing ASN.1 Data Length field encountered during decompression processing</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="38bca-114">解释</span><span class="sxs-lookup"><span data-stu-id="38bca-114">Explanation</span></span>  
 <span data-ttu-id="38bca-115">此错误是指压缩数据的 ASN.1 结构。</span><span class="sxs-lookup"><span data-stu-id="38bca-115">This error refers to the ASN.1 structure of the compressed data.</span></span> <span data-ttu-id="38bca-116">此错误表明压缩数据的发送方未正确结构化压缩数据或者有人篡改（未经授权而进行更改）消息。</span><span class="sxs-lookup"><span data-stu-id="38bca-116">The error indicates the sender of the compressed data either structured the compressed data incorrectly or there was tampering (unauthorized change) of the message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="38bca-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="38bca-117">User Action</span></span>  
 <span data-ttu-id="38bca-118">查看压缩数据的结构并检查是否对消息进行了篡改。</span><span class="sxs-lookup"><span data-stu-id="38bca-118">Review the structure of the compressed data and check for tampering with the message.</span></span>