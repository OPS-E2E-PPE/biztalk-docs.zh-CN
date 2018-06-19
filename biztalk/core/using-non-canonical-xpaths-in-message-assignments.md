---
title: 在消息分配中使用非规范 Xpath |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 052d1d72-43ce-4654-bf29-86f82ad65e91
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 201d6f8b6bc910faf79b64ac0b4617530b20608a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287621"
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a>在消息赋值中使用非规范化 XPath
如果使用 .Net 消息部分，则可以用 XML 序列化属性批注代码，不过，当代码中还附带可分辨字段和/或属性批注时，会使 XPath 表达式变得极其复杂。 这些复杂的 XPath 表达式可能是非规范化的。 非规范化 XPath 只能用于直接绑定的业务流程，如果用于逻辑绑定或物理绑定的业务流程，可能会失败。 直接绑定的业务流程不依赖管道来处理 XML 文档，因此在处理之前，整个 XML 文档已加载到内存中。  
  
## <a name="canonical-and-non-canonical-xpath"></a>规范和非规范 XPath  
 规范或短型 XPath 的使用与 XPath 规范中的缩写的语法 ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) 来指定的位置路径。 下面是规范化 XPath 表达式的一些判别属性：  
  
-   默认情况下，在表达式的每一步中都假定一个 `child::` 轴  
  
-   `@` 是 `attribute::` 的简写形式。  
  
-   `//` 是 `/descendant-or-self::node()/` 的简写形式。  
  
-   `.` 是 `self::node()` 的简写形式。  
  
-   `..` 是 `parent::node()` 的简写形式。  
  
 规范化 XPath 表达式是简单表达式，例如 `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`。  
  
 这与非规范化形式的 XPath 相反。 此窗体即所谓的"常规窗体"任意 XPath"，并区分的任意复杂，并且可以合并多个轴的表达式： `//element-name//*[local-name()='element-name' and position()=2]`。  
  
## <a name="example"></a>示例  
 以下面的程序为例：  
  
```  
using System;  
using System.IO;  
using System.Xml.Serialization;  
using Microsoft.XLANGs.BaseTypes;  
  
namespace ComplexNetXPath  
{  
    public class Animal  
    {  
        [Property( typeof(BTS.RetryCount) )]  
        public int NumberOfLegs;  
    }   
    public class Snake : Animal  
    {  
        public Snake()  
        {  
            NumberOfLegs = 0;  
        }  
    }   
    public class Dog : Animal  
    {  
        public Dog()  
        {  
            NumberOfLegs = 4;  
        }  
    }   
    public class Zoo  
    {  
        //  
        // Dogs and snakes are the possible animals of  
        // the week.  
        //  
        [XmlElement(typeof(Snake))]  
        [XmlElement(typeof(Dog))]  
        public Animal AnimalOfTheWeek;  
    }  
    class Class1  
    {  
        static void Main(string[] args)  
        {  
            XmlSerializer ser = new XmlSerializer(typeof(Zoo));  
            Stream s = Console.OpenStandardOutput();  
            Zoo z = new Zoo();  
            z.AnimalOfTheWeek = new Dog();  
            ser.Serialize( s, z );  
            s.Flush();  
            Console.WriteLine("------------------");  
            z.AnimalOfTheWeek = new Snake();  
            ser.Serialize( s, z );  
            s.Flush();  
        }  
    }  
}   
```  
  
 Zoo 类型包含一个 Animal 字段，它可以是 Snake 或 Dog。 Animal 实例有一个 NumberOfLegs 字段，用 PropertyAttribute 进行批注，将 BTS.RetryCount 属性分配给此字段。  
  
> [!NOTE]
>  实际的应用程序要定义自己的属性。  
  
 当本周动物是 Dog 时，序列化的 Zoo 实例如下所示：  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 当本周动物是 Snake 时，序列化的 Zoo 实例如下所示：  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 以与 .Net Zoo 类等价的 XML 架构为例，用于选择 RetryCount 属性的 XPath 表达式将允许 Snake 或 Dog 步骤显示在该属性的路径中：  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 XML 管道组件无法处理这种非规范化 XPath 表达式。 为了避免这种情况，请不要将多选择 XML 序列化属性与 XML 管道一起使用，在使用以下 XML 序列化属性时也应谨慎：  
  
-   XmlElementAttribute  
  
-   XmlAttributeAttribute  
  
-   XmlArrayItemAttribute