---
title: 错误-常规本地序列化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericNativeSerialize
ms.assetid: 3728727d-7d99-432d-844e-c956cc4635e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbe7591c6d48c647d60daf232b591acbad50ae4b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530743"
---
# <a name="error---generic-native-serialization"></a><span data-ttu-id="75bd2-102">错误-常规本地序列化</span><span class="sxs-lookup"><span data-stu-id="75bd2-102">Error - Generic Native Serialization</span></span>
<span data-ttu-id="75bd2-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="75bd2-103">**Error Code**</span></span>  
  
 <span data-ttu-id="75bd2-104">btm1049</span><span class="sxs-lookup"><span data-stu-id="75bd2-104">btm1049</span></span>  
  
 <span data-ttu-id="75bd2-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="75bd2-105">**Explanation**</span></span>  
  
 <span data-ttu-id="75bd2-106">由于未指定错误的目标架构所指定的本机格式，无法转换由映射指定的转换生成的 XML 输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="75bd2-106">The XML output instance message produced by the transformation specified by the map could not be converted to the native format specified by the destination schema due to an unspecified error.</span></span>  
  
 <span data-ttu-id="75bd2-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="75bd2-107">**User Action**</span></span>  
  
 <span data-ttu-id="75bd2-108">在 BizTalk 编辑器中打开目标架构并使用**验证架构**，**验证实例**，并**生成实例**命令中，右键单击时可用在解决方案资源管理器，以找出问题的架构。</span><span class="sxs-lookup"><span data-stu-id="75bd2-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>