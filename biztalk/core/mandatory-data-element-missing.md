---
title: 必需数据元素缺失 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510d54b3-13de-4735-92ec-04fd4b9d460e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a44e4824805a137121bf1f5bd030cb16329484d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966486"
---
# <a name="mandatory-data-element-missing"></a><span data-ttu-id="6da36-102">必需数据元素缺失</span><span class="sxs-lookup"><span data-stu-id="6da36-102">Mandatory data element missing</span></span>
## <a name="details"></a><span data-ttu-id="6da36-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="6da36-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6da36-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="6da36-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6da36-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="6da36-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6da36-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="6da36-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6da36-107">事件源</span><span class="sxs-lookup"><span data-stu-id="6da36-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6da36-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6da36-108"> EDI</span></span> |
|    <span data-ttu-id="6da36-109">组件</span><span class="sxs-lookup"><span data-stu-id="6da36-109">Component</span></span>    |                                       <span data-ttu-id="6da36-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="6da36-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6da36-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="6da36-111">Symbolic Name</span></span>  |                      <span data-ttu-id="6da36-112">X12DeMandatoryDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="6da36-112">X12DeMandatoryDataElementMissingDescription</span></span>                       |
|  <span data-ttu-id="6da36-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="6da36-113">Message Text</span></span>   |                             <span data-ttu-id="6da36-114">必需数据元素缺失</span><span class="sxs-lookup"><span data-stu-id="6da36-114">Mandatory data element missing</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="6da36-115">解释</span><span class="sxs-lookup"><span data-stu-id="6da36-115">Explanation</span></span>  
 <span data-ttu-id="6da36-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换不包含消息架构（其 minOccurs 大于 0）所需的数据元素。</span><span class="sxs-lookup"><span data-stu-id="6da36-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a data element that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6da36-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="6da36-117">User Action</span></span>  
 <span data-ttu-id="6da36-118">若要解决此错误，请确保交换包含消息架构所需的所有数据元素，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="6da36-118">To resolve this error, make sure that the interchange contains all the data elements required by the message schema, and then have the message resent.</span></span>