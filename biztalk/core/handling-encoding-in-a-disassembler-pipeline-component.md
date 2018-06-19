---
title: 处理反汇编程序管道组件中编码 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcbfb8f86847668436fae04db7bee1703dfb60ad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246701"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a><span data-ttu-id="bb223-102">处理反汇编程序管道组件中编码</span><span class="sxs-lookup"><span data-stu-id="bb223-102">Handling Encoding in a Disassembler Pipeline Component</span></span>
<span data-ttu-id="bb223-103">确保您的自定义拆装器组件采用如下格式之一对出站文档编码：</span><span class="sxs-lookup"><span data-stu-id="bb223-103">Ensure that your custom disassembler component encodes outbound documents in one of the following formats:</span></span>  
  
-   <span data-ttu-id="bb223-104">UTF-8</span><span class="sxs-lookup"><span data-stu-id="bb223-104">UTF-8</span></span>  
  
-   <span data-ttu-id="bb223-105">UTF 16</span><span class="sxs-lookup"><span data-stu-id="bb223-105">UTF-16</span></span>  
  
-   <span data-ttu-id="bb223-106">UTF-32</span><span class="sxs-lookup"><span data-stu-id="bb223-106">UTF-32</span></span>  
  
-   <span data-ttu-id="bb223-107">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="bb223-107">UTF-16LE</span></span>  
  
-   <span data-ttu-id="bb223-108">UTF-16BE</span><span class="sxs-lookup"><span data-stu-id="bb223-108">UTF-16BE</span></span>  
  
 <span data-ttu-id="bb223-109">业务流程引擎可能无法处理采用其他编码格式的文档。</span><span class="sxs-lookup"><span data-stu-id="bb223-109">The orchestration engine may not be able to process documents with other encoding formats.</span></span>  
  
 <span data-ttu-id="bb223-110">.NET Framework 不支持 UTF-32LE 和 UTF-32BE；若要使用这些格式，您必须创建自定义编码实现。</span><span class="sxs-lookup"><span data-stu-id="bb223-110">UTF-32LE and UTF-32BE are not supported by the .NET Framework; to use these formats, you must create a custom encoding implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb223-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb223-111">See Also</span></span>  
 [<span data-ttu-id="bb223-112">开发分解的管道组件</span><span class="sxs-lookup"><span data-stu-id="bb223-112">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)