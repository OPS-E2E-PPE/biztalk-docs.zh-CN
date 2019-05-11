---
title: 消息赋值中使用非规范化的 XPaths |Microsoft Docs
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
ms.openlocfilehash: 2402b3b95e9eb12d3362f018a197dc6cbc602020
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395403"
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a>在消息赋值中使用非规范化 Xpath
如果使用.Net 消息部分，就可以进行批注您用 XML 序列化属性的代码，当还附带可分辨的字段和/或属性批注，可能会导致相当复杂的 XPath 表达式。 很可能会不规范这些复杂的 XPath 表达式。 非规范化 XPath 只能用于直接绑定的业务流程中，可能会因逻辑或物理方式绑定的业务流程。 直接绑定的业务流程，不要依赖于用于处理 XML 文档; 的管道因此，在处理之前的内存中加载整个 XML 文档。  
  
## <a name="canonical-and-non-canonical-xpath"></a>规范的非规范化 XPath  
 规范或简短形式的 XPath 使用 XPath 规范中的缩写的语法 ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) 来指定位置的路径。 规范化 XPath 表达式的一些判别属性包括：  
  
- `child::`轴假定默认情况下，每个步骤的表达式  
  
- `@` 是的缩写`attribute::`。  
  
- `//` 是的缩写`/descendant-or-self::node()/`。  
  
- `.` 是的缩写`self::node()`。  
  
- `..` 是的缩写`parent::node()`。  
  
  规范化 XPath 表达式是简单表达式，如`/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`。  
  
  这可以与非规范化形式的 XPath 相反。 此窗体即所谓的"一般形式"任意 XPath"，其特点是由表达式的任意复杂，并且可以包含多个轴： `//element-name//*[local-name()='element-name' and position()=2]`。  
  
## <a name="example"></a>示例  
 请考虑以下程序：  
  
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
  
 Zoo 类型包含一个 Animal 字段，它可以是 Snake 或 Dog。 Animal 实例有一个 NumberOfLegs 字段，使用将分配 BTS PropertyAttribute 进行批注。RetryCount 属性设置为此字段。  
  
> [!NOTE]
>  实际的应用程序定义自己的属性。  
  
 当本周动物是 dog 时，序列化的 Zoo 实例如下所示：  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 当本周动物是 snake 时，序列化的 Zoo 实例如下所示：  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 考虑 Xml 架构与.Net Zoo 类，用于选择 RetryCount 属性的 XPath 表达式将允许 Snake 或 Dog 步骤显示在属性的路径上：  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 XML 管道组件无法处理此非规范化 XPath 表达式。 若要避免这种情况下，进行多项选择 Xml 序列化属性不应在与 XML 管道一起使用，并使用以下 xml 序列化属性时应小心：  
  
-   XmlElementAttribute  
  
-   XmlAttributeAttribute  
  
-   XmlArrayItemAttribute