---
title: 错误-一般性本地解析 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericNativeParsing
ms.assetid: a28a4c0f-b69b-448b-b305-3b06b4f061e4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 383c3198af290552715d51812f22c82760cb445f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-native-parsing"></a><span data-ttu-id="ae9f5-102">错误-一般性本地解析</span><span class="sxs-lookup"><span data-stu-id="ae9f5-102">Error - Generic Native Parsing</span></span>
<span data-ttu-id="ae9f5-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="ae9f5-103">**Error Code**</span></span>  
  
 <span data-ttu-id="ae9f5-104">btm1042</span><span class="sxs-lookup"><span data-stu-id="ae9f5-104">btm1042</span></span>  
  
 <span data-ttu-id="ae9f5-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="ae9f5-105">**Explanation**</span></span>  
  
 <span data-ttu-id="ae9f5-106">测试映射操作为指定的本机的输入的实例消息文件无法分析和生成泛型分析错误。</span><span class="sxs-lookup"><span data-stu-id="ae9f5-106">The native input instance message file specified for the Test Map operation could not be parsed, and generated a generic fatal parsing error.</span></span>  
  
 <span data-ttu-id="ae9f5-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="ae9f5-107">**User Action**</span></span>  
  
 <span data-ttu-id="ae9f5-108">根据需要，正确源架构将与代码图或本机的输入的实例消息中指定的文件，或两者都关联。</span><span class="sxs-lookup"><span data-stu-id="ae9f5-108">As appropriate, correct either the source schema associated with the map or the native input instance message in the specified file, or both.</span></span> <span data-ttu-id="ae9f5-109">请考虑使用内 BizTalk 编辑器隔离问题。</span><span class="sxs-lookup"><span data-stu-id="ae9f5-109">Consider working within BizTalk Editor to isolate the problem.</span></span> <span data-ttu-id="ae9f5-110">**验证架构**和**生成实例**右键单击解决方案资源管理器中的架构时可用命令可用于查找架构错误。</span><span class="sxs-lookup"><span data-stu-id="ae9f5-110">The **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>