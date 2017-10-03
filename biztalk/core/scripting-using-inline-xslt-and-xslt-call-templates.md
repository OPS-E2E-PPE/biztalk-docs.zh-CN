---
title: "脚本使用内联 XSLT 和 XSLT 调用模板 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3168417-3653-4c9e-a09c-184ffdc0ccb2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7c4c1d8eff582d15f9ce022053b80f2dea2f856
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-using-inline-xslt-and-xslt-call-templates"></a>脚本使用内联 XSLT 和 XSLT 调用模板
你可以直接编写用于可扩展样式表语言转换 (XSLT) 样式表**脚本**functoid。 这样，您就可以执行链接和内置 functoid 可能无法表示的转换。 XSLT 脚本有两种类型：内联 XSLT 和 XSLT 调用模板。 当你选择在**选择脚本类型**中的下拉列表**配置脚本 Functoid**对话框中，示例代码将显示您可以使用。  
  
 内联 XSLT 脚本和内联 XSLT 调用模板可以调用外部程序集中的函数。 进行此类调用需要设置**自定义扩展 XML**网格的属性。 有关详细信息，请参阅**自定义扩展 XML （网格属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="inline-xslt"></a>内联 XSLT  
 内联 XSLT 脚本只能生成输出。 **脚本**functoid 可能没有任何输入的链接。 该 functoid 还必须直接链接到目标架构中的记录或字段。  
  
 此外，该脚本还用于创建目标节点及其任何下级结构。  
  
 以下输入实例消息包含表示联系人信息的两个元素：  
  
```  
<ns0:SourceInstance xmlns:ns0="http://SourceInstanceNamespace">  
    <Address>  
        <Contact>Karin Zimprich</Contact>  
        <ContactType>Referral</ContactType>  
    </Address>  
</ns0:SourceInstance>  
```  
  
 以下的内联 XSLT 脚本，在脚本缓冲区中，输入将转换**联系人**和**ContactType**字段添加到属性。  
  
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
  
 如果具有适当的输出架构，那么，在针对前面的输入实例消息运行时，该脚本将生成以下输出：  
  
```  
<ns0:OutInstance xmlns:ns0="http://More_XSLT.Out">  
    <ContactInfo ContactType="Referral" Contact="Karin Zimprich" xmlns:p="http://SourceInstanceNamespace">  
    </ContactInfo>  
</ns0:OutInstance>  
```  
  
 请注意，指向没有**脚本**functoid 不会阻止 XSLT 脚本从输入的实例消息中获取数据。 该脚本指定了输入实例值的路径。  
  
 有关内联 XSLT 脚本的另一个示例，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="inline-xslt-call-templates"></a>内联 XSLT 调用模板  
 与内联 XSLT 脚本类似，内联 XSLT 调用模板必须直接连接到目标节点。 不过，内联 XSLT 调用模板可以使用源自源架构和其他 functoid 的链接。  
  
 调用模板用于创建目标节点及其任何子结构。  
  
 连接两个元素的示例 XSLT 调用模板出现在**输入脚本**时你选择缓冲**内联 XSLT 调用模板**中**选择脚本类型**下拉列表。  
  
 有关内联 XSLT 调用模板的另一个示例，请参阅[（BizTalk Server 示例文件夹中） 的 XML 工具](../core/xml-tools-biztalk-server-samples-folder.md)。  
  
## <a name="see-also"></a>另请参阅  
 [脚本 Functoid](../core/scripting-functoid.md)   
 [脚本使用外部程序集](../core/scripting-using-external-assemblies.md)   
 [脚本使用内联 C#、 JScript.NET 和 Visual Basic.NET](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [如何在向地图添加脚本 Functoid](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)