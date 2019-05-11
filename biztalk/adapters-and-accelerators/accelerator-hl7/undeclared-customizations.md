---
title: 未声明的自定义设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5d31c7803eaa8fe0f8afeb6ed7c534f70233db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286418"
---
# <a name="undeclared-customizations"></a><span data-ttu-id="0501f-102">未声明的自定义项</span><span class="sxs-lookup"><span data-stu-id="0501f-102">Undeclared Customizations</span></span>
<span data-ttu-id="0501f-103">而无需定义的格式或数据的性质，可以将数据添加到一条消息。</span><span class="sxs-lookup"><span data-stu-id="0501f-103">You can add data to a message without defining the format or nature of the data.</span></span> <span data-ttu-id="0501f-104">您使用未声明的 Z 段执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0501f-104">You do so by using undeclared Z segments.</span></span> <span data-ttu-id="0501f-105">未声明的 Z 段是一条消息末尾的意外的实例。</span><span class="sxs-lookup"><span data-stu-id="0501f-105">Undeclared Z segments are unexpected instances at the end of a message.</span></span> <span data-ttu-id="0501f-106">分析器/XML 验证器不会验证段。</span><span class="sxs-lookup"><span data-stu-id="0501f-106">The parser/XML validator does not validate the segment.</span></span> <span data-ttu-id="0501f-107">它不由任何架构定义。</span><span class="sxs-lookup"><span data-stu-id="0501f-107">It is not defined by any schema.</span></span> <span data-ttu-id="0501f-108">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将视为二进制大型对象 (BLOB) 的段。</span><span class="sxs-lookup"><span data-stu-id="0501f-108">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) treats the segment as a binary large object (BLOB).</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] <span data-ttu-id="0501f-109">将未声明的 Z 段数据，通过传递作为三部分组成的消息的第三个部分。</span><span class="sxs-lookup"><span data-stu-id="0501f-109">passes undeclared Z segment data through as the third part of a three-part message.</span></span> <span data-ttu-id="0501f-110">三个部分是标头、 正文和未声明的 Z 段，也称为 Z 一部分。</span><span class="sxs-lookup"><span data-stu-id="0501f-110">The three parts are the header, the body, and the undeclared Z segment, also called the Z part.</span></span> <span data-ttu-id="0501f-111">以字母"Z"，例如，"ZPD"自定义患者的人口统计信息的信息，开头的段 ID 标识的 Z 部分。</span><span class="sxs-lookup"><span data-stu-id="0501f-111">A segment ID beginning with the letter "Z", for instance, "ZPD" for custom patient demographics information, identifies the Z part.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0501f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0501f-112">See Also</span></span>  
 <span data-ttu-id="0501f-113">[声明自定义项](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span><span class="sxs-lookup"><span data-stu-id="0501f-113">[Declared Customizations](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md) </span></span>  
 <span data-ttu-id="0501f-114">[使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="0501f-114">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="0501f-115">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0501f-115">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="0501f-116">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="0501f-116">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="0501f-117">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="0501f-117">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)