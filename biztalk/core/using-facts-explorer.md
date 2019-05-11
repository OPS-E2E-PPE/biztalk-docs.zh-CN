---
title: 使用事实浏览器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Facts Explorer
- business rules, vocabularies
- business rules, schemas
- business rules, databases
- business rules, .NET classes
- Facts Explorer [Business Rule Composer]
ms.assetid: ee125eb1-d5b9-4121-8a25-fcb7a640570e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79020dd4487d338e839a4a6d7bacc815f2b19bf9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247327"
---
# <a name="using-facts-explorer"></a><span data-ttu-id="d4d70-102">使用事实浏览器</span><span class="sxs-lookup"><span data-stu-id="d4d70-102">Using Facts Explorer</span></span>
<span data-ttu-id="d4d70-103">事实浏览器包含四个选项卡：**词汇**， **XML 架构**，**数据库**，并且 **.NET 类**。</span><span class="sxs-lookup"><span data-stu-id="d4d70-103">The Facts Explorer contains four tabs: **Vocabularies**, **XML Schemas**, **Databases**, and **.NET Classes**.</span></span>  
  
## <a name="vocabularies-tab"></a><span data-ttu-id="d4d70-104">词汇选项卡</span><span class="sxs-lookup"><span data-stu-id="d4d70-104">Vocabularies tab</span></span>  
 <span data-ttu-id="d4d70-105">使用**词汇**在事实浏览器来管理词汇版本和定义的选项卡。</span><span class="sxs-lookup"><span data-stu-id="d4d70-105">Use the **Vocabularies** tab in the Facts Explorer to manage vocabulary versions and definitions.</span></span>  
  
 <span data-ttu-id="d4d70-106">使用快捷菜单来访问以下选项。</span><span class="sxs-lookup"><span data-stu-id="d4d70-106">Use the shortcut menu to access the following options.</span></span>  
  
|<span data-ttu-id="d4d70-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d4d70-107">Use this</span></span>|<span data-ttu-id="d4d70-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d4d70-108">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="d4d70-109">**添加新词汇**</span><span class="sxs-lookup"><span data-stu-id="d4d70-109">**Add New Vocabulary**</span></span>|<span data-ttu-id="d4d70-110">创建新的词汇。</span><span class="sxs-lookup"><span data-stu-id="d4d70-110">Create a new vocabulary.</span></span>|  
|<span data-ttu-id="d4d70-111">**添加新版本**</span><span class="sxs-lookup"><span data-stu-id="d4d70-111">**Add New Version**</span></span>|<span data-ttu-id="d4d70-112">创建所选词汇的新的空版本。</span><span class="sxs-lookup"><span data-stu-id="d4d70-112">Create a new empty version of the selected vocabulary.</span></span> <span data-ttu-id="d4d70-113">可以从其他版本复制定义并将其粘贴到新版本。</span><span class="sxs-lookup"><span data-stu-id="d4d70-113">You can copy definitions from other versions and paste them into the new version.</span></span>|  
|<span data-ttu-id="d4d70-114">**粘贴词汇版本**</span><span class="sxs-lookup"><span data-stu-id="d4d70-114">**Paste Vocabulary Version**</span></span>|<span data-ttu-id="d4d70-115">将以前复制的词汇版本的内容粘贴为所选词汇的新版本。</span><span class="sxs-lookup"><span data-stu-id="d4d70-115">Paste the contents of a previously copied vocabulary version as a new version in the selected vocabulary.</span></span>|  
|<span data-ttu-id="d4d70-116">**删除**</span><span class="sxs-lookup"><span data-stu-id="d4d70-116">**Delete**</span></span>|<span data-ttu-id="d4d70-117">删除所选的词汇及其所有版本。</span><span class="sxs-lookup"><span data-stu-id="d4d70-117">Delete the selected vocabulary and all its versions.</span></span>|  
|<span data-ttu-id="d4d70-118">**添加新定义**</span><span class="sxs-lookup"><span data-stu-id="d4d70-118">**Add New Definition**</span></span>|<span data-ttu-id="d4d70-119">启动词汇定义向导以在所选的词汇版本中创建新的定义。</span><span class="sxs-lookup"><span data-stu-id="d4d70-119">Launch the Vocabulary Definition Wizard to create a new definition in the selected vocabulary version.</span></span>|  
|<span data-ttu-id="d4d70-120">**保存**</span><span class="sxs-lookup"><span data-stu-id="d4d70-120">**Save**</span></span>|<span data-ttu-id="d4d70-121">保存对所选的版本及其定义所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d4d70-121">Save the changes made to the selected version and its definitions.</span></span>|  
|<span data-ttu-id="d4d70-122">**Publish**</span><span class="sxs-lookup"><span data-stu-id="d4d70-122">**Publish**</span></span>|<span data-ttu-id="d4d70-123">发布所选的词汇版本。</span><span class="sxs-lookup"><span data-stu-id="d4d70-123">Publish the selected vocabulary version.</span></span> <span data-ttu-id="d4d70-124">请注意，不能直接修改已发布的版本。</span><span class="sxs-lookup"><span data-stu-id="d4d70-124">Note that you cannot directly modify a published version.</span></span> <span data-ttu-id="d4d70-125">可以复制并将其粘贴到新版本的词汇。</span><span class="sxs-lookup"><span data-stu-id="d4d70-125">You can copy and paste it to a new version of the vocabulary.</span></span>|  
|<span data-ttu-id="d4d70-126">**重新加载**</span><span class="sxs-lookup"><span data-stu-id="d4d70-126">**Reload**</span></span>|<span data-ttu-id="d4d70-127">重新加载所选的词汇版本及其定义，可以选择放弃当前对该版本所做的全部更改和从规则存储恢复内容。</span><span class="sxs-lookup"><span data-stu-id="d4d70-127">Reload the selected vocabulary version and its definitions, with the option to discard any current changes made in that version and restore the contents from the rule store.</span></span>|  
|<span data-ttu-id="d4d70-128">**修改**</span><span class="sxs-lookup"><span data-stu-id="d4d70-128">**Modify**</span></span>|<span data-ttu-id="d4d70-129">启动词汇定义向导以更改所选的定义。</span><span class="sxs-lookup"><span data-stu-id="d4d70-129">Launch the Vocabulary Definition Wizard to change the selected definition.</span></span> <span data-ttu-id="d4d70-130">请注意，不能修改已发布的词汇版本的定义。</span><span class="sxs-lookup"><span data-stu-id="d4d70-130">Note that you cannot modify a definition that is part of a published vocabulary version.</span></span>|  
|<span data-ttu-id="d4d70-131">**转至源事实**</span><span class="sxs-lookup"><span data-stu-id="d4d70-131">**Go to source fact**</span></span>|<span data-ttu-id="d4d70-132">有关所选定义，请转至.NET 程序集、 XML 架构或数据库表中的对应源事实。</span><span class="sxs-lookup"><span data-stu-id="d4d70-132">For the selected definition, go to the corresponding source fact in a .NET assembly, XML schema, or database table.</span></span>|  
  
