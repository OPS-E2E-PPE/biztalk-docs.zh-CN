---
title: 错误-一般性本地解析 |Microsoft Docs
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
ms.openlocfilehash: eb7b46fb6b04486c8c80a286c86a4f9cb3c84dbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348245"
---
# <a name="error---generic-native-parsing"></a><span data-ttu-id="e43c1-102">错误-一般性本地解析</span><span class="sxs-lookup"><span data-stu-id="e43c1-102">Error - Generic Native Parsing</span></span>
<span data-ttu-id="e43c1-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="e43c1-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e43c1-104">btm1042</span><span class="sxs-lookup"><span data-stu-id="e43c1-104">btm1042</span></span>  
  
 <span data-ttu-id="e43c1-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="e43c1-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e43c1-106">为测试映射操作指定的本地输入的实例消息文件无法分析和生成泛型分析错误。</span><span class="sxs-lookup"><span data-stu-id="e43c1-106">The native input instance message file specified for the Test Map operation could not be parsed, and generated a generic fatal parsing error.</span></span>  
  
 <span data-ttu-id="e43c1-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="e43c1-107">**User Action**</span></span>  
  
 <span data-ttu-id="e43c1-108">根据需要，正确的源架构与映射或本地输入的实例消息中指定的文件，或两种关联。</span><span class="sxs-lookup"><span data-stu-id="e43c1-108">As appropriate, correct either the source schema associated with the map or the native input instance message in the specified file, or both.</span></span> <span data-ttu-id="e43c1-109">请考虑工作在 BizTalk 编辑器中以找出问题。</span><span class="sxs-lookup"><span data-stu-id="e43c1-109">Consider working within BizTalk Editor to isolate the problem.</span></span> <span data-ttu-id="e43c1-110">**验证架构**并**生成实例**命令中，右键单击解决方案资源管理器中的架构后即可可用于找出架构错误。</span><span class="sxs-lookup"><span data-stu-id="e43c1-110">The **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>