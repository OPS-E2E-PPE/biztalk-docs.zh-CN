---
title: "在消息分配中使用非规范 Xpath |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 052d1d72-43ce-4654-bf29-86f82ad65e91
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 201d6f8b6bc910faf79b64ac0b4617530b20608a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-non-canonical-xpaths-in-message-assignments"></a><span data-ttu-id="c6bf4-102">在消息赋值中使用非规范化 XPath</span><span class="sxs-lookup"><span data-stu-id="c6bf4-102">Using Non-Canonical XPaths in Message Assignments</span></span>
<span data-ttu-id="c6bf4-103">如果使用 .Net 消息部分，则可以用 XML 序列化属性批注代码，不过，当代码中还附带可分辨字段和/或属性批注时，会使 XPath 表达式变得极其复杂。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-103">If you use .Net message parts, it is possible to annotate your code with the XML serialization attribute that, when also accompanied by distinguished fields and/or property annotations, can result in fairly complex XPath expressions.</span></span> <span data-ttu-id="c6bf4-104">这些复杂的 XPath 表达式可能是非规范化的。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-104">It is possible that these complex XPath expressions will be non-canonical.</span></span> <span data-ttu-id="c6bf4-105">非规范化 XPath 只能用于直接绑定的业务流程，如果用于逻辑绑定或物理绑定的业务流程，可能会失败。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-105">Non-canonical XPath should only be used in direct bound orchestrations and may fail with logically or physically bound orchestrations.</span></span> <span data-ttu-id="c6bf4-106">直接绑定的业务流程不依赖管道来处理 XML 文档，因此在处理之前，整个 XML 文档已加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-106">Direct bound orchestrations do not rely on a pipeline for processing the XML document; as a result, the entire XML document is loaded in memory prior to processing.</span></span>  
  
## <a name="canonical-and-non-canonical-xpath"></a><span data-ttu-id="c6bf4-107">规范和非规范 XPath</span><span class="sxs-lookup"><span data-stu-id="c6bf4-107">Canonical and Non-Canonical XPath</span></span>  
 <span data-ttu-id="c6bf4-108">规范或短型 XPath 的使用与 XPath 规范中的缩写的语法 ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) 来指定的位置路径。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-108">The canonical or short-form of XPath uses the abbreviated syntax from the XPath specification ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) to specify a location path.</span></span> <span data-ttu-id="c6bf4-109">下面是规范化 XPath 表达式的一些判别属性：</span><span class="sxs-lookup"><span data-stu-id="c6bf4-109">Some distinguishing properties of canonical XPath expressions include:</span></span>  
  
-   <span data-ttu-id="c6bf4-110">默认情况下，在表达式的每一步中都假定一个 `child::` 轴</span><span class="sxs-lookup"><span data-stu-id="c6bf4-110">The `child::` axis is assumed by default for each step of the expression</span></span>  
  
-   <span data-ttu-id="c6bf4-111">`@` 是 `attribute::` 的简写形式。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-111">`@` is short for `attribute::`.</span></span>  
  
-   <span data-ttu-id="c6bf4-112">`//` 是 `/descendant-or-self::node()/` 的简写形式。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-112">`//` is short for `/descendant-or-self::node()/`.</span></span>  
  
-   <span data-ttu-id="c6bf4-113">`.` 是 `self::node()` 的简写形式。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-113">`.` is short for `self::node()`.</span></span>  
  
-   <span data-ttu-id="c6bf4-114">`..` 是 `parent::node()` 的简写形式。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-114">`..` is short for `parent::node()`.</span></span>  
  
 <span data-ttu-id="c6bf4-115">规范化 XPath 表达式是简单表达式，例如 `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-115">Canonical XPath expressions are simple expressions such as `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`.</span></span>  
  
 <span data-ttu-id="c6bf4-116">这与非规范化形式的 XPath 相反。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-116">This can be contrasted with the non-canonical form of XPath.</span></span> <span data-ttu-id="c6bf4-117">此窗体即所谓的"常规窗体"任意 XPath"，并区分的任意复杂，并且可以合并多个轴的表达式： `//element-name//*[local-name()='element-name' and position()=2]`。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-117">This form is also known as the "general form" or "arbitrary XPath" and is distinguished by expressions that are arbitrarily complex and may combine multiple axes: `//element-name//*[local-name()='element-name' and position()=2]`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6bf4-118">示例</span><span class="sxs-lookup"><span data-stu-id="c6bf4-118">Example</span></span>  
 <span data-ttu-id="c6bf4-119">以下面的程序为例：</span><span class="sxs-lookup"><span data-stu-id="c6bf4-119">Consider the following program:</span></span>  
  
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
  
 <span data-ttu-id="c6bf4-120">Zoo 类型包含一个 Animal 字段，它可以是 Snake 或 Dog。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-120">The Zoo type contains an Animal field that may be either a Snake or a Dog.</span></span> <span data-ttu-id="c6bf4-121">Animal 实例有一个 NumberOfLegs 字段，用 PropertyAttribute 进行批注，将 BTS.RetryCount 属性分配给此字段。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-121">The Animal instance has a NumberOfLegs field that is annotated with the PropertyAttribute which assigns the BTS.RetryCount property to this field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6bf4-122">实际的应用程序要定义自己的属性。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-122">A real application would define its own properties.</span></span>  
  
 <span data-ttu-id="c6bf4-123">当本周动物是 Dog 时，序列化的 Zoo 实例如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6bf4-123">When the animal of the week is a dog, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 <span data-ttu-id="c6bf4-124">当本周动物是 Snake 时，序列化的 Zoo 实例如下所示：</span><span class="sxs-lookup"><span data-stu-id="c6bf4-124">When the animal of the week is a snake, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 <span data-ttu-id="c6bf4-125">以与 .Net Zoo 类等价的 XML 架构为例，用于选择 RetryCount 属性的 XPath 表达式将允许 Snake 或 Dog 步骤显示在该属性的路径中：</span><span class="sxs-lookup"><span data-stu-id="c6bf4-125">Considering the Xml schema equivalent to the .Net Zoo class, the XPath expression for selecting the RetryCount property would allow for either a Snake or a Dog step to appear on the path to the property:</span></span>  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 <span data-ttu-id="c6bf4-126">XML 管道组件无法处理这种非规范化 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="c6bf4-126">The XML pipeline components cannot handle this non-canonical XPath expression.</span></span> <span data-ttu-id="c6bf4-127">为了避免这种情况，请不要将多选择 XML 序列化属性与 XML 管道一起使用，在使用以下 XML 序列化属性时也应谨慎：</span><span class="sxs-lookup"><span data-stu-id="c6bf4-127">To avoid this situation, multiple-choice Xml serialization attributes should not be used in conjunction with the XML pipelines and care should be taken when using the following xml serialization attributes:</span></span>  
  
-   <span data-ttu-id="c6bf4-128">XmlElementAttribute</span><span class="sxs-lookup"><span data-stu-id="c6bf4-128">XmlElementAttribute</span></span>  
  
-   <span data-ttu-id="c6bf4-129">XmlAttributeAttribute</span><span class="sxs-lookup"><span data-stu-id="c6bf4-129">XmlAttributeAttribute</span></span>  
  
-   <span data-ttu-id="c6bf4-130">XmlArrayItemAttribute</span><span class="sxs-lookup"><span data-stu-id="c6bf4-130">XmlArrayItemAttribute</span></span>