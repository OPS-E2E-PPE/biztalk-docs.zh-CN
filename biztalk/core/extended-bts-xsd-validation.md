---
title: 扩展 (BTS-XSD) 验证 |Microsoft Docs
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
ms.openlocfilehash: 65f102e1d5a182b729af164a83efa8f20be49ba7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345923"
---
# <a name="extended-bts-xsd-validation"></a><span data-ttu-id="aa8ce-102">扩展 (BTS-XSD) 验证</span><span class="sxs-lookup"><span data-stu-id="aa8ce-102">Extended (BTS-XSD) Validation</span></span>
<span data-ttu-id="aa8ce-103">EDI 接收管道和 EDI 发送管道执行扩展的验证，仅当已使用其数据类型不是 EDI 数据类型的元素自定义架构。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-103">The EDI receive pipeline and EDI send pipeline perform extended validation only if the schema has been customized with elements whose data type is not an EDI data type.</span></span> <span data-ttu-id="aa8ce-104">不会通过 EDI 验证，以便将受扩展验证来验证这些添加的元素。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-104">These added elements would not be validated by EDI validation, so will be covered by extended validation.</span></span> <span data-ttu-id="aa8ce-105">扩展验证使用`System.Xml.XmlValidatingReader`并且包括可以在标准 XSD 中定义的所有检查。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-105">Extended validation uses `System.Xml.XmlValidatingReader` and includes all checks that can be defined in a standard XSD.</span></span>  
  
 <span data-ttu-id="aa8ce-106">配置扩展的验证到或从参与方的所有消息。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-106">You configure extended validation for all messages to or from a party.</span></span> <span data-ttu-id="aa8ce-107">为此，选择**扩展验证**中的复选框**验证**页 (在**事务集设置**对于 X12 或 EDIFACT 的部分)，请在在单向协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-107">You do so by selecting the **Extended Validation** checkbox in the **Validation** page (under the **Transaction Set Settings** section for either X12 or EDIFACT), on the one-way agreement tab in the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="aa8ce-108">您可以启用扩展验证而不启用 EDI 验证，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-108">You can enable extension validation without enabling EDI validation, or vice versa.</span></span>  
  
 <span data-ttu-id="aa8ce-109">扩展的验证包括以下检查：</span><span class="sxs-lookup"><span data-stu-id="aa8ce-109">Extended validation consists of the following checks:</span></span>  
  
-   <span data-ttu-id="aa8ce-110">数据元素要求和允许的重复</span><span class="sxs-lookup"><span data-stu-id="aa8ce-110">Data element requirement and allowed repetition</span></span>  
  
-   <span data-ttu-id="aa8ce-111">枚举</span><span class="sxs-lookup"><span data-stu-id="aa8ce-111">Enumerations</span></span>  
  
-   <span data-ttu-id="aa8ce-112">数据元素长度验证 （最小/最大）。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-112">Data element length validation (min/max).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aa8ce-113">不支持在 EDI 发送端的批处理消息的扩展的验证。</span><span class="sxs-lookup"><span data-stu-id="aa8ce-113">Extended Validation for batched messages on the EDI send side is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8ce-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa8ce-114">See Also</span></span>  
 [<span data-ttu-id="aa8ce-115">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="aa8ce-115">EDI Message Validation</span></span>](../core/edi-message-validation.md)