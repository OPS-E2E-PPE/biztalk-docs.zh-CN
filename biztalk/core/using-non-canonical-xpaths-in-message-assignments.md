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
# <a name="using-non-canonical-xpaths-in-message-assignments"></a><span data-ttu-id="8f2bd-102">在消息赋值中使用非规范化 Xpath</span><span class="sxs-lookup"><span data-stu-id="8f2bd-102">Using Non-Canonical XPaths in Message Assignments</span></span>
<span data-ttu-id="8f2bd-103">如果使用.Net 消息部分，就可以进行批注您用 XML 序列化属性的代码，当还附带可分辨的字段和/或属性批注，可能会导致相当复杂的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-103">If you use .Net message parts, it is possible to annotate your code with the XML serialization attribute that, when also accompanied by distinguished fields and/or property annotations, can result in fairly complex XPath expressions.</span></span> <span data-ttu-id="8f2bd-104">很可能会不规范这些复杂的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-104">It is possible that these complex XPath expressions will be non-canonical.</span></span> <span data-ttu-id="8f2bd-105">非规范化 XPath 只能用于直接绑定的业务流程中，可能会因逻辑或物理方式绑定的业务流程。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-105">Non-canonical XPath should only be used in direct bound orchestrations and may fail with logically or physically bound orchestrations.</span></span> <span data-ttu-id="8f2bd-106">直接绑定的业务流程，不要依赖于用于处理 XML 文档; 的管道因此，在处理之前的内存中加载整个 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-106">Direct bound orchestrations do not rely on a pipeline for processing the XML document; as a result, the entire XML document is loaded in memory prior to processing.</span></span>  
  
## <a name="canonical-and-non-canonical-xpath"></a><span data-ttu-id="8f2bd-107">规范的非规范化 XPath</span><span class="sxs-lookup"><span data-stu-id="8f2bd-107">Canonical and Non-Canonical XPath</span></span>  
 <span data-ttu-id="8f2bd-108">规范或简短形式的 XPath 使用 XPath 规范中的缩写的语法 ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) 来指定位置的路径。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-108">The canonical or short-form of XPath uses the abbreviated syntax from the XPath specification ([http://www.w3.org/TR/xpath](http://go.microsoft.com/fwlink/?LinkId=119567)) to specify a location path.</span></span> <span data-ttu-id="8f2bd-109">规范化 XPath 表达式的一些判别属性包括：</span><span class="sxs-lookup"><span data-stu-id="8f2bd-109">Some distinguishing properties of canonical XPath expressions include:</span></span>  
  
- <span data-ttu-id="8f2bd-110">`child::`轴假定默认情况下，每个步骤的表达式</span><span class="sxs-lookup"><span data-stu-id="8f2bd-110">The `child::` axis is assumed by default for each step of the expression</span></span>  
  
- <span data-ttu-id="8f2bd-111">`@` 是的缩写`attribute::`。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-111">`@` is short for `attribute::`.</span></span>  
  
- <span data-ttu-id="8f2bd-112">`//` 是的缩写`/descendant-or-self::node()/`。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-112">`//` is short for `/descendant-or-self::node()/`.</span></span>  
  
- <span data-ttu-id="8f2bd-113">`.` 是的缩写`self::node()`。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-113">`.` is short for `self::node()`.</span></span>  
  
