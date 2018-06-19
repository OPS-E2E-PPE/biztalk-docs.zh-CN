---
title: Edifact 交换 Xml 序列化失败，因为结构无效，没有 FunctionalGroup 或 ServiceSchema |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 530faadd-e301-4743-b4b3-b04ba7578f1d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79d64a9ec19e62f13220be056335bf2d249519a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241437"
---
# <a name="edifact-interchange-xml-serialization-failed-due-to-invalid-structure-no-functionalgroup-or-serviceschema"></a><span data-ttu-id="3b4c3-102">由于结构无效，没有 FunctionalGroup 或 ServiceSchema Edifact 交换 Xml 序列化失败</span><span class="sxs-lookup"><span data-stu-id="3b4c3-102">Edifact interchange Xml serialization failed due to invalid structure, no FunctionalGroup or ServiceSchema</span></span>
## <a name="details"></a><span data-ttu-id="3b4c3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3b4c3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b4c3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3b4c3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3b4c3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3b4c3-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3b4c3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3b4c3-106">Event ID</span></span>|-|  
|<span data-ttu-id="3b4c3-107">事件源</span><span class="sxs-lookup"><span data-stu-id="3b4c3-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3b4c3-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3b4c3-108"> EDI</span></span>|  
|<span data-ttu-id="3b4c3-109">组件</span><span class="sxs-lookup"><span data-stu-id="3b4c3-109">Component</span></span>|<span data-ttu-id="3b4c3-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="3b4c3-110">EDI Engine</span></span>|  
|<span data-ttu-id="3b4c3-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="3b4c3-111">Symbolic Name</span></span>|-|  
|<span data-ttu-id="3b4c3-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="3b4c3-112">Message Text</span></span>|<span data-ttu-id="3b4c3-113">由于结构无效，Edifact 交换 Xml 序列化失败。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-113">Edifact interchange Xml serialization failed due to invalid structure.</span></span> <span data-ttu-id="3b4c3-114">查找 UNZ 的 FunctionalGroup 或 ServiceSchema，但没有找到。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-114">Looking for FunctionalGroup or ServiceSchema for UNZ, but none found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3b4c3-115">解释</span><span class="sxs-lookup"><span data-stu-id="3b4c3-115">Explanation</span></span>  
 <span data-ttu-id="3b4c3-116">此错误/警告/信息事件表明发送管道无法处理保留的 EDIFACT 批处理交换，因为该交换的 XML 文件中不包含 TransactionSetGroup 或 FunctionalGroup 标记。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-116">This Error/Warning/Information event indicates that the send pipeline could not process an EDIFACT batched interchange that was preserved because the TransactionSetGroup or FunctionalGroup tags were not included in the interchange XML file.</span></span>  
  
 <span data-ttu-id="3b4c3-117">当 BizTalk 处理保留的批处理交换时，为该交换的 XML 文件中的一组事务集或组给出了 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-117">When BizTalk processes a batched interchange that is preserved, a group of transaction sets or a group of groups in the interchange's XML file are given an XML tag.</span></span> <span data-ttu-id="3b4c3-118">为一组组给出了 FunctionalGroup 标记。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-118">A group of groups is given the FunctionalGroup tag.</span></span> <span data-ttu-id="3b4c3-119">ServiceSchema 标志表明用于保留的批处理交换的控制架构。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-119">The ServiceSchema flag indicates the control schema used for the preserved-batch interchange.</span></span> <span data-ttu-id="3b4c3-120">如果您使用接收管道和直通传输发送管道设置保留的批处理，则可能会出现此错误条件。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-120">This error condition occurs if you set up a preserved batch using a receive pipeline and a passthrough transmit send pipeline.</span></span> <span data-ttu-id="3b4c3-121">这些标记是由接收管道设置的并且由发送管道删除。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-121">The tags are set by the receive pipeline and stripped out by the send pipeline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3b4c3-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="3b4c3-122">User Action</span></span>  
 <span data-ttu-id="3b4c3-123">若要解决此错误，请确保为保留的批处理生成的 XML 文件具有格式正确的 XML 结构，该机构具有 FunctionalGroup 标记（对于多个组）和/或 ServiceSchema 标记（对于用于保留的批处理交换的控制架构）。</span><span class="sxs-lookup"><span data-stu-id="3b4c3-123">To resolve this error, ensure that the XML file generated for the preserved batch has a well-formed XML structure with the FunctionalGroup tag (for multiple groups) and/or the ServiceSchema tag (for the control schema used for the preserved-batch interchange).</span></span>