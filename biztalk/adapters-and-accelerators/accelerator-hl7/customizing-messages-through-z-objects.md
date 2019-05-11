---
title: 自定义消息通过 Z 对象 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, Z objects
- customizing, messages
- Z objects, customizing messages
- customizing, Z objects
- messages, customizing
ms.assetid: 5bf514f8-d270-42d9-80fa-f10a6f6a20ad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ab08d367e28fdde77e19bccd777d27ceb5e0315
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255543"
---
# <a name="customizing-messages-through-z-objects"></a><span data-ttu-id="23e63-102">通过 Z 对象自定义消息</span><span class="sxs-lookup"><span data-stu-id="23e63-102">Customizing Messages through Z Objects</span></span>
<span data-ttu-id="23e63-103">请务必识别，因为 HL7 可能很全面，它不能解决所有接口伙伴的每个集合的特定要求。</span><span class="sxs-lookup"><span data-stu-id="23e63-103">It is important to recognize that, as comprehensive as HL7 may be, it does not address all the particular requirements of every set of interface partners.</span></span> <span data-ttu-id="23e63-104">将在其中的应用程序特定的数据要求超出数据 HL7 提供的定义的时间。</span><span class="sxs-lookup"><span data-stu-id="23e63-104">There will be times in which the specific data requirements of an application go beyond the data definitions that HL7 provides.</span></span> <span data-ttu-id="23e63-105">HL7 提供了接口开发人员可以使用他们的数据需要超出标准时的方法。</span><span class="sxs-lookup"><span data-stu-id="23e63-105">HL7 has provided methods that interface developers can use when their data needs go beyond the standard.</span></span> <span data-ttu-id="23e63-106">遗憾的是，也有的时间在其中 HL7 接口的实现程序执行未完全掌握的标准版、 内容和任一滥用预先存在的内容或只需将新材料添加到现有段。</span><span class="sxs-lookup"><span data-stu-id="23e63-106">Unfortunately, there are also times in which the implementers of HL7 interfaces do not fully grasp the contents of the standard, and either misuse pre-existing content or simply add new material to existing segments.</span></span>  
  
 <span data-ttu-id="23e63-107">HL7 标准调用支持自定义 （或本地化）"Z 对象"，因为其名称以字母"Z"开头。</span><span class="sxs-lookup"><span data-stu-id="23e63-107">HL7 standards call the supported customization (or localizations) "Z objects", because their names begin with the letter "Z".</span></span> <span data-ttu-id="23e63-108">可以对 HL7 消息执行两种类型的自定义： 声明和未声明。</span><span class="sxs-lookup"><span data-stu-id="23e63-108">You can perform two types of customizations on HL7 messages: declared and undeclared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23e63-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="23e63-109">In This Section</span></span>  
  
-   [<span data-ttu-id="23e63-110">已声明的自定义</span><span class="sxs-lookup"><span data-stu-id="23e63-110">Declared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)  
  
-   [<span data-ttu-id="23e63-111">未声明的自定义</span><span class="sxs-lookup"><span data-stu-id="23e63-111">Undeclared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)