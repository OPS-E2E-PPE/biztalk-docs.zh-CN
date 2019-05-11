---
title: 使用内联 XSLT 和 XSLT 调用模板编写脚本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5df34bc134b9cb842d4ebc0db96f00a3716ee5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251241"
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a>使用内联 XSLT 和 XSLT 调用模板编写脚本
您可以直接编写可扩展样式表语言转换 (XSLT) 样式表中使用**脚本**functoid。 这使您可以执行转换，链接和内置 functoid 可能无法表示。 有两种类型的 XSLT 脚本： 内联 XSLT 和 XSLT 调用模板。 在选中**选择脚本类型**下拉列表中的**配置脚本 Functoid**对话框中，示例代码将显示您可以使用。  
  
 内联 XSLT 脚本和内联 XSLT 调用模板可以调用外部程序集中的函数。 执行此类调用需要设置**自定义扩展 XML**网格的属性。 有关详细信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="inline-xslt"></a>内联 XSLT  
 内联 XSLT 脚本只能生成输出。 **脚本**functoid 可能没有任何输入的链接。 该 functoid 必须直接链接到的记录或目标架构中的字段。  
  
 此外，该脚本负责创建目标节点及其任何下级结构。  
  
 以下输入的实例消息包含两个元素代表的联系信息。  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 以下内联 XSLT 脚本，在脚本缓冲区中，输入将转换**联系人**并**ContactType**属性字段。  
  
```  
<ContactInfo xmlns:p="http://SourceInstanceNamespace">  
     <xsl:variable name="var:var1" select="/p:SourceInstance/Address/ContactType" />  
     <xsl:attribute name="ContactType">  
          <xsl:value-of select="$var:var1" />  
     </xsl:attribute>  
     <xsl:variable name="var:var2" select="/p:SourceInstance/Address/Contact" />  
     <xsl:attribute name="Contact">  
          <xsl:value-of select="$var:var2" />  
     </xsl:attribute>  
</ContactInfo>  
```  
  
 该脚本生成以下输出，假定针对前面的输入的实例消息运行时的相应的输出架构。  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 请注意，不存在指向**脚本**functoid 不会妨碍该 XSLT 脚本从输入的实例消息中获取数据。 该脚本指定的输入的实例值的路径。  
  
 有关内联 XSLT 脚本的其他示例，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="inline-xslt-call-templates"></a>内联 XSLT 调用模板  
 内联 XSLT 脚本，如内联 XSLT 调用模板必须直接连接到目标节点。 但是，内联 XSLT 调用模板可能会使用来自源架构和来自其他 functoid 的链接。  
  
 调用模板是用于创建目标节点及其任何子结构。  
  
 串联两个元素的示例 XSLT 调用模板中显示**输入脚本**缓冲选择时**内联 XSLT 调用模板**中**选择脚本类型**下拉列表。  
  
 有关内联 XSLT 调用模板的其他示例，请参阅[XML 工具 （BizTalk Server 示例文件夹）](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="see-also"></a>请参阅  
 [脚本 Functoid](../core/scripting-functoid.md)   
 [使用外部程序集编写脚本](../core/scripting-using-external-assemblies.md)   
 [使用内联 C#、 JScript.NET 和 Visual Basic.NET 编写脚本](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [如何向映射添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)