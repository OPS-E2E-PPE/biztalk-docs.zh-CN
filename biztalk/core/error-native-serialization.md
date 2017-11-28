---
title: "错误-本机序列化 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.nativeSerialize
ms.assetid: 48f8d460-83a0-44ce-af9b-086fcad36cb8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0d4a842a3f9a10703fb47bf21edb01ab92bd93c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---native-serialization"></a><span data-ttu-id="f5845-102">错误-本机序列化</span><span class="sxs-lookup"><span data-stu-id="f5845-102">Error - Native Serialization</span></span>
<span data-ttu-id="f5845-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="f5845-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f5845-104">btm1048</span><span class="sxs-lookup"><span data-stu-id="f5845-104">btm1048</span></span>  
  
 <span data-ttu-id="f5845-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="f5845-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f5845-106">尝试将映射所生成的 XML 输出实例消息转换为目标架构所指定的本地格式时，出现如消息中所指示的序列化错误。</span><span class="sxs-lookup"><span data-stu-id="f5845-106">The indicated serialization error was encountered when attempting to convert the XML output instance message produced by the map into the native format specified by the destination schema.</span></span>  
  
 <span data-ttu-id="f5845-107">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="f5845-107">**User Action**</span></span>  
  
 <span data-ttu-id="f5845-108">根据所指示的序列化错误，适当修改映射中指定的转换或目标架构，或者对二者同时进行修改。</span><span class="sxs-lookup"><span data-stu-id="f5845-108">Based on the indicated serialization error, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="f5845-109">它可能有助于 BizTalk 编辑器中打开目标架构以及使用**验证架构**，**验证实例**，和**生成实例**命令可用右键单击解决方案资源管理器中的架构。</span><span class="sxs-lookup"><span data-stu-id="f5845-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>