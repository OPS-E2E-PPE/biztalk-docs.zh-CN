---
title: "基类型和通用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- base schemas
- schemas, common schemas
- schemas, base schemas
- common schemas
ms.assetid: 60eb24f6-cc4f-4c6d-ab15-9e3a6b4ed376
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ca51abfcdbfe965bc3da8deeb97f72df736903
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="base-and-common-schemas"></a><span data-ttu-id="3e595-102">基类型和通用架构</span><span class="sxs-lookup"><span data-stu-id="3e595-102">Base and Common Schemas</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="3e595-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]已实现的记录和所包含独立的架构中的单个消息架构的元素。</span><span class="sxs-lookup"><span data-stu-id="3e595-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] has implemented the records and elements that comprise individual message schemas in separate schemas.</span></span> <span data-ttu-id="3e595-104">此方法提供了一个位置来为字段和格式，使此类更改中的消息架构提供更新。</span><span class="sxs-lookup"><span data-stu-id="3e595-104">This approach provides a single location to provide updates for fields and formats, insulating the message schema from such changes.</span></span>  
  
 <span data-ttu-id="3e595-105">基础架构 (**SWIFT 基 Types.xsd**) 包含的消息架构引用通用记录和元素定义。</span><span class="sxs-lookup"><span data-stu-id="3e595-105">The base schema (**SWIFT Base Types.xsd**) contains the common record and element definitions that the message schemas reference.</span></span> <span data-ttu-id="3e595-106">通用记录和元素定义与 SWIFT FIN 消息字段相对应。</span><span class="sxs-lookup"><span data-stu-id="3e595-106">The common record and element definitions correspond to the SWIFT FIN message fields.</span></span> <span data-ttu-id="3e595-107">你需要将此架构添加到任何使用的消息架构的项目。</span><span class="sxs-lookup"><span data-stu-id="3e595-107">You need to add this schema to any project that uses the message schema.</span></span> <span data-ttu-id="3e595-108">基础架构介绍的规则和常用函数，并定义 A4SWIFT 使用来验证相应的消息实例的格式。</span><span class="sxs-lookup"><span data-stu-id="3e595-108">The base schema covers the rules and common functions, and defines the formats that A4SWIFT uses to validate the appropriate message instances.</span></span> <span data-ttu-id="3e595-109">SWIFT 基 Types.xsd 架构定义 XSD **simpleType**和 SWIFT 字段的复杂元素。</span><span class="sxs-lookup"><span data-stu-id="3e595-109">The SWIFT Base Types.xsd schema defines XSD **simpleType** and complex elements for SWIFT fields.</span></span> <span data-ttu-id="3e595-110">已定义 SWIFT **simpleType**元素的所有基字段，如量、 速率、 价格和等等，SWIFT 使用中的许多字段。</span><span class="sxs-lookup"><span data-stu-id="3e595-110">SWIFT has defined **simpleType** elements for all base fields, such as the Amount, Rate, Price, and so on, which SWIFT uses in many of the fields.</span></span> <span data-ttu-id="3e595-111">SWIFT 基 Types.xsd 架构还定义包括许多自定义的字段的 XSD 复杂元素**simpleTypes**架构中定义。</span><span class="sxs-lookup"><span data-stu-id="3e595-111">The SWIFT Base Types.xsd schema also defines XSD complex elements for fields that include many of the custom **simpleTypes** defined in the schema.</span></span> <span data-ttu-id="3e595-112">例如， **BankIdentifierCode**复杂元素使用银行代码、 国家/地区代码、 区号和分支代码。</span><span class="sxs-lookup"><span data-stu-id="3e595-112">For example, the **BankIdentifierCode** complex element uses Bank Code, Country Code, Area Code, and Branch Code.</span></span> <span data-ttu-id="3e595-113">用户可以添加新**simpleTypes**和镜像 SWIFT 字段，并可以修改现有类型的复杂元素。</span><span class="sxs-lookup"><span data-stu-id="3e595-113">Users can add new **simpleTypes** and complex elements that mirror SWIFT fields and can modify existing types.</span></span> <span data-ttu-id="3e595-114">你应注意，但是，当你修改现有类型，因为业务规则引擎 (BRE) 验证和 XML 验证功能都依赖于这些定义的类型。</span><span class="sxs-lookup"><span data-stu-id="3e595-114">You should take care, however, when you modify existing types, because the Business Rule Engine (BRE) Validation and XML Validation features are dependent upon these defined types.</span></span>  
  
 <span data-ttu-id="3e595-115">公用架构 (**SWIFT 常见数据 Types.xsd**) 基础架构中定义相应的字段的字符集。</span><span class="sxs-lookup"><span data-stu-id="3e595-115">The common schema (**SWIFT Common Data Types.xsd**) defines the character sets appropriate to the fields in the base schema.</span></span> <span data-ttu-id="3e595-116">SWIFT 定义中引用这些字符集*SWIFT 用户手册*。</span><span class="sxs-lookup"><span data-stu-id="3e595-116">SWIFT defines these character sets, as referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="3e595-117">你还需要将公用架构添加到架构项目。</span><span class="sxs-lookup"><span data-stu-id="3e595-117">You also need to add the common schema to your schema projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e595-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e595-118">See Also</span></span>  
 [<span data-ttu-id="3e595-119">使用架构</span><span class="sxs-lookup"><span data-stu-id="3e595-119">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)