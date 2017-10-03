---
title: "EDI 消息验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71f34561-d280-48bb-b1dd-ce37b87c5023
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21439969bc8e23b5b9901077c14a98128aa64c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-message-validation"></a><span data-ttu-id="94a42-102">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="94a42-102">EDI Message Validation</span></span>
<span data-ttu-id="94a42-103">EDI 数据是作为带分隔符的文件（没有自描述标签）进行传输的，因此编码规则会施加严格的格式规则以确保目标应用程序可以成功地分析和使用信息以进行下游处理。</span><span class="sxs-lookup"><span data-stu-id="94a42-103">EDI data is transmitted as delimited files (without self describing tags) and therefore the encoding rules enforce strict formatting rules to ensure the destination application is able to successfully parse and consume the information for downstream processing.</span></span>  
  
 <span data-ttu-id="94a42-104">EDI 接收管道和 EDI 发送管道中 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 执行一系列的验证。</span><span class="sxs-lookup"><span data-stu-id="94a42-104">The EDI receive pipeline and EDI send pipeline in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI and AS2 perform a series of validations.</span></span> <span data-ttu-id="94a42-105">一些始终执行;如果启用协议中的属性或架构中执行其他人。</span><span class="sxs-lookup"><span data-stu-id="94a42-105">Some are always performed; others are performed if enabled in agreement properties or in the schema.</span></span> <span data-ttu-id="94a42-106">有关如何配置验证的详细信息，请参阅[如何验证 EDI 交换是配置的](../core/how-validation-of-an-edi-interchange-is-configured.md)。</span><span class="sxs-lookup"><span data-stu-id="94a42-106">For more information about how validation is configured, see [How Validation of an EDI Interchange Is Configured](../core/how-validation-of-an-edi-interchange-is-configured.md).</span></span>  
  
 <span data-ttu-id="94a42-107">如以下主题中所述，EDI 交换的验证工作涉及几种不同类型的验证。</span><span class="sxs-lookup"><span data-stu-id="94a42-107">Validation of an EDI interchange involves several different kinds of validation, as described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="94a42-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="94a42-108">In This Section</span></span>  
  
-   [<span data-ttu-id="94a42-109">如何配置 EDI 交换的验证</span><span class="sxs-lookup"><span data-stu-id="94a42-109">How Validation of an EDI Interchange Is Configured</span></span>](../core/how-validation-of-an-edi-interchange-is-configured.md)  
  
-   [<span data-ttu-id="94a42-110">EDI 结构验证</span><span class="sxs-lookup"><span data-stu-id="94a42-110">EDI Structural Validation</span></span>](../core/edi-structural-validation.md)  
  
-   [<span data-ttu-id="94a42-111">协议属性验证</span><span class="sxs-lookup"><span data-stu-id="94a42-111">Agreement Properties Validation</span></span>](../core/agreement-properties-validation.md)  
  
-   [<span data-ttu-id="94a42-112">EDI 类型 （数据元素） 验证</span><span class="sxs-lookup"><span data-stu-id="94a42-112">EDI Type (Data Element) Validation</span></span>](../core/edi-type-data-element-validation.md)  
  
-   [<span data-ttu-id="94a42-113">扩展 (BTS-XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="94a42-113">Extended (BTS-XSD) Validation</span></span>](../core/extended-bts-xsd-validation.md)  
  
-   [<span data-ttu-id="94a42-114">架构验证</span><span class="sxs-lookup"><span data-stu-id="94a42-114">Schema Validation</span></span>](../core/schema-validation2.md)  
  
-   [<span data-ttu-id="94a42-115">交叉字段段验证</span><span class="sxs-lookup"><span data-stu-id="94a42-115">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)