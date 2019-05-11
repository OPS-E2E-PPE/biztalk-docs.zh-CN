---
title: ISA 和 IEA 中的控制编号不匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f9091ea-460b-464b-acd5-8dc0488b61e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15f273ca2ddec143cbd7e72af6b3f06c8485fc17
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390240"
---
# <a name="control-number-in-isa-and-iea-do-not-match"></a><span data-ttu-id="06b4e-102">ISA 和 IEA 中的控件编号不匹配</span><span class="sxs-lookup"><span data-stu-id="06b4e-102">Control Number in ISA and IEA do not match</span></span>
## <a name="details"></a><span data-ttu-id="06b4e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="06b4e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="06b4e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="06b4e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="06b4e-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="06b4e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="06b4e-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="06b4e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="06b4e-107">事件源</span><span class="sxs-lookup"><span data-stu-id="06b4e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="06b4e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="06b4e-108">EDI</span></span> |
|    <span data-ttu-id="06b4e-109">组件</span><span class="sxs-lookup"><span data-stu-id="06b4e-109">Component</span></span>    |                                       <span data-ttu-id="06b4e-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="06b4e-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="06b4e-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="06b4e-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="06b4e-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="06b4e-112">Message Text</span></span>   |                       <span data-ttu-id="06b4e-113">ISA 和 IEA 中的控件编号不匹配</span><span class="sxs-lookup"><span data-stu-id="06b4e-113">Control Number in ISA and IEA do not match</span></span>                       |
  
## <a name="explanation"></a><span data-ttu-id="06b4e-114">解释</span><span class="sxs-lookup"><span data-stu-id="06b4e-114">Explanation</span></span>  
 <span data-ttu-id="06b4e-115">此错误/警告/信息事件表明 AS2 接收管道无法处理传入的交换，因为交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有不同的值。</span><span class="sxs-lookup"><span data-stu-id="06b4e-115">This Error/Warning/Information event indicates that the AS2 receive pipeline could not process the incoming interchange because the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange do not have the same value.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06b4e-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="06b4e-116">User Action</span></span>  
 <span data-ttu-id="06b4e-117">若要解决此错误，请确保交换的 ISA13 和 IEA02 字段中包含的交换控制编号具有相同的值，然后重新发送交换。</span><span class="sxs-lookup"><span data-stu-id="06b4e-117">To resolve this error, make sure that the interchange control numbers contained in the ISA13 and IEA02 fields of the interchange have the same value, and then have the interchange resent.</span></span>