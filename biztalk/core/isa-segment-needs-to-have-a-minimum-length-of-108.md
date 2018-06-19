---
title: ISA 段需要具有最小长度为 108 |Microsoft 文档
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
ms.openlocfilehash: 5ecd5c6761c6dbcc59ad6353efa2772b9eecf387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22261893"
---
# <a name="isa-segment-needs-to-have-a-minimum-length-of-108"></a><span data-ttu-id="1a16c-102">ISA 段需要具有最小长度为 108</span><span class="sxs-lookup"><span data-stu-id="1a16c-102">ISA segment needs to have a minimum length of 108</span></span>
## <a name="details"></a><span data-ttu-id="1a16c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1a16c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a16c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1a16c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1a16c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1a16c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="1a16c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1a16c-106">Event ID</span></span>|-|  
|<span data-ttu-id="1a16c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="1a16c-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1a16c-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="1a16c-108"> EDI</span></span>|  
|<span data-ttu-id="1a16c-109">组件</span><span class="sxs-lookup"><span data-stu-id="1a16c-109">Component</span></span>|<span data-ttu-id="1a16c-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="1a16c-110">EDI Engine</span></span>|  
|<span data-ttu-id="1a16c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="1a16c-111">Symbolic Name</span></span>|<span data-ttu-id="1a16c-112">NseIsaSuffix1LFDescription</span><span class="sxs-lookup"><span data-stu-id="1a16c-112">NseIsaSuffix1LFDescription</span></span>|  
|<span data-ttu-id="1a16c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="1a16c-113">Message Text</span></span>|<span data-ttu-id="1a16c-114">ISA 段需要具有最小长度为 108、 实例具有 {0}</span><span class="sxs-lookup"><span data-stu-id="1a16c-114">ISA segment needs to have a minimum length of 108, instance has {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1a16c-115">解释</span><span class="sxs-lookup"><span data-stu-id="1a16c-115">Explanation</span></span>  
 <span data-ttu-id="1a16c-116">此错误/警告/信息事件指示接收管道不无法处理传入的交换，因为交换中的 ISA 段不符合到的位数由服务架构 (X12ServiceSchema 或EdifactServiceSchema BaseArtifacts.dll 中)。</span><span class="sxs-lookup"><span data-stu-id="1a16c-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the ISA segment in the interchange did not conform to the number of digits established by the service schema (X12ServiceSchema or the EdifactServiceSchema in BaseArtifacts.dll).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1a16c-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="1a16c-117">User Action</span></span>  
 <span data-ttu-id="1a16c-118">若要解决此错误，确保每个的 ISA 段 （ISA16 到 ISA01) 中的字段具有所需最少数字个数。</span><span class="sxs-lookup"><span data-stu-id="1a16c-118">To resolve this error, make sure that each of the fields in the ISA segment (from ISA01 to ISA16) has the required minimum number of digits.</span></span> <span data-ttu-id="1a16c-119">可以通过打开 BizTalk Server 管理控制台；打开“BizTalk 组”节点、“应用程序”节点、“BizTalk EDI 应用程序”节点，然后是架构节点；打开根节点为 ISA 的 Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema；然后单击“架构视图”来查看最小位数。</span><span class="sxs-lookup"><span data-stu-id="1a16c-119">You can see the minimum number of digits by opening the BizTalk Server Administration Console; opening the BizTalk Group node, the Applications node, the BizTalk EDI Application node, and then the schema node; opening the Microsoft.BizTalk.Edi.BaseArtifacts.X12ServiceSchema with the root node of ISA; and then clicking the Schema View.</span></span>