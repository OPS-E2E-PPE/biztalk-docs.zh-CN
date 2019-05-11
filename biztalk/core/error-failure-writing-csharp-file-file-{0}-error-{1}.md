---
title: 错误-写入 CSharp 文件时出错 (&lt;file:---{0}&gt;)。 错误： {1} |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8342be9-b19e-4eb3-9da4-b1cb0fb54bd9
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0e417a96b148191cf349a393cc96671902059c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348284"
---
# <a name="error---failure-writing-csharp-file-ltfile---0gt-error-1"></a><span data-ttu-id="39116-103">错误-写入 CSharp 文件时出错 (&lt;file:---{0}&gt;)。</span><span class="sxs-lookup"><span data-stu-id="39116-103">Error - Failure writing CSharp file (&lt;file:---{0}&gt;).</span></span> <span data-ttu-id="39116-104">错误： {1}</span><span class="sxs-lookup"><span data-stu-id="39116-104">Error: {1}</span></span>
<span data-ttu-id="39116-105">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="39116-105">**Error Code**</span></span>  
  
 <span data-ttu-id="39116-106">btm1060</span><span class="sxs-lookup"><span data-stu-id="39116-106">btm1060</span></span>  
  
 <span data-ttu-id="39116-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="39116-107">**Explanation**</span></span>  
  
 <span data-ttu-id="39116-108">映射器编译器不能在生成任务指定的位置中创建 c# 文件时，会出现错误。</span><span class="sxs-lookup"><span data-stu-id="39116-108">Error occurs when mapper compiler is not able to create the csharp file in the location specified by the build task.</span></span>  
  
 <span data-ttu-id="39116-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="39116-109">**User Action**</span></span>  
  
 <span data-ttu-id="39116-110">检查包含在消息中的错误消息 (错误{1})。</span><span class="sxs-lookup"><span data-stu-id="39116-110">Check the error message included in the message (Error {1}).</span></span> <span data-ttu-id="39116-111">如果它是未经授权的异常，则可能不需要的项目输出文件夹的写入权限。</span><span class="sxs-lookup"><span data-stu-id="39116-111">If it is an UnAuthorised exception, then you may not have write permissions for the project output folder.</span></span>