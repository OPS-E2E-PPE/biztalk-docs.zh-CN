---
title: "自定义消息通过 Z 对象 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, Z objects
- customizing, messages
- Z objects, customizing messages
- customizing, Z objects
- messages, customizing
ms.assetid: 5bf514f8-d270-42d9-80fa-f10a6f6a20ad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e01e5f106c690d506364dd2040702cdad0c3adcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-messages-through-z-objects"></a><span data-ttu-id="0c5c1-102">自定义消息通过 Z 对象</span><span class="sxs-lookup"><span data-stu-id="0c5c1-102">Customizing Messages through Z Objects</span></span>
<span data-ttu-id="0c5c1-103">请务必识别，因为在 HL7 可能是尽可能全面，它不能解决接口合作伙伴的每个集的所有特定的要求。</span><span class="sxs-lookup"><span data-stu-id="0c5c1-103">It is important to recognize that, as comprehensive as HL7 may be, it does not address all the particular requirements of every set of interface partners.</span></span> <span data-ttu-id="0c5c1-104">将在其中应用程序的特定数据要求超出数据 HL7 提供的定义的时间。</span><span class="sxs-lookup"><span data-stu-id="0c5c1-104">There will be times in which the specific data requirements of an application go beyond the data definitions that HL7 provides.</span></span> <span data-ttu-id="0c5c1-105">HL7 具有提供的接口开发人员可以使用时其数据需要超出标准的方法。</span><span class="sxs-lookup"><span data-stu-id="0c5c1-105">HL7 has provided methods that interface developers can use when their data needs go beyond the standard.</span></span> <span data-ttu-id="0c5c1-106">遗憾的是，也有的时间顺序 HL7 接口的实施者执行不完全抓住该标准中，内容和任一滥用预先存在的内容或只需将新材料添加到现有的网段。</span><span class="sxs-lookup"><span data-stu-id="0c5c1-106">Unfortunately, there are also times in which the implementers of HL7 interfaces do not fully grasp the contents of the standard, and either misuse pre-existing content or simply add new material to existing segments.</span></span>  
  
 <span data-ttu-id="0c5c1-107">HL7 标准调用支持自定义项 （或本地化信息）"Z 对象"，因为其名称以字母"Z"开头。</span><span class="sxs-lookup"><span data-stu-id="0c5c1-107">HL7 standards call the supported customization (or localizations) "Z objects", because their names begin with the letter "Z".</span></span> <span data-ttu-id="0c5c1-108">你可以对 HL7 消息执行两种类型的自定义项： 声明和未声明。</span><span class="sxs-lookup"><span data-stu-id="0c5c1-108">You can perform two types of customizations on HL7 messages: declared and undeclared.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c5c1-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="0c5c1-109">In This Section</span></span>  
  
-   [<span data-ttu-id="0c5c1-110">声明的自定义项</span><span class="sxs-lookup"><span data-stu-id="0c5c1-110">Declared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)  
  
-   [<span data-ttu-id="0c5c1-111">未声明的自定义项</span><span class="sxs-lookup"><span data-stu-id="0c5c1-111">Undeclared Customizations</span></span>](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)