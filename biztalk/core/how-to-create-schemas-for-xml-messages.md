---
title: 如何为 XML 消息创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22b241d002884f24be0a2972db24b8a398ee1d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984446"
---
# <a name="how-to-create-schemas-for-xml-messages"></a><span data-ttu-id="d9ae5-102">如何为 XML 消息创建架构</span><span class="sxs-lookup"><span data-stu-id="d9ae5-102">How to Create Schemas for XML Messages</span></span>
<span data-ttu-id="d9ae5-103">有几种方法用于创建 BizTalk 消息架构。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-103">There are several methods for creating BizTalk message schemas.</span></span> <span data-ttu-id="d9ae5-104">本主题提供一些方法的分步说明。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-104">This topic provides step-by-step instructions for some of those methods.</span></span>  
  
### <a name="to-create-a-new-schema"></a><span data-ttu-id="d9ae5-105">若要创建新的架构</span><span class="sxs-lookup"><span data-stu-id="d9ae5-105">To create a new schema</span></span>  
  
1. <span data-ttu-id="d9ae5-106">在中**解决方案资源管理器**，选择你想要添加的架构的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-106">In **Solution Explorer**, select the BizTalk project to which you want to add a schema.</span></span>  
  
2. <span data-ttu-id="d9ae5-107">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-107">On the **Project** menu, click **Add New Item**.</span></span>  
  
3. <span data-ttu-id="d9ae5-108">在中**添加新项- \< *BizTalk 项目名称*\>** 对话框中，在**模板**部分中，单击**架构**.</span><span class="sxs-lookup"><span data-stu-id="d9ae5-108">In the **Add New Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Schema**.</span></span>  
  
4. <span data-ttu-id="d9ae5-109">在中**名称**框中，键入架构的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-109">In the **Name** box, type a name for the schema, and then click **Add**.</span></span>  
  
5. <span data-ttu-id="d9ae5-110">如有必要，可按 F4 打开 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-110">If necessary, press F4 to open the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window.</span></span>  
  
6. <span data-ttu-id="d9ae5-111">在架构树视图中，选择**架构**节点，然后在属性窗口中，选择**Target Namespace**属性并键入目标命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-111">In the schema tree view, select the **Schema** node, and then in the Properties window, select the **Target Namespace** property and type a name for the target namespace.</span></span> <span data-ttu-id="d9ae5-112">务必将此属性设置在此初始阶段中的架构创建;避免使用默认值**目标 Namespace**属性值。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-112">It is important that you set this property in this initial phase of schema creation; avoid using the default **Target Namespace** property value.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d9ae5-113">某些项目成员文件，例如架构文件的名称选项可能会导致编译错误由于冲突而进行更高版本上使用 C# 保留字和.net Framework 类型和命名空间名称 （例如系统）。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-113">Certain name choices for project member files, such as schema files, can cause compilation errors later on due to conflicts with C# reserved words and.NET Framework type and namespace names (such as System).</span></span> <span data-ttu-id="d9ae5-114">例如以下架构名称：schema.xsd、XmlContent 和 RootNodes。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-114">Examples for schemas include schema.xsd, XmlContent, and RootNodes.</span></span> <span data-ttu-id="d9ae5-115">这是因为**类型名称**属性默认为基 （非扩展名） 部分**Filename**属性。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-115">This is because the **Type Name** property defaults to the base (non-extension) portion of the  **Filename** property.</span></span> <span data-ttu-id="d9ae5-116">可以通过显式更改的值来解决这种类型的编译错误**类型名称**为不冲突的属性。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-116">You can work around this type of compilation error by explicitly changing the value of the **Type Name** property to something that does not conflict.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d9ae5-117">您可能需要添加、 删除和修改的记录和字段以及其关联的属性架构中。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-117">You may need to add, delete, and modify the records and fields in your schema along with their associated properties.</span></span> <span data-ttu-id="d9ae5-118">若要了解详细信息，请参阅[管理架构节点内](../core/managing-the-nodes-within-a-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-118">To learn more about this, see [Managing the Nodes Within a Schema](../core/managing-the-nodes-within-a-schema.md).</span></span>  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a><span data-ttu-id="d9ae5-119">若要从非 XSD 源生成架构</span><span class="sxs-lookup"><span data-stu-id="d9ae5-119">To generate a schema from a non-XSD source</span></span>  
  
1.  <span data-ttu-id="d9ae5-120">在中**解决方案资源管理器**，右键单击 BizTalk 项目，依次指向**添加**，然后单击**添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-120">In **Solution Explorer**, right-click a BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="d9ae5-121">在中**添加生成的项- \< *BizTalk 项目名称*\>** 对话框中，在**模板**部分中，单击**生成架构**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-121">In the **Add Generated Items - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="d9ae5-122">在中**生成架构**对话框中**文档类型**下拉列表中，选择**XDR 架构**， **DTD 架构**，或**格式正确的 XML**。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-122">In the **Generate Schemas** dialog box, in the **Document type** drop-down list, select **XDR Schema**, **DTD Schema**, or **Well-Formed XML**.</span></span>  
  
     <span data-ttu-id="d9ae5-123">如果看到任何一个**DTD （未加载）** 或**格式正确的 XML （未加载）** 在下拉列表中，选择相应的文档类型，并完成安装过程将指导你缺少 DLL。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-123">If you see either **DTD (Not Loaded)** or **Well-Formed XML (Not Loaded)** in the drop-down list, select the appropriate document type anyway, and you will be guided through the process of installing the missing DLL.</span></span> <span data-ttu-id="d9ae5-124">然后，重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-124">Then repeat these steps.</span></span>  
  
4.  <span data-ttu-id="d9ae5-125">在中**生成架构**对话框中，单击**浏览**，找到你想要导入，然后单击的文件**打开**。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-125">In the **Generate Schemas** dialog box, click **Browse**, locate the file you want to import, and then click **Open**.</span></span> <span data-ttu-id="d9ae5-126">您找到该文件必须匹配你在上一步中选择的文档类型。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-126">The file you locate must match the document type you selected in the previous step.</span></span>  
  
     <span data-ttu-id="d9ae5-127">从指定的文件，使用相同的名称作为该文件扩展名为.xsd 和 BizTalk 编辑器中打开生成新的架构。</span><span class="sxs-lookup"><span data-stu-id="d9ae5-127">A new schema is generated from the specified file, using the same name as that file with the .xsd extension, and opened in BizTalk Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ae5-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9ae5-128">See Also</span></span>  
 [<span data-ttu-id="d9ae5-129">管理项目中的架构</span><span class="sxs-lookup"><span data-stu-id="d9ae5-129">Managing Schemas Within Projects</span></span>](../core/managing-schemas-within-projects.md)