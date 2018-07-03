---
title: 如何保存、 重命名，并关闭架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65e15d9e-40ae-4850-9c13-88033cb3b3bb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059a52bd3dd34669c5809653302c049eee92b96e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002902"
---
# <a name="how-to-save-rename-and-close-schemas"></a><span data-ttu-id="48e22-102">如何保存、 重命名，并关闭架构</span><span class="sxs-lookup"><span data-stu-id="48e22-102">How to Save, Rename, and Close Schemas</span></span>
<span data-ttu-id="48e22-103">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，架构是具有 .xsd 扩展名的 XML 架构定义 (XSD) 语言文件并驻留在文件系统中。</span><span class="sxs-lookup"><span data-stu-id="48e22-103">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], schemas are XML Schema definition (XSD) language files and reside on the file system with .xsd extensions.</span></span> <span data-ttu-id="48e22-104">在使用 BizTalk 编辑器开发架构时，会经常需要保存和关闭架构文件，有时还可能需要重命名这些文件。</span><span class="sxs-lookup"><span data-stu-id="48e22-104">When you use BizTalk Editor to develop schemas, you will routinely need to save and close schema files, and occasionally you may need to rename them.</span></span> <span data-ttu-id="48e22-105">本主题将介绍执行这些基本操作所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="48e22-105">This topic describes the steps required to perform these basic operations.</span></span>  
  
### <a name="to-save-a-schema"></a><span data-ttu-id="48e22-106">若要保存架构</span><span class="sxs-lookup"><span data-stu-id="48e22-106">To save a schema</span></span>  
  
1. <span data-ttu-id="48e22-107">如果需要，可以通过单击 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中主编辑窗口顶部相应的选项卡，为要保存的架构激活 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="48e22-107">If necessary, activate BizTalk Editor for the schema to be saved by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="48e22-108">上**文件**菜单上，单击 * * 保存 *\<架构名称\>* * *。</span><span class="sxs-lookup"><span data-stu-id="48e22-108">On the **File** menu, click **Save *\<Name of Schema\>***.</span></span>  
  
    <span data-ttu-id="48e22-109">如尚未保存对架构所做的更改，则显示在主编辑窗口顶部的选项卡上的该架构的名称将不再以星号 (\*) 结尾，这表示更改未保存。</span><span class="sxs-lookup"><span data-stu-id="48e22-109">If the schema had unsaved changes, its name as displayed on the tab at the top of the main editing window will no longer end with an asterisk (\*), which is used to indicate unsaved changes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48e22-110">您可以通过单击保存以新名称的架构**保存*\<名称的架构\>* 作为**上**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="48e22-110">You can save the schema under a new name by clicking **Save *\<Name of Schema\>* As** on the **File** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48e22-111">您可以将架构作为保存所有更改的项目在项目中通过单击操作的一部分**全部保存**上**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="48e22-111">You can save the schema as part of saving all changed items in the project by clicking **Save All** on the **File** menu.</span></span>  
  
#### <a name="to-rename-a-schema"></a><span data-ttu-id="48e22-112">若要重命名架构</span><span class="sxs-lookup"><span data-stu-id="48e22-112">To rename a schema</span></span>  
  
1.  <span data-ttu-id="48e22-113">在解决方案资源管理器，右键单击你想要重命名，然后单击架构**重命名**。</span><span class="sxs-lookup"><span data-stu-id="48e22-113">In Solution Explorer, right-click the schema that you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="48e22-114">在解决方案资源管理器中显示在该架构位置的编辑框内，为该架构键入新名称，或更改其现有名称，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="48e22-114">In the editing box that appears in the location of the schema in Solution Explorer, type the new name for the schema, or alter its existing name, and then press ENTER.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48e22-115">您可能还需要更改**类型名称**进行重命名的架构。</span><span class="sxs-lookup"><span data-stu-id="48e22-115">You may also want to change the **Type Name** of the schema when you rename.</span></span> <span data-ttu-id="48e22-116">您更改**类型名称**通过选择**架构**中的解决方案资源管理器并输入中的新名称**类型名称**属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="48e22-116">You change the **Type Name** by selecting the **schema** in the solution explorer and entering the new name in the **Type Name** in the Properties window.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="48e22-117">不应对正在由其他架构使用的架构进行重命名。</span><span class="sxs-lookup"><span data-stu-id="48e22-117">You should not rename any schema that is being used by another schema.</span></span> <span data-ttu-id="48e22-118">其中包括已由其他架构包括、导入或重新定义的架构，以及已为其建立升级的属性架构。</span><span class="sxs-lookup"><span data-stu-id="48e22-118">This includes schemas that have been included, imported, or redefined by other schemas, as well as property schemas for which promotions have already been established.</span></span> <span data-ttu-id="48e22-119">如果进行了重命名，则正在使用的架构将无法找到另外一个架构，因为它所包含的名称已不准确。</span><span class="sxs-lookup"><span data-stu-id="48e22-119">If you do so, the schema that is being used will not be able to find the renamed schema because the name it contains will no longer be accurate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48e22-120">对于诸如架构文件之类的项目成员文件，如果选择某些名称作为其名称，可能会由于与 C# 保留字、.NET Framework 类型和命名空间名称（例如“System”）之间的冲突而导致以后出现编译错误。</span><span class="sxs-lookup"><span data-stu-id="48e22-120">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as "System").</span></span> <span data-ttu-id="48e22-121">例如以下架构名称：schema.xsd、XmlContent 和 RootNodes。</span><span class="sxs-lookup"><span data-stu-id="48e22-121">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="48e22-122">这是因为**类型名称**属性默认为基 （非扩展名） 部分**Filename**属性。</span><span class="sxs-lookup"><span data-stu-id="48e22-122">This is because the **Type Name** property defaults to the base (non-extension) portion of the **Filename** property.</span></span> <span data-ttu-id="48e22-123">可以通过显式更改的值来解决这种类型的编译错误**类型名称**为不冲突的属性。</span><span class="sxs-lookup"><span data-stu-id="48e22-123">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
#### <a name="to-close-a-schema"></a><span data-ttu-id="48e22-124">若要关闭架构</span><span class="sxs-lookup"><span data-stu-id="48e22-124">To close a schema</span></span>  
  
1. <span data-ttu-id="48e22-125">如有必要，激活 BizTalk 编辑器中的架构通过单击 Microsoft 中主编辑窗口顶部相应的选项卡关闭[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="48e22-125">If necessary, activate BizTalk Editor for the schema to be closed by clicking the appropriate tab at the top of the main editing window in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
2. <span data-ttu-id="48e22-126">在 **“文件”** 菜单上，单击 **“关闭”**。</span><span class="sxs-lookup"><span data-stu-id="48e22-126">On the **File** menu, click **Close**.</span></span>  
  
    <span data-ttu-id="48e22-127">对于已关闭的架构，相应的 BizTalk 编辑器也将关闭。</span><span class="sxs-lookup"><span data-stu-id="48e22-127">BizTalk Editor closes for the schema that has been closed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e22-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="48e22-128">See Also</span></span>  
 [<span data-ttu-id="48e22-129">管理项目中的架构</span><span class="sxs-lookup"><span data-stu-id="48e22-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)