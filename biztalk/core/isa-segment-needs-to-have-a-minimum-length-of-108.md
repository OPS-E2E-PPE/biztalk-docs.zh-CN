---
title: ISA 段需要具有最小长度为 108 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57641445-cebb-4219-998d-54038d7ddf19
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d511e0a50d610313bbe1c7ce4b3137c55ad0328
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329689"
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a><span data-ttu-id="e1af1-102">ISA 段需要具有最小长度为 108</span><span class="sxs-lookup"><span data-stu-id="e1af1-102">ISA segment needs to have a minimum length of 108</span></span>
## <a name="details"></a><span data-ttu-id="e1af1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e1af1-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="e1af1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e1af1-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="e1af1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e1af1-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="e1af1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e1af1-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="e1af1-107">事件源</span><span class="sxs-lookup"><span data-stu-id="e1af1-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e1af1-108">EDI</span><span class="sxs-lookup"><span data-stu-id="e1af1-108">EDI</span></span> |
|    <span data-ttu-id="e1af1-109">组件</span><span class="sxs-lookup"><span data-stu-id="e1af1-109">Component</span></span>    |                                       <span data-ttu-id="e1af1-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="e1af1-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="e1af1-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="e1af1-111">Symbolic Name</span></span>  |                               <span data-ttu-id="e1af1-112">NseIsaSuffix1LFDescription</span><span class="sxs-lookup"><span data-stu-id="e1af1-112">NseIsaSuffix1LFDescription</span></span>                               |
|  <span data-ttu-id="e1af1-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="e1af1-113">Message Text</span></span>   |          <span data-ttu-id="e1af1-114">ISA 段需要具有最小长度为 108，实际上是 {0}</span><span class="sxs-lookup"><span data-stu-id="e1af1-114">ISA segment needs to have a minimum length of 108, instance has {0}</span></span>           |
  
## <a name="explanation"></a><span data-ttu-id="e1af1-115">解释</span><span class="sxs-lookup"><span data-stu-id="e1af1-115">Explanation</span></span>  
 <span data-ttu-id="e1af1-116">此错误/警告/信息事件表明接收管道不无法处理传入的交换，因为交换中的 ISA 段不符合服务架构建立的位数 (X12ServiceSchema 或EdifactServiceSchema 在 BaseArtifacts.dll 中)。</span><span class="sxs-lookup"><span data-stu-id="e1af1-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the ISA segment in the interchange did not conform to the number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e1af1-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="e1af1-117">User Action</span></span>  
 <span data-ttu-id="e1af1-118">若要解决此错误，请确保每个字段 （从为 ISA16 ISA01) 的 ISA 段中具有所需的最小数字位数。</span><span class="sxs-lookup"><span data-stu-id="e1af1-118">To resolve this error, make sure that each of the fields in the ISA segment (from ISA01 to ISA16) has the required minimum number of digits.</span></span> <span data-ttu-id="e1af1-119">可以通过打开 BizTalk Server 管理控制台; 看到最小位数打开 BizTalk 组节点、 应用程序节点、 BizTalk EDI 应用程序节点，然后架构节点;使用 ISA; 的根节点打开 Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema然后单击架构视图。</span><span class="sxs-lookup"><span data-stu-id="e1af1-119">You can see the minimum number of digits by opening the BizTalk Server Administration Console; opening the BizTalk Group node, the Applications node, the BizTalk EDI Application node, and then the schema node; opening the Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema with the root node of ISA; and then clicking the Schema View.</span></span>