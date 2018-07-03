---
title: 段标记 id 后找不到字段分隔符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f6f0a74-3560-4d6d-9893-85e8426e6b17
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82511305a9df96af2bfafe81ce41fb0eaf9ab604
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965782"
---
# <a name="field-separator-not-found-after-segment-tag-id"></a><span data-ttu-id="0940e-102">在段标记 id 后找不到字段分隔符</span><span class="sxs-lookup"><span data-stu-id="0940e-102">Field separator not found after segment tag id</span></span>
## <a name="details"></a><span data-ttu-id="0940e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0940e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="0940e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0940e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="0940e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0940e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="0940e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0940e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="0940e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="0940e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0940e-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0940e-108"> EDI</span></span> |
|    <span data-ttu-id="0940e-109">组件</span><span class="sxs-lookup"><span data-stu-id="0940e-109">Component</span></span>    |                                       <span data-ttu-id="0940e-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="0940e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="0940e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="0940e-111">Symbolic Name</span></span>  |                          <span data-ttu-id="0940e-112">X12SeFsNotFoundAfterTagIdDescription</span><span class="sxs-lookup"><span data-stu-id="0940e-112">X12SeFsNotFoundAfterTagIdDescription</span></span>                          |
|  <span data-ttu-id="0940e-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="0940e-113">Message Text</span></span>   |                     <span data-ttu-id="0940e-114">在段标记 id 后找不到字段分隔符</span><span class="sxs-lookup"><span data-stu-id="0940e-114">Field separator not found after segment tag id</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="0940e-115">解释</span><span class="sxs-lookup"><span data-stu-id="0940e-115">Explanation</span></span>  
 <span data-ttu-id="0940e-116">此错误/警告/信息事件表明接收管道无法处理交换，因为交换包含一个段，该段具有端标识符，但之后没有紧跟数据元素分隔符。</span><span class="sxs-lookup"><span data-stu-id="0940e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the interchange because the interchange contained a segment that had a segment identifier without a data element separator immediately following it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0940e-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="0940e-117">User Action</span></span>  
 <span data-ttu-id="0940e-118">若要解决此错误，请确保交换中的所有段标识符之后紧跟数据元素分隔符，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="0940e-118">To resolve this error, ensure that all segment identifiers in the interchange have data element separators immediately following them, and then have the interchange resent.</span></span>