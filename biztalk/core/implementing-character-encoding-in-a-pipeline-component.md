---
title: "实现管道组件中的字符编码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], encoding
ms.assetid: 862b56da-ec14-41f9-b63c-42d81124e167
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1bc95dc44fa4a4905affaad969c248aa4b76d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-character-encoding-in-a-pipeline-component"></a><span data-ttu-id="82131-102">实现管道组件中的字符编码</span><span class="sxs-lookup"><span data-stu-id="82131-102">Implementing Character Encoding in a Pipeline Component</span></span>
<span data-ttu-id="82131-103">若要支持自定义的字符编码，必须实现自定义编码类通过从 Microsoft.NET Framework 派生**编码**类，然后通过从标准的平面继承来创建自定义的平面文件管道组件文件反汇编程序或平面文件汇编器组件。</span><span class="sxs-lookup"><span data-stu-id="82131-103">To support custom character encoding, you must implement a custom encoding class by deriving from the Microsoft .NET Framework **Encoding** class, then create a custom flat file pipeline component by inheriting from the standard Flat File Disassembler or Flat File Assembler component.</span></span> <span data-ttu-id="82131-104">你可以通过重写受保护的虚方法提供的新的编码实例到分析引擎**FFDasmComp.GetDataReader**下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="82131-104">You can supply a new encoding instance to the parsing engine by overriding the protected virtual method **FFDasmComp.GetDataReader** as shown in the following example.</span></span>  
  
```  
/// <summary>  
/// Gets a data reader instance  
/// </summary>  
/// <param name="dataStream">Data stream</param>  
/// <param name="dataEncoding">Data encoding</param>  
/// <param name="detectEncodingFromByteOrderMarks">Detect encoding from a byte order mark</param>  
/// <returns>IDataReader instance</returns>  
      protected override IDataReader GetDataReader(Stream dataStream, Encoding dataEncoding, bool detectEncodingFromByteOrderMarks)  
      {  
         // Delegate call to the base implementation passing fixed UTF-7 encoding  
         return base.GetDataReader(dataStream, new CustomEncoding(), false);  
      }  
```  
  
## <a name="using-predefined-encoding-classes"></a><span data-ttu-id="82131-105">使用预定义编码类</span><span class="sxs-lookup"><span data-stu-id="82131-105">Using predefined encoding classes</span></span>  
 <span data-ttu-id="82131-106">下面的编码类型是 Microsoft .NET Framework 预定义的，可用于构造解析程序：</span><span class="sxs-lookup"><span data-stu-id="82131-106">The following encoding types are predefined by the Microsoft .NET Framework and can be used to construct the parser:</span></span>  
  
-   <span data-ttu-id="82131-107">ASCII</span><span class="sxs-lookup"><span data-stu-id="82131-107">ASCII</span></span>  
  
-   <span data-ttu-id="82131-108">UTF7</span><span class="sxs-lookup"><span data-stu-id="82131-108">UTF7</span></span>  
  
-   <span data-ttu-id="82131-109">UTF8</span><span class="sxs-lookup"><span data-stu-id="82131-109">UTF8</span></span>  
  
-   <span data-ttu-id="82131-110">Unicode (UTF16)</span><span class="sxs-lookup"><span data-stu-id="82131-110">Unicode (UTF16)</span></span>  
  
```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.UTF8));  
```  
  
## <a name="using-supported-code-pages"></a><span data-ttu-id="82131-111">使用受支持的代码页</span><span class="sxs-lookup"><span data-stu-id="82131-111">Using supported code pages</span></span>  
 <span data-ttu-id="82131-112">使用以下代码来支持 Shift-JIS（代码页 932）。</span><span class="sxs-lookup"><span data-stu-id="82131-112">Use the following code to support Shift-JIS (codepage 932).</span></span>  
  

```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.GetEncoding(932)));  
```  
  
## <a name="using-a-private-encoding-class"></a><span data-ttu-id="82131-113">使用私有编码类</span><span class="sxs-lookup"><span data-stu-id="82131-113">Using a private encoding class</span></span>  
 <span data-ttu-id="82131-114">你可以创建您自己的编码类派生自**System.Text.Encoding**抽象类，并执行你自己的编码和解码。</span><span class="sxs-lookup"><span data-stu-id="82131-114">You can create your own encoding class that derives from the **System.Text.Encoding** abstract class and perform your own encoding and decoding.</span></span>  
  
```  
class MyEncoding : System.Text.Encoding  
{  
   // overriding methods omitted  
}  
  
XmlReader xr = docspec.Parser(new DataReader(new MyEncoding()));  
```  
  
## <a name="using-a-private-datareader-class"></a><span data-ttu-id="82131-115">使用私有 DataReader 类</span><span class="sxs-lookup"><span data-stu-id="82131-115">Using a private DataReader class</span></span>  

 <span data-ttu-id="82131-116">你可以创建自己[DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx)类，该类实现`IDataReader`接口，并且没有创建任何编码类执行读取。</span><span class="sxs-lookup"><span data-stu-id="82131-116">You can create your own [DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx) class that implements the `IDataReader` interface and performs reading without creating any encoding classes.</span></span>  
  
```  
class MyDataReader : IDataReader  
{  
   // Implement data reader functions  
   // ...  
}  
  
XmlReader xr = docspec.Parse(new MyDataReader());  
```  
  
## <a name="see-also"></a><span data-ttu-id="82131-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82131-117">See Also</span></span>  
 [<span data-ttu-id="82131-118">使用了分析和序列化引擎</span><span class="sxs-lookup"><span data-stu-id="82131-118">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)