---
title: 如何导入 BPEL4WS |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3626fcb9-8e7d-4812-a0c9-bde6e7954ec8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e82dd80e280eff39ff5c1678b5c9751e378ee1b
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="import-bpel4ws-in-biztalk-server"></a>BizTalk Server 中的导入 BPEL4WS
可以从现有的 BPEL4WS 进行导入以创建业务流程。  
  
> [!IMPORTANT]
>  此版本的 BizTalk Server 支持 BPEL4WS 1.1。 无法导入或导出 BPEL4WS 1.0。  
  
 有关如何导入 BPEL4WS 的示例，请参阅[BPEL 导入 （BizTalk Server 示例）](../core/bpel-import-biztalk-server-sample.md)。  
  
## <a name="import-bpel4ws-into-an-orchestration"></a>导入 BPEL4WS 到业务流程  
  
1.  创建一个新的项目。  
  
2.  在 BizTalk 项目类型中，双击“BizTalk Server BPEL 导入项目”，或选择“BizTalk Server BPEL 导入项目”，然后按“确定”。  
  
3.  在向导中，选择要导入以形成新的 BizTalk 项目的 BPEL、WSDL 和 XSD 文件。 包括通过 import 和 include 语句引用的所有文件。  
  
4.  为所调用的 Web Services 选择 WSDL 文件。  
  
     现在，您可以修改或部署新的业务流程。  
  
 **导入 BPEL4WS 的限制**  
  
-   在导入 BPEL 和 WSDL 时，请确保 WSDL 定义节点和 BPEL 过程节点的 Name 属性不匹配。  
  
-   不要在导入的 BPEL4WS 中使用 XLANG/s 保留字。 完整列表，请参阅[XLANG/s 保留字](../core/xlang-s-reserved-words.md)。  
  
-   仅支持 XSD 预定义的简单类型。  
  
-   不支持 xsd:QName;它是作为 System.String 导入。 改为使用 xsd: string。  
  
-   请考虑在导入 BPEL4WS 时使用规范化的 XPaths。  
  
     最好只导入规范化的 XPaths，以便获得最佳性能。 必须通过使用“/*[local-name()="someName" and namespace-uri()="someUri"]”将从根到升级节点的完整路径拼写出来。  
  
     如果导入非规范化的 XPath，则可以删除升级并重新升级相同字段，以便让架构编辑器创建正确的规范化 XPath。  
  
     示例: (targetNamespace = http://BizTalk_Server_Project3.Schema1)  
  
    ```  
    <element name=Root type=complexType>  
                <sequence>  
                            <element name=promotedField/>  
                </sequence>  
    </element>  
    ```  
  
     `XPath - /*[local-name()='Root' and namespace-uri()='http://BizTalk_Server_Project3.Schema1']/\*[local-name()='promotedField' and namespace-uri()='']` 
  
    |规范化 XPath|非规范化 XPath|  
    |---------------------|--------------------------|  
    |BizTalk 编辑器将显示一个特殊图标 (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) 来表示字段已被提升。 如果使用规范化 XPath 表达式升级字段，则可以通过更有效地遍历 XML 来改进性能。|BizTalk 编辑器不显示特殊图标。 编译器和升级对话框都会发出警告。 随着消息大小的增长，会对性能产生明显的线性影响。|  
  
## <a name="see-also"></a>另请参阅  
 [如何导出 BPEL4WS](../core/how-to-export-bpel4ws.md)   
 [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)
