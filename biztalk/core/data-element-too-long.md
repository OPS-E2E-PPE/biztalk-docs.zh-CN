---
title: 数据元素太长 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bf608cc1-d482-4e19-8f56-10d9e03feb79
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 134c2c2b0931373840cf5726d8f6680590840b9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988734"
---
# <a name="data-element-too-long"></a><span data-ttu-id="cd307-102">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="cd307-102">Data element too long</span></span>
## <a name="details"></a><span data-ttu-id="cd307-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="cd307-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="cd307-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="cd307-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="cd307-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="cd307-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="cd307-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="cd307-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="cd307-107">事件源</span><span class="sxs-lookup"><span data-stu-id="cd307-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cd307-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="cd307-108"> EDI</span></span> |
|    <span data-ttu-id="cd307-109">组件</span><span class="sxs-lookup"><span data-stu-id="cd307-109">Component</span></span>    |                                       <span data-ttu-id="cd307-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="cd307-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="cd307-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="cd307-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="cd307-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="cd307-112">Message Text</span></span>   |                                 <span data-ttu-id="cd307-113">数据元素太长</span><span class="sxs-lookup"><span data-stu-id="cd307-113">Data element too long</span></span>                                  |
  
## <a name="explanation"></a><span data-ttu-id="cd307-114">解释</span><span class="sxs-lookup"><span data-stu-id="cd307-114">Explanation</span></span>  
 <span data-ttu-id="cd307-115">此错误/警告/信息事件表明 EDI 接收管道或 EDI 发送管道无法处理传入的交换，因为数据元素的长度大于架构指定的最大长度。</span><span class="sxs-lookup"><span data-stu-id="cd307-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was longer than the maximum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cd307-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="cd307-116">User Action</span></span>  
 <span data-ttu-id="cd307-117">若要解决此错误，请缩短交换中太长的数据元素，以便该数据元素低于最大限制。</span><span class="sxs-lookup"><span data-stu-id="cd307-117">To resolve this error, shorten the data element in the interchange that was too long so it is below the maximum limit.</span></span> <span data-ttu-id="cd307-118">若要确定最大长度，请打开 \XSD_Schema 文件夹中的架构，搜索数据元素 ID，并确定 maxLength 值。</span><span class="sxs-lookup"><span data-stu-id="cd307-118">To determine the maximum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the maxLength value is.</span></span>