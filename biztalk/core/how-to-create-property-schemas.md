---
title: 如何创建属性架构 |Microsoft Docs
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
ms.openlocfilehash: 4fcab4ad4370fe68558fe1ca47de13f9a896c5a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339376"
---
# <a name="how-to-create-property-schemas"></a><span data-ttu-id="bf7e9-102">如何创建属性架构</span><span class="sxs-lookup"><span data-stu-id="bf7e9-102">How to Create Property Schemas</span></span>
<span data-ttu-id="bf7e9-103">如果选择将字段升级为属性字段，您需要首先定义属性架构。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-103">If you choose to promote fields as property fields, you will need to define a property schema first.</span></span> <span data-ttu-id="bf7e9-104">此属性架构指定从定义与属性架构相关联的架构的实例消息中的字段可以升级到这些字段的非结构化的的集合。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-104">This property schema specifies an unstructured collection of fields into which you can promote fields from within an instance message defined by a schema associated with your property schema.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bf7e9-105">不要复制或编辑现有属性架构来创建新的架构。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-105">Do not copy and edit an existing property schema to create a new schema.</span></span> <span data-ttu-id="bf7e9-106">属性架构包含特定于架构的内部数据。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-106">The property schema contains schema-specific internal data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf7e9-107">不需要创建用于升级可分辨的字段的属性架构。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-107">You do not need to create a property schema to promote distinguished fields.</span></span>  
  
### <a name="to-create-a-property-schema"></a><span data-ttu-id="bf7e9-108">若要创建属性架构</span><span class="sxs-lookup"><span data-stu-id="bf7e9-108">To create a property schema</span></span>  
  
1.  <span data-ttu-id="bf7e9-109">在中**解决方案资源管理器**，右键单击 BizTalk 项目，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-109">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="bf7e9-110">在中**添加新项**对话框中**模板**部分中，单击**属性架构**。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-110">In the **Add New Item** dialog box, in the **Templates** section, click **Property Schema**.</span></span>  
  
3.  <span data-ttu-id="bf7e9-111">在中**名称**框中，键入架构的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-111">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
     <span data-ttu-id="bf7e9-112">此时会打开新的属性架构，并且其中已包含**Field 元素**名为 Property1 节点。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-112">The new property schema opens, and it already contains a **Field Element** node named Property1.</span></span>  
  
4.  <span data-ttu-id="bf7e9-113">在架构树中，右键单击**Field 元素**节点中，单击**重命名**，在架构中，键入第一个属性的描述性名称，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-113">In the schema tree, right-click that **Field Element** node, click **Rename**, type a descriptive name for the first property in the schema, and then press ENTER.</span></span>  
  
5.  <span data-ttu-id="bf7e9-114">设置**数据类型**和其他相关属性，根据需要，为**Field 元素**属性窗口中的节点。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-114">Set the **Data Type** and other relevant properties, as appropriate, for the **Field Element** node in the Properties window.</span></span>  
  
6.  <span data-ttu-id="bf7e9-115">如果你想要插入**Field 元素**节点的其他属性，右键单击\<架构\>节点中，单击**插入 Schema 节点**，然后单击**子字段元素**，然后重复步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-115">If you want to insert **Field Element** nodes for additional properties, right-click the \<Schema\> node, click **Insert Schema Node**, and then click **Child Field Element**, and then repeat steps 4 and 5.</span></span> <span data-ttu-id="bf7e9-116">根据需要创建组所需的重复**Field 元素**节点到你想要升级实例消息中的值。</span><span class="sxs-lookup"><span data-stu-id="bf7e9-116">Repeat as necessary to create the required set of **Field Element** nodes into which you intend to promote values from instance messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7e9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf7e9-117">See Also</span></span>  
 [<span data-ttu-id="bf7e9-118">管理项目中的架构</span><span class="sxs-lookup"><span data-stu-id="bf7e9-118">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)