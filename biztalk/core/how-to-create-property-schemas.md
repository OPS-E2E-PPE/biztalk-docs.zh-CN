---
title: 如何创建属性架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24086dea-62b8-4ef6-8af8-eb4ab7c3c018
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee97f4cb3065fdb201ec19f88a79e7899f03ac49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970475"
---
# <a name="how-to-create-property-schemas"></a><span data-ttu-id="93200-102">如何创建属性架构</span><span class="sxs-lookup"><span data-stu-id="93200-102">How to Create Property Schemas</span></span>
<span data-ttu-id="93200-103">如果选择将字段升级为属性字段，则需要首先定义属性架构。</span><span class="sxs-lookup"><span data-stu-id="93200-103">If you choose to promote fields as property fields, you will need to define a property schema first.</span></span> <span data-ttu-id="93200-104">此属性架构指定了一个非结构化的字段集合，您可以将与属性架构相关联的架构所定义的实例消息中的字段升级到该字段集合中。</span><span class="sxs-lookup"><span data-stu-id="93200-104">This property schema specifies an unstructured collection of fields into which you can promote fields from within an instance message defined by a schema associated with your property schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="93200-105">不要复制或编辑现有属性架构来创建新的架构。</span><span class="sxs-lookup"><span data-stu-id="93200-105">Do not copy and edit an existing property schema to create a new schema.</span></span> <span data-ttu-id="93200-106">属性架构包含特定于架构的内部数据。</span><span class="sxs-lookup"><span data-stu-id="93200-106">The property schema contains schema-specific internal data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93200-107">无需创建属性架构即可升级可分辨字段。</span><span class="sxs-lookup"><span data-stu-id="93200-107">You do not need to create a property schema to promote distinguished fields.</span></span>  
  
### <a name="to-create-a-property-schema"></a><span data-ttu-id="93200-108">创建属性架构</span><span class="sxs-lookup"><span data-stu-id="93200-108">To create a property schema</span></span>  
  
1.  <span data-ttu-id="93200-109">在**解决方案资源管理器**，右键单击 BizTalk 项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="93200-109">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="93200-110">在**添加新项**对话框中，在**模板**部分中，单击**属性架构**。</span><span class="sxs-lookup"><span data-stu-id="93200-110">In the **Add New Item** dialog box, in the **Templates** section, click **Property Schema**.</span></span>  
  
3.  <span data-ttu-id="93200-111">在**名称**框中，为架构中，键入一个名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="93200-111">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
     <span data-ttu-id="93200-112">新的属性架构将打开，并且它已包含**Field 元素**名为 Property1 节点。</span><span class="sxs-lookup"><span data-stu-id="93200-112">The new property schema opens, and it already contains a **Field Element** node named Property1.</span></span>  
  
4.  <span data-ttu-id="93200-113">在架构树中，右键单击**Field 元素**节点，单击**重命名**，在架构中，键入第一个属性的描述性名称，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="93200-113">In the schema tree, right-click that **Field Element** node, click **Rename**, type a descriptive name for the first property in the schema, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="93200-114">设置**数据类型**和其他相关的属性，根据需要为**Field 元素**属性窗口中的节点。</span><span class="sxs-lookup"><span data-stu-id="93200-114">Set the **Data Type** and other relevant properties, as appropriate, for the **Field Element** node in the Properties window.</span></span>  
  
6.  <span data-ttu-id="93200-115">如果你想要插入**Field 元素**对于其他属性，节点右键单击\<架构\>节点，单击**插入架构节点**，然后单击**子字段元素**，然后重复步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="93200-115">If you want to insert **Field Element** nodes for additional properties, right-click the \<Schema\> node, click **Insert Schema Node**, and then click **Child Field Element**, and then repeat steps 4 and 5.</span></span> <span data-ttu-id="93200-116">根据需要创建组所需的重复**Field 元素**你想要从实例消息升级值到其中的节点。</span><span class="sxs-lookup"><span data-stu-id="93200-116">Repeat as necessary to create the required set of **Field Element** nodes into which you intend to promote values from instance messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93200-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93200-117">See Also</span></span>  
 [<span data-ttu-id="93200-118">管理项目中的架构</span><span class="sxs-lookup"><span data-stu-id="93200-118">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)