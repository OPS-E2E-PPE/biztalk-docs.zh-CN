---
title: 错误-本机序列化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeSerialize
ms.assetid: 48f8d460-83a0-44ce-af9b-086fcad36cb8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80d6d9df379b93a11d4d736161029684ec175cb1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347272"
---
# <a name="error---native-serialization"></a><span data-ttu-id="6a682-102">错误-本机序列化</span><span class="sxs-lookup"><span data-stu-id="6a682-102">Error - Native Serialization</span></span>
<span data-ttu-id="6a682-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="6a682-103">**Error Code**</span></span>  
  
 <span data-ttu-id="6a682-104">btm1048</span><span class="sxs-lookup"><span data-stu-id="6a682-104">btm1048</span></span>  
  
 <span data-ttu-id="6a682-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="6a682-105">**Explanation**</span></span>  
  
 <span data-ttu-id="6a682-106">尝试将 XML 输出实例消息转换映射生成到目标架构指定的本机格式时遇到指示的序列化错误。</span><span class="sxs-lookup"><span data-stu-id="6a682-106">The indicated serialization error was encountered when attempting to convert the XML output instance message produced by the map into the native format specified by the destination schema.</span></span>  
  
 <span data-ttu-id="6a682-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="6a682-107">**User Action**</span></span>  
  
 <span data-ttu-id="6a682-108">在映射中指定的转换或目标架构中，或者对二者同时根据指示的序列化错误，请合适的更正。</span><span class="sxs-lookup"><span data-stu-id="6a682-108">Based on the indicated serialization error, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="6a682-109">可能会有帮助，BizTalk 编辑器中打开目标架构，并使用**验证架构**，**验证实例**，并**生成实例**命令可用右键单击解决方案资源管理器中的架构。</span><span class="sxs-lookup"><span data-stu-id="6a682-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>