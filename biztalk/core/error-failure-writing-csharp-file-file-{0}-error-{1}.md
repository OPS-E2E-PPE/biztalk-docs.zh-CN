---
title: "错误-未能写入 CSharp 文件 (&lt;file:---{0}&gt;)。 错误： {1} |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8342be9-b19e-4eb3-9da4-b1cb0fb54bd9
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9609b1a7fcc5340312a10344daec8102011725e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---failure-writing-csharp-file-ltfile---0gt-error-1"></a><span data-ttu-id="f282c-103">错误-未能写入 CSharp 文件 (&lt;file:---{0}&gt;)。</span><span class="sxs-lookup"><span data-stu-id="f282c-103">Error - Failure writing CSharp file (&lt;file:---{0}&gt;).</span></span> <span data-ttu-id="f282c-104">错误： {1}</span><span class="sxs-lookup"><span data-stu-id="f282c-104">Error: {1}</span></span>
<span data-ttu-id="f282c-105">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="f282c-105">**Error Code**</span></span>  
  
 <span data-ttu-id="f282c-106">btm1060</span><span class="sxs-lookup"><span data-stu-id="f282c-106">btm1060</span></span>  
  
 <span data-ttu-id="f282c-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="f282c-107">**Explanation**</span></span>  
  
 <span data-ttu-id="f282c-108">映射器编译器不能在由生成任务指定的位置中创建 csharp 文件时发生错误。</span><span class="sxs-lookup"><span data-stu-id="f282c-108">Error occurs when mapper compiler is not able to create the csharp file in the location specified by the build task.</span></span>  
  
 <span data-ttu-id="f282c-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="f282c-109">**User Action**</span></span>  
  
 <span data-ttu-id="f282c-110">检查错误消息包含在消息 (错误 {1})。</span><span class="sxs-lookup"><span data-stu-id="f282c-110">Check the error message included in the message (Error {1}).</span></span> <span data-ttu-id="f282c-111">如果它是未经授权的异常，则您可能不具有对项目输出文件夹的写权限。</span><span class="sxs-lookup"><span data-stu-id="f282c-111">If it is an UnAuthorised exception, then you may not have write permissions for the project output folder.</span></span>