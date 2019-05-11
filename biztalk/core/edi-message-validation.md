---
title: EDI 消息验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09ee189ccd827c72fd177d65eaa49461e2287538
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350351"
---
# <a name="edi-message-validation"></a><span data-ttu-id="463d8-102">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="463d8-102">EDI Message Validation</span></span>
<span data-ttu-id="463d8-103">EDI 数据作为带分隔符的文件传输 （不带自描述标签） 并因此编码规则强制执行严格的格式设置规则，以确保目标应用程序应能够成功地分析和使用进行下游处理的信息。</span><span class="sxs-lookup"><span data-stu-id="463d8-103">EDI data is transmitted as delimited files (without self describing tags) and therefore the encoding rules enforce strict formatting rules to ensure the destination application is able to successfully parse and consume the information for downstream processing.</span></span>  
  
 <span data-ttu-id="463d8-104">EDI 接收管道和 EDI 发送管道中 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 执行一系列验证。</span><span class="sxs-lookup"><span data-stu-id="463d8-104">The EDI receive pipeline and EDI send pipeline in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 perform a series of validations.</span></span> <span data-ttu-id="463d8-105">始终执行一些;如果协议中启用属性，或者在架构中执行其他人。</span><span class="sxs-lookup"><span data-stu-id="463d8-105">Some are always performed; others are performed if enabled in agreement properties or in the schema.</span></span> <span data-ttu-id="463d8-106">有关如何配置验证的详细信息，请参阅[如何验证 EDI 交换是配置的](../core/how-validation-of-an-edi-interchange-is-configured.md)。</span><span class="sxs-lookup"><span data-stu-id="463d8-106">For more information about how validation is configured, see [How Validation of an EDI Interchange Is Configured](../core/how-validation-of-an-edi-interchange-is-configured.md).</span></span>  
  
 <span data-ttu-id="463d8-107">对 EDI 交换的验证涉及几种不同的验证，如以下主题中所述。</span><span class="sxs-lookup"><span data-stu-id="463d8-107">Validation of an EDI interchange involves several different kinds of validation, as described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="463d8-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="463d8-108">In This Section</span></span>  
  
-   [<span data-ttu-id="463d8-109">如何配置对 EDI 交换的验证</span><span class="sxs-lookup"><span data-stu-id="463d8-109">How Validation of an EDI Interchange Is Configured</span></span>](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [<span data-ttu-id="463d8-110">EDI 结构验证</span><span class="sxs-lookup"><span data-stu-id="463d8-110">EDI Structural Validation</span></span>](../core/edi-structural-validation.md)  
  
-   [<span data-ttu-id="463d8-111">协议属性验证</span><span class="sxs-lookup"><span data-stu-id="463d8-111">Agreement Properties Validation</span></span>](../core/agreement-properties-validation.md)  
  
-   [<span data-ttu-id="463d8-112">EDI 类型（数据元素）验证</span><span class="sxs-lookup"><span data-stu-id="463d8-112">EDI Type (Data Element) Validation</span></span>](../core/edi-type-data-element-validation.md)  
  
-   [<span data-ttu-id="463d8-113">扩展 (BTS-XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="463d8-113">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)  
  
-   [<span data-ttu-id="463d8-114">架构验证</span><span class="sxs-lookup"><span data-stu-id="463d8-114">Schema Validation</span></span>](../core/schema-validation2.md)  
  
-   [<span data-ttu-id="463d8-115">跨字段-段验证</span><span class="sxs-lookup"><span data-stu-id="463d8-115">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)