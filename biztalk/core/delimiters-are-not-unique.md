---
title: 分隔符不唯一 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c37cc55-8923-4124-9004-91ee5093df9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed635103026d71902ab9c1f93d1849fbeff3d1c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389675"
---
# <a name="delimiters-are-not-unique"></a><span data-ttu-id="7805a-102">分隔符不唯一</span><span class="sxs-lookup"><span data-stu-id="7805a-102">Delimiters are not unique</span></span>
## <a name="details"></a><span data-ttu-id="7805a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7805a-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="7805a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7805a-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="7805a-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7805a-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="7805a-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7805a-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="7805a-107">事件源</span><span class="sxs-lookup"><span data-stu-id="7805a-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7805a-108">EDI</span><span class="sxs-lookup"><span data-stu-id="7805a-108">EDI</span></span> |
|    <span data-ttu-id="7805a-109">组件</span><span class="sxs-lookup"><span data-stu-id="7805a-109">Component</span></span>    |                                       <span data-ttu-id="7805a-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="7805a-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="7805a-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="7805a-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="7805a-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="7805a-112">Message Text</span></span>   |                               <span data-ttu-id="7805a-113">分隔符不唯一</span><span class="sxs-lookup"><span data-stu-id="7805a-113">Delimiters are not unique</span></span>                                |
  
## <a name="explanation"></a><span data-ttu-id="7805a-114">解释</span><span class="sxs-lookup"><span data-stu-id="7805a-114">Explanation</span></span>  
 <span data-ttu-id="7805a-115">此错误/警告/信息事件表明 EDI 发送管道无法处理传出交换，因为交换中标识的两个或多个分隔符（用于分隔交换的多个方面）相同。</span><span class="sxs-lookup"><span data-stu-id="7805a-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because two or more of the separators identified in the interchange, and used to separate facets of the interchange, were the same.</span></span> <span data-ttu-id="7805a-116">这些分隔符是在 X12 交换的 ISA 分段以及 EDIFACT 交换的 UNA 分段中标识的。</span><span class="sxs-lookup"><span data-stu-id="7805a-116">The separators are identified in the ISA segment of an X12 interchange and in the UNA segment of an EDIFACT interchange.</span></span> <span data-ttu-id="7805a-117">保留的批方案中可能会发生两个或多个分隔符具有相同值的情况，或者如果交换通过直通传输接收，然后由发送端口选取作为 MessageBox 中的 XML 文件，也可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="7805a-117">Two or more separators with the same value can occur in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span> <span data-ttu-id="7805a-118">此错误将会导致处理交换失败。</span><span class="sxs-lookup"><span data-stu-id="7805a-118">This error condition will cause processing of the interchange to fail.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7805a-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="7805a-119">User Action</span></span>  
 <span data-ttu-id="7805a-120">若要解决此错误，请标识交换中具有相同值的分隔符，并更改其中一个分隔符的值。</span><span class="sxs-lookup"><span data-stu-id="7805a-120">To resolve this error, identify which separators in the interchange have the same value, and change the value of one of the separators.</span></span>