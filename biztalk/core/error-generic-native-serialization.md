---
title: "错误-泛型的本机序列化 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.genericNativeSerialize
ms.assetid: 3728727d-7d99-432d-844e-c956cc4635e4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d2eacfae17d72dbb17786a1d924cfdf14be20ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-native-serialization"></a><span data-ttu-id="7877d-102">错误-泛型的本机序列化</span><span class="sxs-lookup"><span data-stu-id="7877d-102">Error - Generic Native Serialization</span></span>
<span data-ttu-id="7877d-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="7877d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="7877d-104">btm1049</span><span class="sxs-lookup"><span data-stu-id="7877d-104">btm1049</span></span>  
  
 <span data-ttu-id="7877d-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="7877d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="7877d-106">由映射指定的转换所生成的 XML 输出实例消息无法转换为目标架构所指定的本地格式，具体错误并未指明。</span><span class="sxs-lookup"><span data-stu-id="7877d-106">The XML output instance message produced by the transformation specified by the map could not be converted to the native format specified by the destination schema due to an unspecified error.</span></span>  
  
 <span data-ttu-id="7877d-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="7877d-107">**User Action**</span></span>  
  
 <span data-ttu-id="7877d-108">在 BizTalk 编辑器中打开目标架构，并使用**验证架构**，**验证实例**，和**生成实例**命令中，右键单击时可用在解决方案资源管理器，以找出问题的架构。</span><span class="sxs-lookup"><span data-stu-id="7877d-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>