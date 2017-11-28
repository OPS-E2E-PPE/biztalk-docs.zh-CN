---
title: "太短的数据元素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a22c0551-3262-476c-a6c6-2fd214331244
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 311c40d80f1299ce4abcf5f2e5aec5cac2681251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-element-too-short"></a><span data-ttu-id="0ee63-102">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="0ee63-102">Data element too short</span></span>
## <a name="details"></a><span data-ttu-id="0ee63-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0ee63-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0ee63-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0ee63-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0ee63-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0ee63-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0ee63-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0ee63-106">Event ID</span></span>|-|  
|<span data-ttu-id="0ee63-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0ee63-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0ee63-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0ee63-108"> EDI</span></span>|  
|<span data-ttu-id="0ee63-109">组件</span><span class="sxs-lookup"><span data-stu-id="0ee63-109">Component</span></span>|<span data-ttu-id="0ee63-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0ee63-110">EDI Engine</span></span>|  
|<span data-ttu-id="0ee63-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0ee63-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="0ee63-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="0ee63-112">Message Text</span></span>|<span data-ttu-id="0ee63-113">数据元素太短</span><span class="sxs-lookup"><span data-stu-id="0ee63-113">Data element too short</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0ee63-114">解释</span><span class="sxs-lookup"><span data-stu-id="0ee63-114">Explanation</span></span>  
 <span data-ttu-id="0ee63-115">此错误/警告/信息事件表明 EDI 接收管道或 EDI 发送管道无法处理传入的交换，因为数据元素短于架构指定的最小长度。</span><span class="sxs-lookup"><span data-stu-id="0ee63-115">This Error/Warning/Information event indicates that the EDI receive pipeline or the EDI Send pipeline could not process the incoming interchange because a data element was shorter than the minimum length specified by the schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0ee63-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="0ee63-116">User Action</span></span>  
 <span data-ttu-id="0ee63-117">若要解决此错误，延长长度太短，因此它是大于最小长度交换中的数据元素。</span><span class="sxs-lookup"><span data-stu-id="0ee63-117">To resolve this error, lengthen the data element in the interchange that was too short so it is greater than the minimum length.</span></span> <span data-ttu-id="0ee63-118">若要确定的最小长度，\XSD_Schema 文件夹中打开该架构、 数据元素 ID，搜索和标识 minLength 值是什么。</span><span class="sxs-lookup"><span data-stu-id="0ee63-118">To determine the minimum length, open the schema in the \XSD_Schema folder, search on the data element ID, and identify what the minLength value is.</span></span>