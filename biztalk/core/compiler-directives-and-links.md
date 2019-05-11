---
title: 编译器指令和链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compilier directives
- maps, compiling
- BizTalk Mapper, compiler directives
- links [maps], compiling
ms.assetid: 1655e10c-af98-4100-849d-b8214f93cfe9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8dd646a456a06d4ca032f6e68eadf386979bb15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356960"
---
# <a name="compiler-directives-and-links"></a><span data-ttu-id="6215f-102">编译器指令和链接</span><span class="sxs-lookup"><span data-stu-id="6215f-102">Compiler Directives and Links</span></span>
<span data-ttu-id="6215f-103">你可以在链接的链接的基础上配置以下两条编译器指令：</span><span class="sxs-lookup"><span data-stu-id="6215f-103">You can configure the following two compiler directives on a link-by-link basis:</span></span>  
  
- <span data-ttu-id="6215f-104">检索输入的实例消息中的哪些数据并将其复制为输出实例消息中的相关元素或属性值。</span><span class="sxs-lookup"><span data-stu-id="6215f-104">What data from the input instance message is retrieved and copied as the relevant element or attribute value in the output instance message.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="6215f-105">此处的数据包括用于复制的元素或属性名称的选项本身，而不是元素或属性相关联的任何值。</span><span class="sxs-lookup"><span data-stu-id="6215f-105">Data here includes the option to copy the name of the element or attribute itself, rather than any value associated with the element or attribute.</span></span> <span data-ttu-id="6215f-106">元素和属性名称都不通常被视为 XML 实例消息中传送数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="6215f-106">Element and attribute names are not normally thought of as part of the data carried in an XML instance message.</span></span>  
  
- <span data-ttu-id="6215f-107">如何匹配节点是源和目标架构之间的执行。</span><span class="sxs-lookup"><span data-stu-id="6215f-107">How node-matching is performed between the source and destination schemas.</span></span>  
  
  <span data-ttu-id="6215f-108">本部分提供了这些选项可用于这些指令的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="6215f-108">This section provides a detailed explanation of these options available for these directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6215f-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="6215f-109">In This Section</span></span>  
  
-   [<span data-ttu-id="6215f-110">数据转换配置</span><span class="sxs-lookup"><span data-stu-id="6215f-110">Data Transformation Configuration</span></span>](../core/data-transformation-configuration.md)  
  
-   [<span data-ttu-id="6215f-111">节点层次结构级匹配</span><span class="sxs-lookup"><span data-stu-id="6215f-111">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)