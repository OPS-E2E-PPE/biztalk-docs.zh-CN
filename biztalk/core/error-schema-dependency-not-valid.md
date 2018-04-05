---
title: 错误-架构依存关系无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaDependencyNotValid
ms.assetid: 431278f0-6cd1-4b3f-8d87-16af4991d354
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36326608f191b520c41cb42890aec029c432fd30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error---schema-dependency-not-valid"></a><span data-ttu-id="9d058-102">错误-架构依存关系无效</span><span class="sxs-lookup"><span data-stu-id="9d058-102">Error - Schema Dependency Not Valid</span></span>
<span data-ttu-id="9d058-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="9d058-103">**Error Code**</span></span>  
  
 <span data-ttu-id="9d058-104">BEC2009</span><span class="sxs-lookup"><span data-stu-id="9d058-104">BEC2009</span></span>  
  
 <span data-ttu-id="9d058-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="9d058-105">**Explanation**</span></span>  
  
 <span data-ttu-id="9d058-106">所有相关的架构，如导入、 包含，或在当前架构中重新定义，必须添加到此 BizTalk 项目或存在于此项目所引用的程序集中。</span><span class="sxs-lookup"><span data-stu-id="9d058-106">All dependent schemas, such as those that are imported, included, or redefined in the current schema, must be added to this BizTalk project or exist in an assembly referenced by this project.</span></span> <span data-ttu-id="9d058-107">甚至架构**导入**，**包括**，和**重新定义**远程网站指定架构的指令必须添加到此 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="9d058-107">Even schema **import**, **include**, and **redefine** directives that specify schemas on a remote Web site must be added to this BizTalk project.</span></span>  
  
 <span data-ttu-id="9d058-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="9d058-108">**User Action**</span></span>  
  
 <span data-ttu-id="9d058-109">使用**添加现有项**命令**文件**菜单和 Microsoft® BizTalk® Server 项目将此架构所依赖的所有架构添加到 BizTalk 项目的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="9d058-109">Use the **Add Existing Item** command on the **File** menu and the shortcut menu for the Microsoft® BizTalk® Server project to add all schemas upon which this schema depends to the BizTalk project.</span></span> <span data-ttu-id="9d058-110">你可能需要这样的架构从网站下载到本地硬盘添加到 BizTalk 项目之前。</span><span class="sxs-lookup"><span data-stu-id="9d058-110">You may need to download such schemas from a Web site to your local hard disk before adding them to the BizTalk project.</span></span>