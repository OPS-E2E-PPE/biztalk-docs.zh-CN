---
title: 字段位置计算 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e315f09-f2c9-49cc-8d2f-0f4f2d48fd45
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160e28e23de6c792e3669831e84e582dd07c7318
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345593"
---
# <a name="field-position-calculation"></a><span data-ttu-id="a49f5-102">字段位置计算</span><span class="sxs-lookup"><span data-stu-id="a49f5-102">Field Position Calculation</span></span>

## <a name="overview"></a><span data-ttu-id="a49f5-103">概述</span><span class="sxs-lookup"><span data-stu-id="a49f5-103">Overview</span></span>
<span data-ttu-id="a49f5-104">当你使用**位置长度**和**位置偏移量**的属性**字段元素**并**字段属性**中的节点在架构定义平面文件消息，在位置记录的布局**启动位置**并**长度**的列**平面文件**选项卡中BizTalk 编辑器中的计算的起始位置和长度，分别显示的记录和相关字段。</span><span class="sxs-lookup"><span data-stu-id="a49f5-104">When you use the **Positional Length** and **Positional Offset** properties of the **Field Element** and **Field Attribute** nodes in your schema to define the layout of the positional records in your flat file message, the **Start Position** and **Length** columns of the **Flat File** tab in BizTalk Editor show the calculated starting positions and lengths, respectively, of the relevant fields and records.</span></span>  

> [!NOTE]
>  <span data-ttu-id="a49f5-105">**平面文件**选项卡时，会显示替代选项卡式视图与 XSD 视图在 BizTalk 编辑器中配置了平面文件扩展使用**架构编辑器扩展**属性**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="a49f5-105">The **Flat File** tab appear as an alternate tabbed view with the XSD view in BizTalk Editor when you have configured the flat file extension using the **Schema Editor Extensions** property of the **Schema** node.</span></span> <span data-ttu-id="a49f5-106">此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="a49f5-106">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

 <span data-ttu-id="a49f5-107">通常，特定字段的起始位置*N*是前一个字段的起始位置加上一个字段，再加上所用的字段指定的 （位置） 偏移量长度*N*.</span><span class="sxs-lookup"><span data-stu-id="a49f5-107">In general, the starting position of a particular field *N* is the starting position of the previous field, plus the length of the previous field, plus the (positional) offset you have specified for field *N*.</span></span>  

 <span data-ttu-id="a49f5-108">在 Microsoft 中的所有字段位置计算[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是，将自动执行，在动态，无需执行命令 （如已在以前版本的 BizTalk Server 所需）。</span><span class="sxs-lookup"><span data-stu-id="a49f5-108">All field position calculation in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is performed automatically, on-the-fly, without any need to execute a command (as was required in previous versions of BizTalk Server).</span></span>  

## <a name="see-also"></a><span data-ttu-id="a49f5-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a49f5-109">See Also</span></span>  
- [<span data-ttu-id="a49f5-110">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="a49f5-110">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
- <span data-ttu-id="a49f5-111">**位置长度 （平面文件架构的节点属性）** 和**位置偏移量 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a49f5-111">**Positional Length (Node Property of Flat File Schemas)** and **Positional Offset (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
