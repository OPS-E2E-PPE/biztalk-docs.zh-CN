---
title: 处理拆装器管道组件中的编码 |Microsoft Docs
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
ms.openlocfilehash: 596161cd2ccf5d4f9a492bbdd23cd8f6f22c5c2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995230"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a><span data-ttu-id="31f87-102">处理拆装器管道组件中的编码</span><span class="sxs-lookup"><span data-stu-id="31f87-102">Handling Encoding in a Disassembler Pipeline Component</span></span>
<span data-ttu-id="31f87-103">确保您的自定义拆装器组件采用如下格式之一对出站文档编码：</span><span class="sxs-lookup"><span data-stu-id="31f87-103">Ensure that your custom disassembler component encodes outbound documents in one of the following formats:</span></span>  
  
- <span data-ttu-id="31f87-104">UTF-8</span><span class="sxs-lookup"><span data-stu-id="31f87-104">UTF-8</span></span>  
  
- <span data-ttu-id="31f87-105">UTF-16</span><span class="sxs-lookup"><span data-stu-id="31f87-105">UTF-16</span></span>  
  
- <span data-ttu-id="31f87-106">UTF-32</span><span class="sxs-lookup"><span data-stu-id="31f87-106">UTF-32</span></span>  
  
- <span data-ttu-id="31f87-107">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="31f87-107">UTF-16LE</span></span>  
  
- <span data-ttu-id="31f87-108">UTF-16BE</span><span class="sxs-lookup"><span data-stu-id="31f87-108">UTF-16BE</span></span>  
  
  <span data-ttu-id="31f87-109">业务流程引擎可能无法处理采用其他编码格式的文档。</span><span class="sxs-lookup"><span data-stu-id="31f87-109">The orchestration engine may not be able to process documents with other encoding formats.</span></span>  
  
  <span data-ttu-id="31f87-110">.NET Framework 不支持 UTF-32LE 和 UTF-32BE；若要使用这些格式，您必须创建自定义编码实现。</span><span class="sxs-lookup"><span data-stu-id="31f87-110">UTF-32LE and UTF-32BE are not supported by the .NET Framework; to use these formats, you must create a custom encoding implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31f87-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="31f87-111">See Also</span></span>  
 [<span data-ttu-id="31f87-112">开发拆装管道组件</span><span class="sxs-lookup"><span data-stu-id="31f87-112">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)