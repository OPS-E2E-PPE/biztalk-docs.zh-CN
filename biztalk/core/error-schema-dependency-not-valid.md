---
title: 错误-架构依存关系无效 |Microsoft Docs
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
ms.openlocfilehash: bcee29e7074ca012c11aea738c5fa44c6e702352
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346956"
---
# <a name="error---schema-dependency-not-valid"></a><span data-ttu-id="2c61f-102">错误-架构依存关系无效</span><span class="sxs-lookup"><span data-stu-id="2c61f-102">Error - Schema Dependency Not Valid</span></span>
<span data-ttu-id="2c61f-103">**错误代码**</span><span class="sxs-lookup"><span data-stu-id="2c61f-103">**Error Code**</span></span>  
  
 <span data-ttu-id="2c61f-104">BEC2009</span><span class="sxs-lookup"><span data-stu-id="2c61f-104">BEC2009</span></span>  
  
 <span data-ttu-id="2c61f-105">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c61f-105">**Explanation**</span></span>  
  
 <span data-ttu-id="2c61f-106">所有相关的架构，如将导入的那些包含，或当前架构中重新定义，必须添加到此 BizTalk 项目或存在于此项目所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="2c61f-106">All dependent schemas, such as those that are imported, included, or redefined in the current schema, must be added to this BizTalk project or exist in an assembly referenced by this project.</span></span> <span data-ttu-id="2c61f-107">即使架构**导入**，**包括**，并**重新定义**必须将架构指定远程网站的指令添加到此 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2c61f-107">Even schema **import**, **include**, and **redefine** directives that specify schemas on a remote Web site must be added to this BizTalk project.</span></span>  
  
 <span data-ttu-id="2c61f-108">**用户执行任何操作**</span><span class="sxs-lookup"><span data-stu-id="2c61f-108">**User Action**</span></span>  
  
 <span data-ttu-id="2c61f-109">使用**添加现有项**命令**文件**菜单和 Microsoft® BizTalk® Server 项目将此架构所依赖的所有架构添加到 BizTalk 项目的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="2c61f-109">Use the **Add Existing Item** command on the **File** menu and the shortcut menu for the Microsoft® BizTalk® Server project to add all schemas upon which this schema depends to the BizTalk project.</span></span> <span data-ttu-id="2c61f-110">您可能需要此类架构从 Web 站点下载到本地硬盘之前将它们添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2c61f-110">You may need to download such schemas from a Web site to your local hard disk before adding them to the BizTalk project.</span></span>