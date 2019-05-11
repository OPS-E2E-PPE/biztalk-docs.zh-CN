---
title: 如何导入 BPEL4WS |Microsoft Docs
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
ms.openlocfilehash: d52dba33e4dadb788cca4ba60969989967fd9532
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384984"
---
# <a name="import-bpel4ws-in-biztalk-server"></a>在 BizTalk Server 中导入 BPEL4WS
您可以从现有的 BPEL4WS，若要创建一个业务流程导入。  
  
> [!IMPORTANT]
>  此版本的 BizTalk Server 支持 BPEL4WS 1.1。 无法导入或导出 BPEL4WS 1.0。  
  
 有关如何导入 BPEL4WS 的示例，请参阅[BPEL 导入 （BizTalk Server 示例）](../core/bpel-import-biztalk-server-sample.md)。  
  
## <a name="import-bpel4ws-into-an-orchestration"></a>导入 BPEL4WS 到业务流程  
  
1. 创建一个新的项目。  
  
2. 从 BizTalk 项目类型中，双击 BizTalk Server BPEL 导入项目，或选择 BizTalk Server BPEL 导入项目，然后按确定。  
  
3. 在向导中，选择要导入以形成新的 BizTalk 项目的 BPEL、 WSDL 和 XSD 文件。 包括通过导入引用和 include 语句的所有文件。  
  
4. 选择为调用 Web 服务的 WSDL 文件。  
  
    现在可以修改或部署新的业务流程。  
  
   **导入对 BPEL4WS 的限制**  
  
-   在导入 BPEL 和 WSDL，请确保 WSDL 定义节点和 BPEL 过程节点的 Name 属性不匹配。  
  
-   不要在您导入的 BPEL4WS 中使用 XLANG/s 保留字。 有关完整列表，请参阅[XLANG/s 保留字](../core/xlang-s-reserved-words.md)。  
  
-   支持预定义的 XSD 简单类型。  
  
-   不支持 xsd: qname;它将作为 System.String 导入。 改为使用 xsd: string。  
  
-   请考虑导入 BPEL4WS 时使用规范化的 XPaths。  
  
     它是很好的做法导入规范化的 XPaths，以便获得最佳性能。 从根到升级节点的整个路径必须使用拼写 / * [local-name ="someName"和命名空间 uri （） ="someUri"]。  
  
     如果导入非规范化 XPath，可以删除升级，以便让架构编辑器创建正确的规范化 XPath 重新升级相同字段。  
  
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
    |BizTalk 编辑器将显示一个特殊的图标 (![](../core/media/ebiz-orch-promotedprop.gif "ebiz_orch_promotedprop")) 来表示字段已升级。 使用情况的规范化 XPath 表达式将字段升级可以提高性能通过更有效地遍历 XML|BizTalk 编辑器不显示特殊图标。 编译器和升级对话框发出警告。 没有对消息大小增加时的性能的线性明显影响。|  
  
## <a name="see-also"></a>请参阅  
 [如何导出 BPEL4WS](../core/how-to-export-bpel4ws.md)   
 [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)
