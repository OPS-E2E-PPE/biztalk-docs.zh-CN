---
title: "实例消息处理使用属性提升 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 753571b8-4609-4ac4-a974-8bd6dfecb077
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 288657d43443582c5a05df5dd6e67059eca572e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="instance-message-processing-using-property-promotion"></a><span data-ttu-id="54278-102">使用属性升级处理实例消息</span><span class="sxs-lookup"><span data-stu-id="54278-102">Instance Message Processing Using Property Promotion</span></span>
<span data-ttu-id="54278-103">将属性提升通过**属性字段**方法，则需要创建的属性架构。</span><span class="sxs-lookup"><span data-stu-id="54278-103">Promoting properties by using the **Property Field** method requires the creation of a property schema.</span></span> <span data-ttu-id="54278-104">有关创建属性架构的详细信息，请参阅[如何创建属性架构](../core/how-to-create-property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="54278-104">For more information about creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span> <span data-ttu-id="54278-105">因为所有属性提升，与你使用**升级属性**对话框中，这是可访问通过使用**升级属性**属性**架构**中的节点消息架构。</span><span class="sxs-lookup"><span data-stu-id="54278-105">As with all property promotion, you use the **Promote Properties** dialog box, which is accessible by using the **Promote Properties** property of the **Schema** node in message schemas.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54278-106">您必须选择升级属性的管道，以便访问和使用升级属性。</span><span class="sxs-lookup"><span data-stu-id="54278-106">You must choose a pipeline that promotes properties in order to access and use the promote properties.</span></span> <span data-ttu-id="54278-107">例如，如果您使用 PassthruReceive 管道，将不会升级任何属性；因此，基于内容的路由和其他功能将无法按预期使用。</span><span class="sxs-lookup"><span data-stu-id="54278-107">For example, if you use the PassthruReceive pipeline, no properties will be promoted; as a result, content-based routing and other functionality will not work as expected.</span></span>  
  
 <span data-ttu-id="54278-108">在**升级属性**对话框框中，请确保**属性字段**在对话框中的右侧选择选项卡。</span><span class="sxs-lookup"><span data-stu-id="54278-108">In the **Promote Properties** dialog box, make sure the **Property Fields** tab is selected in the right side of the dialog box.</span></span> <span data-ttu-id="54278-109">接下来，请确保相应的属性架构包含在顶部的属性架构列表**属性字段**选项卡。如有必要，使用文件夹按钮通过选择适当的属性架构**BizTalk 类型选取器**对话框。</span><span class="sxs-lookup"><span data-stu-id="54278-109">Next, ensure the appropriate property schema is included in the Property Schemas List at the top of the **Property Fields** tab. If necessary, use the folder button to select the appropriate property schema by using the **BizTalk Type Picker** dialog box.</span></span> <span data-ttu-id="54278-110">接下来，展开以查找并选择对话框左侧的架构树中节点**Field 元素**节点或**字段特性**你想要将提升为的属性字段中，并依次的节点**添加**。</span><span class="sxs-lookup"><span data-stu-id="54278-110">Next, expand the nodes in the schema tree on the left side of the dialog box to find and select the **Field Element** node or **Field Attribute** node that you want to promote as a property field, and then click **Add**.</span></span> <span data-ttu-id="54278-111">最后，使用下拉列表中的**属性**列**属性字段字典**表选择**Field 元素**用于对属性架构中的节点将提升的属性相关联。</span><span class="sxs-lookup"><span data-stu-id="54278-111">Finally, use the drop-down list in the **Property** column of the **Property-Fields dictionary** table to select a **Field Element** node in a property schema with which to associate the promoted property.</span></span> <span data-ttu-id="54278-112">有关升级到使用的属性字段的属性的分步说明**升级属性**对话框 ox，请参阅[如何将数据复制到作为属性字段消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="54278-112">For step-by-step instructions about promoting properties to property fields using the **Promote Properties** dialog ox, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54278-113">你还可以升级**记录**节点**Field 元素**中属性的架构，但仅当节点**内容类型**属性**记录**节点设置为**SimpleContent**。</span><span class="sxs-lookup"><span data-stu-id="54278-113">You can also promote a **Record** node to a **Field Element** node in the property schema, but only if the **Content Type** property of the **Record** node is set to **SimpleContent**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54278-114">在一个架构中，可以对同一属性升级多次，只要所有这些升级都是在不同的根节点下进行即可。</span><span class="sxs-lookup"><span data-stu-id="54278-114">The same property can be promoted multiple times within a schema as long as all of these promotions are performed under different root nodes.</span></span> <span data-ttu-id="54278-115">这是因为消息是根据单个根节点进行验证的，只有在该根节点下升级的属性才会在运行时进行评估。</span><span class="sxs-lookup"><span data-stu-id="54278-115">This is because the message is validated against a single root node and only properties promoted under that root node are evaluated at run time.</span></span>  
  
 <span data-ttu-id="54278-116">若要删除**Field 元素**节点或**字段特性**节点的属性字段会提升的属性集从选择中的提升的属性**属性字段字典**表上**属性字段**选项卡上，并依次**删除**。</span><span class="sxs-lookup"><span data-stu-id="54278-116">To remove a **Field Element** node or **Field Attribute** node from the set of properties being promoted as property fields, select the promoted property in the **Property-Fields dictionary** table on the **Property Fields** tab, and then click **Remove**.</span></span>  
  
 <span data-ttu-id="54278-117">**节点路径**中的列**属性字段字典**表显示为对应于提升的属性的架构节点的 XPath。</span><span class="sxs-lookup"><span data-stu-id="54278-117">The **Node Path** column in the **Property-Fields dictionary** table shows the XPath to the schema node corresponding to the promoted property.</span></span> <span data-ttu-id="54278-118">你可以通过直接编辑此值**编辑实例 XPath**对话框。</span><span class="sxs-lookup"><span data-stu-id="54278-118">You can edit this value directly by using the **Edit Instance XPath** dialog box.</span></span> <span data-ttu-id="54278-119">你可以打开此对话框中，通过单击省略号 (**...**) 时选择该单元格将显示在相应的单元格右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="54278-119">You can open this dialog box by clicking the ellipsis (**...**) button that appears at the right end of the corresponding cell when you select that cell.</span></span> <span data-ttu-id="54278-120">在直接编辑 XPath 值时必须谨慎，因为如果 BizTalk 编辑器无法解析 XPath，则会妨碍相应的验证操作。</span><span class="sxs-lookup"><span data-stu-id="54278-120">Care must be taken when editing XPath values directly because XPaths that cannot be resolved by BizTalk Editor will prevent proper validation operations.</span></span>  
  
 <span data-ttu-id="54278-121">BizTalk 编辑器还提供简化的命令，可提升属性使用**属性字段**机制。</span><span class="sxs-lookup"><span data-stu-id="54278-121">BizTalk Editor also provides a streamlined command for promoting properties using the **Property Field** mechanism.</span></span> <span data-ttu-id="54278-122">此命令称为快速升级，它是可通过**Promote &#124;快速升级**BizTalk 和快捷菜单上的命令。</span><span class="sxs-lookup"><span data-stu-id="54278-122">This command is called Quick Promotion, and it is available using the **Promote &#124; Quick Promotion** command on the BizTalk and shortcut menus.</span></span> <span data-ttu-id="54278-123">此命令将升级所选**字段**节点 (或**记录**节点) 在指定的属性架构中自动创建的属性字段**默认属性架构名称**中的属性**属性页**包含架构的对话框。</span><span class="sxs-lookup"><span data-stu-id="54278-123">This command promotes the selected **Field** node (or **Record** node) to a property field that is automatically created in the property schema specified by the **Default Property Schema Name** property in the **Property Pages** dialog box for the containing schema.</span></span> <span data-ttu-id="54278-124">有关将升级到使用快速升级命令的属性字段的属性的分步说明，请参阅[如何将数据复制到作为属性字段消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="54278-124">For step-by-step instructions about promoting properties to property fields using the Quick Promotion command, see [How to Copy Data to the Message Context as Property Fields](../core/how-to-copy-data-to-the-message-context-as-property-fields.md).</span></span>  
  
 <span data-ttu-id="54278-125">在使用属性字段机制升级属性时，将会向消息架构的 XSD 表示形式中添加两个 XML 架构定义 (XSD) 语言片段。</span><span class="sxs-lookup"><span data-stu-id="54278-125">When you promote a property by using the property field mechanism, two XML Schema definition (XSD) language fragments are added to the XSD representation of the message schema.</span></span> <span data-ttu-id="54278-126">第一个 XSD 片段是与关联的批注片段**架构**标识相应的属性架构，如以下示例所示的元素：</span><span class="sxs-lookup"><span data-stu-id="54278-126">The first XSD fragment is an annotation fragment associated with the **schema** element that identifies the corresponding property schema, as in the following example:</span></span>  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:imports>  
            <b:namespace prefix="ns0"  
                uri="http://BizTalk_Server_Project1.PropertySchema1"  
                location=".\propertyschema1.xsd" />  
        </b:imports>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
 <span data-ttu-id="54278-127">第二个 XSD 片段是与关联的批注片段**根**（无论是否它已被重命名） 的元素，它标识**Field 元素**节点或**字段属性**已提升使用属性的节点值字段机制，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="54278-127">The second XSD fragment is an annotation fragment associated with the **Root** element (regardless of whether it has been renamed) that identifies the **Field Element** node or **Field Attribute** node values that have been promoted by using the property field mechanism, as in the following example:</span></span>  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:properties>  
            <b:property name="ns0:PromProp1"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/@*[local-  
                 name()='Field_x0020_1']" />  
            <b:property name="ns0:PromProp2"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/*[local-  
                 name()='ProgramManager']/*[local-name()='Name']" />  
        </b:properties>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54278-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54278-128">See Also</span></span>  
 <span data-ttu-id="54278-129">[使用与控件消息处理的消息内容的方法](../core/ways-to-use-message-content-to-control-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="54278-129">[Ways to Use Message Content to Control Message Processing](../core/ways-to-use-message-content-to-control-message-processing.md) </span></span>  
 [<span data-ttu-id="54278-130">如何将数据复制到作为属性字段的消息上下文</span><span class="sxs-lookup"><span data-stu-id="54278-130">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)