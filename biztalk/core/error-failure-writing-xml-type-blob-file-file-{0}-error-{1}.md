---
title: 错误-写入 XML 类型 Blob 文件时出错 (&lt;file:---{0}&gt;)。 错误： {1} |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb787db4-0919-4e1b-bfe1-ba0e19a08881
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8917230d4209079ef6f581e2f747fc45aafc827
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388873"
---
# <a name="error---failure-writing-xml-type-blob-file-ltfile---0gt-error-1"></a><span data-ttu-id="de313-103">错误-写入 XML 类型 Blob 文件时出错 (&lt;file:---{0}&gt;)。</span><span class="sxs-lookup"><span data-stu-id="de313-103">Error - Failure writing XML Type Blob file (&lt;file:---{0}&gt;).</span></span> <span data-ttu-id="de313-104">错误： {1}</span><span class="sxs-lookup"><span data-stu-id="de313-104">Error: {1}</span></span>
<span data-ttu-id="de313-105">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="de313-105">**Error Code**</span></span>  
  
 <span data-ttu-id="de313-106">btm1062</span><span class="sxs-lookup"><span data-stu-id="de313-106">btm1062</span></span>  
  
 <span data-ttu-id="de313-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="de313-107">**Explanation**</span></span>  
  
 <span data-ttu-id="de313-108">当映射器编译器不能在生成任务指定的位置中创建的 xml blob 文件时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="de313-108">This occurs when mapper compiler is not able to create the xml blob file in the location specified by the build task.</span></span>  
  
 <span data-ttu-id="de313-109">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="de313-109">**User Action**</span></span>  
  
 <span data-ttu-id="de313-110">检查包含在消息中的错误消息 (错误{1}) 我。</span><span class="sxs-lookup"><span data-stu-id="de313-110">Check the error message included in the message (Error {1})i.</span></span> <span data-ttu-id="de313-111">如果它是未经授权的异常，则可能不需要的项目输出文件夹的写入权限。</span><span class="sxs-lookup"><span data-stu-id="de313-111">If it is an UnAuthorised exception, then you may not have write permission for the project output folder.</span></span>