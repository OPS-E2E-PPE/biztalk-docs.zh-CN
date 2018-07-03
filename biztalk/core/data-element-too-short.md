---
title: 数据元素太短 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22c0551-3262-476c-a6c6-2fd214331244
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db14770404a45ddbfd3aea6ed71e9b8b22417515
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005294"
---
# <a name="data-element-too-short"></a><span data-ttu-id="01197-102">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="01197-102">Data element too short</span></span>
## <a name="details"></a><span data-ttu-id="01197-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="01197-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="01197-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="01197-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="01197-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="01197-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="01197-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="01197-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="01197-107">事件源</span><span class="sxs-lookup"><span data-stu-id="01197-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="01197-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="01197-108"> EDI</span></span> |
|    <span data-ttu-id="01197-109">组件</span><span class="sxs-lookup"><span data-stu-id="01197-109">Component</span></span>    |                                       <span data-ttu-id="01197-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="01197-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="01197-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="01197-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="01197-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="01197-112">Message Text</span></span>   |                                 <span data-ttu-id="01197-113">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="01197-113">Data element too short</span></span>                                 |
  
## <a name="explanation"></a><span data-ttu-id="01197-114">解释</span><span class="sxs-lookup"><span data-stu-id="01197-114">Explanation</span></span>  
 <span data-ttu-id="01197-115">此错误/警告/信息事件表明 EDI 接收管道或 EDI 发送管道无法处理传入的交换，因为数据元素短于架构指定的最小长度。</span><span class="sxs-lookup"><span data-stu-id="01197-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was shorter than the minimum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01197-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="01197-116">User Action</span></span>  
 <span data-ttu-id="01197-117">若要解决此错误，延长函数太短，因此其值大于最小长度的交换中的数据元素。</span><span class="sxs-lookup"><span data-stu-id="01197-117">To resolve this error, lengthen the data element in the interchange that was too short so it is greater than the minimum length.</span></span> <span data-ttu-id="01197-118">若要确定最小长度，打开 \XSD_Schema 文件夹中的架构、 数据元素 id，搜索和识别 minLength 值是什么。</span><span class="sxs-lookup"><span data-stu-id="01197-118">To determine the minimum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the minLength value is.</span></span>