---
title: 用例在平面文件架构中的处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f2b56d2-03fa-41e9-ae28-3275b404d4db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4103b9f133ffac16b967832325effefba04b5ab2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357601"
---
# <a name="case-handling-in-flat-file-schemas"></a><span data-ttu-id="e8746-102">在平面文件架构中处理的用例</span><span class="sxs-lookup"><span data-stu-id="e8746-102">Case Handling in Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="e8746-103">概述</span><span class="sxs-lookup"><span data-stu-id="e8746-103">Overview</span></span>
<span data-ttu-id="e8746-104">可以使用**用例**属性时要执行的平面文件数据的大小写转换消息翻译为其等效的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="e8746-104">You can use the **Case** property to perform case conversion of flat file data when being translated from its equivalent XML format.</span></span> <span data-ttu-id="e8746-105">当平面文件组装器将 XML 消息转换为其等效的平面文件格式，并**用例**属性设置为**所有字母都大写**或**小写**，所有数据受相应架构将转换为大写或小写，分别将在翻译过程。</span><span class="sxs-lookup"><span data-stu-id="e8746-105">When the flat file assembler translates an XML message into its equivalent flat file format, and the **Case** property is set to either **Uppercase** or **Lowercase**, all data governed by the corresponding schema will be converted to uppercase or lowercase, respectively, during the translation.</span></span>  
  
 <span data-ttu-id="e8746-106">当**用例**属性设置为 **（默认）**，不执行任何大小写转换。</span><span class="sxs-lookup"><span data-stu-id="e8746-106">When the **Case** property is set to **(Default)**, no case conversion is performed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8746-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8746-107">See Also</span></span>  
 <span data-ttu-id="e8746-108">**考虑事项时创建平面文件消息架构**和**用例 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="e8746-108">**Considerations When Creating Flat File Message Schemas** and **Case (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>