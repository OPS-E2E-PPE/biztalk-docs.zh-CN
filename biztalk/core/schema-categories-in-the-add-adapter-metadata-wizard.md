---
title: 中的架构类别添加适配器元数据向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927c676-f60a-449e-be43-6f75e28aefe1
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46fd9ffab7aa4f8617e08a18824cc251ad9f4173
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008006"
---
# <a name="schema-categories-in-the-add-adapter-metadata-wizard"></a>中的架构类别添加适配器元数据向导

## <a name="overview"></a>概述
> [!NOTE]
>  本主题仅适用于实现的静态适配器**IStaticAdapterConfig**接口。  
  
 适配器可能会使用任意一种成千上万的架构将数据转换之前将其传递给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 向某个 BizTalk 项目添加元数据时，使用“添加适配器元数据”向导可以从与适配器交互的所有架构的列表中选择所需架构。  
  
 在示例文件适配器中，CategorySchema.xml 文件是一个架构实例，它与适配器框架的 BiztalkAdapterFramework.xsd 文件一起用于填充服务架构的树视图组织。  BizTalkAdapterFramework.xsd 文件位于 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] Developer Tools 文件夹中。  
  
 应该创建此文件，以便按照对您的解决方案直观明了的方式来组织架构。 CategorySchema.xml 中的现有类别仅作为示例，向您演示您可以在自己的树中执行的操作。 这些类别与示例适配器所传递的数据没有任何特别的关联。 架构的组织方式对特定于应用程序的适配器尤为重要，适配器中可能包含成千上万的不同架构。 对于特定于传输的适配器，不必使用树视图组织。  
  
 下图显示**选择导入的服务**添加适配器元数据向导中的页。  
  
 ![](../core/media/ebiz-prog-custad-tree.gif "ebiz_prog_custad_tree")  
“添加适配器元数据”向导中的架构类别树视图  


## <a name="sample-xml"></a>示例 XML
  
 下面的代码显示 CategorySchema.xml 文件：  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<CategoryTree>  
     <DisplayName>Services Organization</DisplayName>  
     <DisplayDescription>An organization of application services</DisplayDescription>  
     <CategoryTreeNode>  
          <DisplayName>Health Care</DisplayName>  
          <Description>Services under Health Care</Description>  
          <CategoryTreeNode>  
               <DisplayName>Administrative</DisplayName>  
               <Description>Administrative Health Care Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Eligibility</DisplayName>  
                    <Description>Eligibility Verification Transactions</Description>  
                    <WSDLReference>ANSI X 12 270</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
     <CategoryTreeNode>  
          <DisplayName>Manufacturing</DisplayName>  
          <Description>Manufacturing Services</Description>  
          <CategoryTreeNode>  
               <DisplayName>Inventory</DisplayName>  
               <Description>Inventory Services</Description>  
               <ServiceTreeNode>  
                    <DisplayName>Requisition</DisplayName>  
                    <Description>Requisition</Description>  
                    <WSDLReference>RequisitionService</WSDLReference>  
               </ServiceTreeNode>  
          </CategoryTreeNode>  
     </CategoryTreeNode>  
</CategoryTree>  
```  
  
 此架构实例中存在下列节点类型：  
  
- **CategoryTree。** 模型的系统信息的顶级结构。 包含零个或多个 CategoryTreeNode、 ExpandableCategoryTreeNode 和 ServiceTreeNode 节点。  
  
- **CategoryTreeNode。** 包含零个或多个 CategoryTreeNode 和 ServiceTreeNode 节点。 使用显示文件夹中的用户界面 (UI) 将一组相关服务为 CategoryTreeNode。 通常，这包含显示名称和要显示的服务的描述。 如果子节点的数目较小，适配器可能使用 CategoryTreeNode。  
  
- **ExpandableCategoryTreeNode。** 展开时，将动态填充一个叶节点。 ExpandableCategoryTreeNode 用作占位符，并出现在 UI 中的文件夹。 这可以用于延迟填充具有子元素的类别节点，直到用户单击以展开的节点。 适配器可能会使用 ExpandableCategoryTreeNode，如果类别包含大量的子节点。  
  
- **ServiceTreeNode。** ServiceTreeNode 为文档或叶节点，在 UI 中的显示，表示 Web 服务描述语言 (WSDL) 文件。  
  
  当用户单击来展开一个节点的文件夹时，适配器框架将调用**IStaticAdapterConfig.GetServiceOrganization**作为值传递的节点名称的适配器上的方法**NodeIdentifier**属性。 适配器应返回包含子节点 CategoryTree，若要添加 ExpandableCategoryTreeNode 下。 适配器框架 ExpandableCategoryTreeNode 替换 CategoryTreeNode 并向其添加返回 CategoryTree 的子级。  
  
> [!NOTE]
>  在首次调用**IStaticAdapterConfig.GetServiceOrganization**适配器框架将传递的节点标识符为 null。 这将告知适配器返回根级别 CategoryTree。  
  
 下面是从 BiztalkAdapterFramework.xsd 文件中提取的类别树架构。 这是用来填充从 XML 文件的特定应用程序依赖于实体框架的树形使用添加适配器元数据向导。 在本例中该文件是 CategorySchema.xml 文件。  
  
```  
<!-- Service Organization Tree schema used by Add Adapter Wizard -->  
    <xs:element name="CategoryTree" type="CategoryTree" />  
    <xs:complexType name="CategoryTree">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="DisplayDescription" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ExpandableCategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
        </xs:sequence>  
        <xs:attribute name="NodeIdentifier" type="xs:string" use="required"></xs:attribute>  
    </xs:complexType>  
    <xs:complexType name="CategoryTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:choice minOccurs="0" maxOccurs="unbounded">  
                <xs:element name="ExpandableCategoryTreeNode" type="ExpandableCategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="CategoryTreeNode" type="CategoryTreeNode" minOccurs="0" maxOccurs="unbounded" />  
                <xs:element name="ServiceTreeNode" type="ServiceTreeNode" minOccurs="0" maxOccurs="unbounded" />  
            </xs:choice>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="ServiceTreeNode">  
        <xs:sequence>  
            <xs:element name="DisplayName" type="xs:string" />  
            <xs:element name="Description" type="xs:string" />  
            <xs:element name="WSDLReference" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:schema>  
```  
  
 之后修改 CategorySchema.xml 文件时，重新生成 AdapterManagement 项目，然后运行添加适配器元数据向导以确保正确显示 CategorySchema.xml 中表示的树。  
  
 有关运行添加适配器元数据向导的信息，请参阅**添加适配器元数据向导对话框** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。