---
title: "错误-根节点重复类名称 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edit.error.rootNodeDupClassName
ms.assetid: 0c7c4d55-9311-4af6-ac26-60b1b943db91
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2011ac3f1295d3eb63d036645f30938c299adff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---root-node-duplicate-class-name"></a><span data-ttu-id="b9bbb-102">错误-根节点重复类名称</span><span class="sxs-lookup"><span data-stu-id="b9bbb-102">Error - Root Node Duplicate Class Name</span></span>
<span data-ttu-id="b9bbb-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="b9bbb-103">**Error Code**</span></span>  
  
 <span data-ttu-id="b9bbb-104">BEC2013</span><span class="sxs-lookup"><span data-stu-id="b9bbb-104">BEC2013</span></span>  
  
 <span data-ttu-id="b9bbb-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="b9bbb-105">**Explanation**</span></span>  
  
 <span data-ttu-id="b9bbb-106">**RootNode TypeName**架构中的根节点的所有属性都必须唯一。</span><span class="sxs-lookup"><span data-stu-id="b9bbb-106">The **RootNode TypeName** property of all of the root nodes in a schema must be unique.</span></span> <span data-ttu-id="b9bbb-107">已找到两个或多个此架构中的根节点具有相同的值，其**RootNode TypeName**属性。</span><span class="sxs-lookup"><span data-stu-id="b9bbb-107">Two or more of the root nodes in this schema have been found to have the same value for their **RootNode TypeName** properties.</span></span>  
  
 <span data-ttu-id="b9bbb-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="b9bbb-108">**User Action**</span></span>  
  
 <span data-ttu-id="b9bbb-109">选择相关的根节点反过来，从而确保你为提供的值及其**RootNode TypeName**属性是有效且唯一。</span><span class="sxs-lookup"><span data-stu-id="b9bbb-109">Select the relevant root nodes in turn, ensuring that the values you supply for their **RootNode TypeName** properties are valid and unique.</span></span>