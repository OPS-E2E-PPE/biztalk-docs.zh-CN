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
ms.openlocfilehash: 61911e53061b0c4ec84b73f533f85a868a0088aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65327627"
---
# <a name="mandatory-data-element-missing"></a><span data-ttu-id="c9c93-102">必需数据元素缺失</span><span class="sxs-lookup"><span data-stu-id="c9c93-102">Mandatory data element missing</span></span>
## <a name="details"></a><span data-ttu-id="c9c93-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c9c93-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c9c93-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c9c93-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c9c93-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c9c93-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c9c93-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c9c93-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c9c93-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c9c93-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c9c93-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c9c93-108">EDI</span></span> |
|    <span data-ttu-id="c9c93-109">组件</span><span class="sxs-lookup"><span data-stu-id="c9c93-109">Component</span></span>    |                                       <span data-ttu-id="c9c93-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c9c93-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c9c93-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c9c93-111">Symbolic Name</span></span>  |                      <span data-ttu-id="c9c93-112">X12DeMandatoryDataElementMissingDescription</span><span class="sxs-lookup"><span data-stu-id="c9c93-112">X12DeMandatoryDataElementMissingDescription</span></span>                       |
|  <span data-ttu-id="c9c93-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="c9c93-113">Message Text</span></span>   |                             <span data-ttu-id="c9c93-114">必需数据元素缺失</span><span class="sxs-lookup"><span data-stu-id="c9c93-114">Mandatory data element missing</span></span>                             |
  
## <a name="explanation"></a><span data-ttu-id="c9c93-115">解释</span><span class="sxs-lookup"><span data-stu-id="c9c93-115">Explanation</span></span>  
 <span data-ttu-id="c9c93-116">此错误/警告/信息事件表明接收管道无法处理传入的 X12 交换，因为交换不包含消息架构（其 minOccurs 大于 0）所需的数据元素。</span><span class="sxs-lookup"><span data-stu-id="c9c93-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming X12 interchange because the interchange did not contain a data element that is required by the message schema (for which minOccurs is greater than 0).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9c93-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="c9c93-117">User Action</span></span>  
 <span data-ttu-id="c9c93-118">若要解决此错误，请确保交换包含消息架构所需的所有数据元素，然后重新发送消息。</span><span class="sxs-lookup"><span data-stu-id="c9c93-118">To resolve this error, make sure that the interchange contains all the data elements required by the message schema, and then have the message resent.</span></span>