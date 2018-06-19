---
title: 扩展 (BTS XSD) 验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed147515b48a23c55e552710d6a76d6df981edd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245949"
---
# <a name="extended-bts-xsd-validation"></a><span data-ttu-id="a90ff-102">扩展 (BTS-XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="a90ff-102">Extended (BTS-XSD) Validation</span></span>
<span data-ttu-id="a90ff-103">仅当在使用其数据类型不为 EDI 数据类型的元素对架构进行了自定义的情况下，EDI 接收管道和 EDI 发送管道才会执行扩展验证。</span><span class="sxs-lookup"><span data-stu-id="a90ff-103">The EDI receive pipeline and EDI send pipeline perform extended validation only if the schema has been customized with elements whose data type is not an EDI data type.</span></span> <span data-ttu-id="a90ff-104">EDI 验证，以便将受扩展验证将不验证这些添加的元素。</span><span class="sxs-lookup"><span data-stu-id="a90ff-104">These added elements would not be validated by EDI validation, so will be covered by extended validation.</span></span> <span data-ttu-id="a90ff-105">扩展验证使用 `System.Xml.XmlValidatingReader` 并且包括可以在标准 XSD 中定义的所有检查。</span><span class="sxs-lookup"><span data-stu-id="a90ff-105">Extended validation uses `System.Xml.XmlValidatingReader` and includes all checks that can be defined in a standard XSD.</span></span>  
  
 <span data-ttu-id="a90ff-106">可以为发送到参与方或从参与方接收的所有消息配置扩展验证。</span><span class="sxs-lookup"><span data-stu-id="a90ff-106">You configure extended validation for all messages to or from a party.</span></span> <span data-ttu-id="a90ff-107">这样做通过选择**扩展验证**中的复选框**验证**页 (下**事务设置设置**X12 或 EDIFACT 部分)，请在中的单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="a90ff-107">You do so by selecting the **Extended Validation** checkbox in the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT), on the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="a90ff-108">可以在不启用 EDI 验证的情况下启用扩展验证，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="a90ff-108">You can enable extension validation without enabling EDI validation, or vice versa.</span></span>  
  
 <span data-ttu-id="a90ff-109">扩展验证包括以下检查：</span><span class="sxs-lookup"><span data-stu-id="a90ff-109">Extended validation consists of the following checks:</span></span>  
  
-   <span data-ttu-id="a90ff-110">数据元素要求和允许的重复</span><span class="sxs-lookup"><span data-stu-id="a90ff-110">Data element requirement and allowed repetition</span></span>  
  
-   <span data-ttu-id="a90ff-111">枚举</span><span class="sxs-lookup"><span data-stu-id="a90ff-111">Enumerations</span></span>  
  
-   <span data-ttu-id="a90ff-112">数据元素长度验证（最小/最大）。</span><span class="sxs-lookup"><span data-stu-id="a90ff-112">Data element length validation (min/max).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a90ff-113">不支持对 EDI 发送端的批处理消息进行扩展式验证。</span><span class="sxs-lookup"><span data-stu-id="a90ff-113">Extended Validation for batched messages on the EDI send side is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90ff-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a90ff-114">See Also</span></span>  
 [<span data-ttu-id="a90ff-115">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="a90ff-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)