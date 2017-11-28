---
title: "错误-编写 XML 类型 Blob 文件的故障 (&lt;file:---{0}&gt;)。 错误： {1} |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb787db4-0919-4e1b-bfe1-ba0e19a08881
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d76ff1a81045d3b764a6a26112a1efd74b284674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---failure-writing-xml-type-blob-file-ltfile---0gt-error-1"></a><span data-ttu-id="97d6d-103">错误-编写 XML 类型 Blob 文件的故障 (&lt;file:---{0}&gt;)。</span><span class="sxs-lookup"><span data-stu-id="97d6d-103">Error - Failure writing XML Type Blob file (&lt;file:---{0}&gt;).</span></span> <span data-ttu-id="97d6d-104">错误： {1}</span><span class="sxs-lookup"><span data-stu-id="97d6d-104">Error: {1}</span></span>
<span data-ttu-id="97d6d-105">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="97d6d-105">**Error Code**</span></span>  
  
 <span data-ttu-id="97d6d-106">btm1062</span><span class="sxs-lookup"><span data-stu-id="97d6d-106">btm1062</span></span>  
  
 <span data-ttu-id="97d6d-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="97d6d-107">**Explanation**</span></span>  
  
 <span data-ttu-id="97d6d-108">当映射器编译器不能在由生成任务指定的位置中创建的 xml blob 文件时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="97d6d-108">This occurs when mapper compiler is not able to create the xml blob file in the location specified by the build task.</span></span>  
  
 <span data-ttu-id="97d6d-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="97d6d-109">**User Action**</span></span>  
  
 <span data-ttu-id="97d6d-110">检查错误消息包含在消息 （错误 {1})i。</span><span class="sxs-lookup"><span data-stu-id="97d6d-110">Check the error message included in the message (Error {1})i.</span></span> <span data-ttu-id="97d6d-111">如果它是未经授权的异常，则您可能没有的项目输出文件夹的写权限。</span><span class="sxs-lookup"><span data-stu-id="97d6d-111">If it is an UnAuthorised exception, then you may not have write permission for the project output folder.</span></span>