## <a name="xml-schemas-tab"></a><span data-ttu-id="d4d70-133">XML 架构选项卡</span><span class="sxs-lookup"><span data-stu-id="d4d70-133">XML Schemas tab</span></span>  
 <span data-ttu-id="d4d70-134">浏览 XSD 架构的 XML 元素和属性定义。</span><span class="sxs-lookup"><span data-stu-id="d4d70-134">Browse through XSD schemas for the definitions of XML elements and attributes.</span></span> <span data-ttu-id="d4d70-135">可以将拖到未发布的词汇版本上的项**词汇**选项卡上，以创建定义，或可以将项拖动到条件编辑器或操作编辑器中以定义谓词、 操作和参数。</span><span class="sxs-lookup"><span data-stu-id="d4d70-135">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
|<span data-ttu-id="d4d70-136">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d4d70-136">Use this</span></span>|<span data-ttu-id="d4d70-137">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d4d70-137">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="d4d70-138">**选择根节点**</span><span class="sxs-lookup"><span data-stu-id="d4d70-138">**Select Root Node**</span></span>|<span data-ttu-id="d4d70-139">选择要从包含多个根节点的 XML 架构加载的根节点。</span><span class="sxs-lookup"><span data-stu-id="d4d70-139">Select a root node to load from an XML schema that contains multiple root notes.</span></span>|  
  
## <a name="databases-tab"></a><span data-ttu-id="d4d70-140">数据库选项卡</span><span class="sxs-lookup"><span data-stu-id="d4d70-140">Databases tab</span></span>  
 <span data-ttu-id="d4d70-141">浏览数据库和表定义的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="d4d70-141">Browse through database servers for databases and table definitions.</span></span> <span data-ttu-id="d4d70-142">可以将拖到未发布的词汇版本上的项**词汇**选项卡上，以创建定义，或可以将项拖动到条件编辑器或操作编辑器中以定义谓词、 操作和参数。</span><span class="sxs-lookup"><span data-stu-id="d4d70-142">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
## <a name="net-classes-tab"></a><span data-ttu-id="d4d70-143">.NET 类选项卡</span><span class="sxs-lookup"><span data-stu-id="d4d70-143">.NET Classes tab</span></span>  
 <span data-ttu-id="d4d70-144">浏览查找公共.NET 类定义的.NET 程序集。</span><span class="sxs-lookup"><span data-stu-id="d4d70-144">Browse through .NET assemblies for public .NET class definitions.</span></span> <span data-ttu-id="d4d70-145">可以将拖到未发布的词汇版本上的项**词汇**选项卡上，以创建定义，或可以将项拖动到条件编辑器或操作编辑器中以定义谓词、 操作和参数。</span><span class="sxs-lookup"><span data-stu-id="d4d70-145">You can drag items onto unpublished vocabulary versions on the **Vocabulary** tab to create definitions, or you can drag items to the Conditions Editor or Actions Editor to define predicates, actions, and arguments.</span></span>  
  
|<span data-ttu-id="d4d70-146">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d4d70-146">Use this</span></span>|<span data-ttu-id="d4d70-147">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d4d70-147">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="d4d70-148">**“浏览”**</span><span class="sxs-lookup"><span data-stu-id="d4d70-148">**Browse**</span></span>|<span data-ttu-id="d4d70-149">从全局程序集缓存中加载.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="d4d70-149">Load a .NET assembly from the global assembly cache</span></span>|  
|<span data-ttu-id="d4d70-150">**删除**</span><span class="sxs-lookup"><span data-stu-id="d4d70-150">**Remove**</span></span>|<span data-ttu-id="d4d70-151">删除.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="d4d70-151">Remove a .NET assembly</span></span>|