- <span data-ttu-id="8f2bd-114">`..` 是的缩写`parent::node()`。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-114">`..` is short for `parent::node()`.</span></span>  
  
  <span data-ttu-id="8f2bd-115">规范化 XPath 表达式是简单表达式，如`/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-115">Canonical XPath expressions are simple expressions such as `/*[local-name()='element-name' and namespaceURI()='http://MyUri.org']/*[local-name()='element-name']/@*[local-name='attribute-name']`.</span></span>  
  
  <span data-ttu-id="8f2bd-116">这可以与非规范化形式的 XPath 相反。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-116">This can be contrasted with the non-canonical form of XPath.</span></span> <span data-ttu-id="8f2bd-117">此窗体即所谓的"一般形式"任意 XPath"，其特点是由表达式的任意复杂，并且可以包含多个轴： `//element-name//*[local-name()='element-name' and position()=2]`。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-117">This form is also known as the "general form" or "arbitrary XPath" and is distinguished by expressions that are arbitrarily complex and may combine multiple axes: `//element-name//*[local-name()='element-name' and position()=2]`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f2bd-118">示例</span><span class="sxs-lookup"><span data-stu-id="8f2bd-118">Example</span></span>  
 <span data-ttu-id="8f2bd-119">请考虑以下程序：</span><span class="sxs-lookup"><span data-stu-id="8f2bd-119">Consider the following program:</span></span>  
  
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
  
 <span data-ttu-id="8f2bd-120">Zoo 类型包含一个 Animal 字段，它可以是 Snake 或 Dog。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-120">The Zoo type contains an Animal field that may be either a Snake or a Dog.</span></span> <span data-ttu-id="8f2bd-121">Animal 实例有一个 NumberOfLegs 字段，使用将分配 BTS PropertyAttribute 进行批注。RetryCount 属性设置为此字段。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-121">The Animal instance has a NumberOfLegs field that is annotated with the PropertyAttribute which assigns the BTS.RetryCount property to this field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f2bd-122">实际的应用程序定义自己的属性。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-122">A real application would define its own properties.</span></span>  
  
 <span data-ttu-id="8f2bd-123">当本周动物是 dog 时，序列化的 Zoo 实例如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f2bd-123">When the animal of the week is a dog, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Dog>  
    <NumberOfLegs>4</NumberOfLegs>  
  </Dog>  
</Zoo>   
```  
  
 <span data-ttu-id="8f2bd-124">当本周动物是 snake 时，序列化的 Zoo 实例如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f2bd-124">When the animal of the week is a snake, the serialized Zoo instance looks like this:</span></span>  
  
```  
<Zoo>  
  <Snake>  
    <NumberOfLegs>0</NumberOfLegs>  
  </Snake>  
</Zoo>  
```  
  
 <span data-ttu-id="8f2bd-125">考虑 Xml 架构与.Net Zoo 类，用于选择 RetryCount 属性的 XPath 表达式将允许 Snake 或 Dog 步骤显示在属性的路径上：</span><span class="sxs-lookup"><span data-stu-id="8f2bd-125">Considering the Xml schema equivalent to the .Net Zoo class, the XPath expression for selecting the RetryCount property would allow for either a Snake or a Dog step to appear on the path to the property:</span></span>  
  
```  
/*[local-name()='Zoo' and namespace-uri()='']/*[(local-name()='Dog' and namespace-uri()='') or (local-name()='Snake' and namespace-uri()='')]/*[local-name()='NumberOfLegs' and namespace-uri()='']  
```  
  
 <span data-ttu-id="8f2bd-126">XML 管道组件无法处理此非规范化 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="8f2bd-126">The XML pipeline components cannot handle this non-canonical XPath expression.</span></span> <span data-ttu-id="8f2bd-127">若要避免这种情况下，进行多项选择 Xml 序列化属性不应在与 XML 管道一起使用，并使用以下 xml 序列化属性时应小心：</span><span class="sxs-lookup"><span data-stu-id="8f2bd-127">To avoid this situation, multiple-choice Xml serialization attributes should not be used in conjunction with the XML pipelines and care should be taken when using the following xml serialization attributes:</span></span>  
  
-   <span data-ttu-id="8f2bd-128">XmlElementAttribute</span><span class="sxs-lookup"><span data-stu-id="8f2bd-128">XmlElementAttribute</span></span>  
  
-   <span data-ttu-id="8f2bd-129">XmlAttributeAttribute</span><span class="sxs-lookup"><span data-stu-id="8f2bd-129">XmlAttributeAttribute</span></span>  
  
-   <span data-ttu-id="8f2bd-130">XmlArrayItemAttribute</span><span class="sxs-lookup"><span data-stu-id="8f2bd-130">XmlArrayItemAttribute</span></span>