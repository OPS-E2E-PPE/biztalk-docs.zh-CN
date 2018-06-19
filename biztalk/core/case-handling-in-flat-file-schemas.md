---
title: 种情况下，平面文件架构中的处理 |Microsoft 文档
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
ms.openlocfilehash: 2312f00a6dab18fa92c0fed05c5c9fa182d500f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231133"
---
# <a name="case-handling-in-flat-file-schemas"></a><span data-ttu-id="9db01-102">在平面文件架构中处理的用例</span><span class="sxs-lookup"><span data-stu-id="9db01-102">Case Handling in Flat File Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="9db01-103">概述</span><span class="sxs-lookup"><span data-stu-id="9db01-103">Overview</span></span>
<span data-ttu-id="9db01-104">你可以使用**用例**属性时要执行的平面文件数据的大小写转换要进行转换从其等效的 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="9db01-104">You can use the **Case** property to perform case conversion of flat file data when being translated from its equivalent XML format.</span></span> <span data-ttu-id="9db01-105">当的平面文件汇编转换成其等效的平面文件格式，一条 XML 消息时与**用例**属性设置为**所有字母都大写**或**小写**，所有数据受相应架构将转换为大写或小写，分别转换的过程中。</span><span class="sxs-lookup"><span data-stu-id="9db01-105">When the flat file assembler translates an XML message into its equivalent flat file format, and the **Case** property is set to either **Uppercase** or **Lowercase**, all data governed by the corresponding schema will be converted to uppercase or lowercase, respectively, during the translation.</span></span>  
  
 <span data-ttu-id="9db01-106">当**用例**属性设置为 **（默认）**，不执行任何大小写转换。</span><span class="sxs-lookup"><span data-stu-id="9db01-106">When the **Case** property is set to **(Default)**, no case conversion is performed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db01-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9db01-107">See Also</span></span>  
 <span data-ttu-id="9db01-108">**注意事项时创建平面文件消息架构**和**用例 （的平面文件架构的节点属性）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9db01-108">**Considerations When Creating Flat File Message Schemas** and **Case (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>