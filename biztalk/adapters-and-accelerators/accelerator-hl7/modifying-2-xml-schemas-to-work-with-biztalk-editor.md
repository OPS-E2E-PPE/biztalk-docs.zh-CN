---
title: "修改 2.XML 架构，以使用 BizTalk 编辑器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, modifying
- modifying, 2.XML schemas
ms.assetid: 07316826-84b6-494e-81b9-f64a3d46ffb0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf68f39e4e4c36587b889490b28541e5a690ed05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="modifying-2xml-schemas-to-work-with-biztalk-editor"></a>修改要使用 BizTalk 编辑器的 2.XML 架构
HL7 2.XML 架构需要进行修改以正确使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。 下面描述如何修改 HL7 V2。要使您能够使用它们使用 BizTalk 编辑器的 XML 架构。  
  
> [!IMPORTANT]
>  Update2XMLSchema 工具会自动执行以下步骤。 请参阅[Update2XMLSchema 工具](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)有关详细信息。  
  
> [!NOTE]
>  **Nillable**属性会导致在元素上的架构。 如果设置为**true**，它指示父元素的实例可以具有**xsi: nil ="true"**属性。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在编译和分析/序列化期间，将忽略此属性。  
  
### <a name="to-modify-2xml-schemas"></a>若要修改 2.XML 架构  
  
1.  在 fields.xsd 文件中，你必须删除的实例**导入**和将其替换为**包括**。 例如，搜索以下文本的 fields.xsd 文件：  
  
    ```  
    <xsd:import namespace="urn:hl7-org:v2xml" schemaLocation="datatypes.xsd"/>   
    ```  
  
     并将文本更改为以下：  
  
    ```  
    <xsd:include schemaLocation="datatypes.xsd"/>   
    ```  
  
2.  在 segments.xsd 文件中，你必须删除包含文本 processcontents 的限制性的行的所有实例 ="宽松"。 例如，搜索以下文本的 segments.xsd 文件：  
  
    ```  
    <xsd:any processContents="lax" namespace="##any" minOccurs="0"/>   
    ```  
  
     And  
  
    ```  
    <xsd:any processContents="lax" namespace="##any"/>   
    ```  
  
     并删除这些行。  
  
3.  对于所有的架构，在标记 xsd:schema 中，你必须添加以下行：  
  
    > [!NOTE]
    >  不要添加此行，如果你已添加架构使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]因为[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]自动为你执行此。  
  
    ```  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    ```  
  
     例如，在文件 ADT_A01.xsd 中搜索以下文本：  
  
    ```  
    <xsd:schema  
     xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns="urn:hl7-org:v2xml"   
     targetNamespace="urn:hl7-org:v2xml">   
    ```  
  
     并将文本更改为以下：  
  
    ```  
    <xsd:schema  
     xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
     xmlns="urn:hl7-org:v2xml"  
     targetNamespace="urn:hl7-org:v2xml"  
     xmlns:b="http://schemas.microsoft.com/BizTalk/2003">   
    ```  
  
4.  对于所有的架构，必须添加根引用。 例如，在 ADT_A01.xsd 文件中，搜索以下文本：  
  
    ```  
    <xsd:include schemaLocation="segments.xsd" />   
    ```  
  
     并将更改为文本：  
  
    ```  
    <xsd:include schemaLocation="segments.xsd" />  
    <xsd:annotation>   
      <xsd:appinfo>   
        <schemaInfo root_reference="ADT_A01"  
     xmlns="http://schemas.microsoft.com/BizTalk/2003" />   
      </xsd:appinfo>   
    </xsd:annotation>   
    ```  
  
    > [!NOTE]
    >  如果你使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你可以使用以下过程来添加此 root_reference。  
  
### <a name="to-add-the-root-reference"></a>若要添加根引用  
  
1.  在解决方案资源管理器中双击你想要编辑的架构。  
  
2.  在属性窗格中，向下滚动属性**root_reference**，从下拉列表中，单击具有相同的架构名称的属性。  
  
3.  在“文件”  菜单上，单击“全部保存” 。  
  
## <a name="see-also"></a>另请参阅  
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)