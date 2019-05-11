---
title: 编译映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, compiling
- XSLT, generating
- maps, validating
- BizTalk Mapper, compiling
- BizTalk Mapper, validating
ms.assetid: 967181d6-22a9-4a76-ae45-3317c0c6321b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46b02fecc64ae238d19ccacb565519321ce960af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357866"
---
# <a name="compiling-maps"></a><span data-ttu-id="31792-102">编译映射</span><span class="sxs-lookup"><span data-stu-id="31792-102">Compiling Maps</span></span>
<span data-ttu-id="31792-103">当验证映射时，BizTalk 映射器编译器组件将生成可扩展样式表语言转换 (XSLT) 样式表。</span><span class="sxs-lookup"><span data-stu-id="31792-103">When you validate maps, the BizTalk Mapper compiler component generates an Extensible Stylesheet Language Transformations (XSLT) style sheet.</span></span> <span data-ttu-id="31792-104">这将创建编译的映射，通过转换到目标架构所定义的实例消息的源架构定义的实例消息。</span><span class="sxs-lookup"><span data-stu-id="31792-104">This creates a compiled map that transforms an instance message defined by the source schema to an instance message defined by the destination schema.</span></span> <span data-ttu-id="31792-105">编译映射将执行的结构规则和转换的网格页中指定。</span><span class="sxs-lookup"><span data-stu-id="31792-105">Compiling a map enforces the structural rules and transformations specified in the grid pages.</span></span>  
  
 <span data-ttu-id="31792-106">转换，如链接，在目标架构中的记录和字段出现的顺序处理。</span><span class="sxs-lookup"><span data-stu-id="31792-106">Transformations, such as links, are processed in the same order that records and fields appear in the destination schema.</span></span> <span data-ttu-id="31792-107">例如，当 BizTalk 映射器到达目标时，才**记录**或**字段**节点的链接，BizTalk 映射器将编译链接的属性。</span><span class="sxs-lookup"><span data-stu-id="31792-107">For example, when BizTalk Mapper reaches a destination **Record** or **Field** node with a link, BizTalk Mapper compiles the properties of the link.</span></span> <span data-ttu-id="31792-108">该操作可能是记录或字段在源架构中，从一个简单的复制值或操作可能会涉及多个计算使用 functoid 以及多个记录和字段。</span><span class="sxs-lookup"><span data-stu-id="31792-108">The action might be a simple copy value from a record or field in the source schema, or the action might involve multiple calculations using functoids and multiple records and fields.</span></span>  
  
 <span data-ttu-id="31792-109">BizTalk 映射器生成中的警告**输出**窗口和**任务列表**窗口，当编译器遇到可能生成不正确的输出的情况。</span><span class="sxs-lookup"><span data-stu-id="31792-109">BizTalk Mapper generates warnings in the **Output** window and **Task List** window when the compiler encounters a situation that might yield incorrect output.</span></span> <span data-ttu-id="31792-110">例如，如果 functoid 需要一个输入的参数，并且没有输入参数，则 BizTalk 映射器生成中的警告**输出**窗口。</span><span class="sxs-lookup"><span data-stu-id="31792-110">For example, if a functoid requires one input parameter and has no input parameters, BizTalk Mapper generates a warning in the **Output** window.</span></span> <span data-ttu-id="31792-111">一般情况下，不应使用生成警告的生产环境中的地图。</span><span class="sxs-lookup"><span data-stu-id="31792-111">In general, you should not use a map in a production environment if it is generating warnings.</span></span>  
  
 <span data-ttu-id="31792-112">生成的 XSLT 样式表的链接也将出现在**输出**窗口时正确编译该映射。</span><span class="sxs-lookup"><span data-stu-id="31792-112">A link to the generated XSLT style sheet also appears in the **Output** window when the map compiles correctly.</span></span>  
  
 <span data-ttu-id="31792-113">BizTalk Server 使用编译的映射来执行的输入的实例消息到输出实例消息翻译。</span><span class="sxs-lookup"><span data-stu-id="31792-113">BizTalk Server uses the compiled map to perform the translation of an input instance message to an output instance message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31792-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="31792-114">See Also</span></span>  
 <span data-ttu-id="31792-115">[测试映射](../core/testing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="31792-115">[Testing Maps](../core/testing-maps.md) </span></span>  
 <span data-ttu-id="31792-116">[数据转换配置](../core/data-transformation-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="31792-116">[Data Transformation Configuration](../core/data-transformation-configuration.md) </span></span>  
 [<span data-ttu-id="31792-117">节点层次结构级匹配</span><span class="sxs-lookup"><span data-stu-id="31792-117">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)