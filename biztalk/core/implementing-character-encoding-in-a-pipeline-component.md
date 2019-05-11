---
title: 管道组件中实现字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], encoding
ms.assetid: 862b56da-ec14-41f9-b63c-42d81124e167
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8445a69b8de63ad2a0df91d3720436d79d605fdc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382612"
---
# <a name="implementing-character-encoding-in-a-pipeline-component"></a>管道组件中实现字符编码
若要支持自定义的字符编码，必须实现一个自定义编码类通过从 Microsoft.NET Framework 派生**编码**类，然后通过从标准平面继承来创建自定义的平面文件管道组件文件拆装器或平面文件组装器组件。 可以通过重写受保护的虚拟方法提供一个新编码实例到解析引擎**FFDasmComp.GetDataReader**如下面的示例中所示。  
  
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
  
## <a name="using-predefined-encoding-classes"></a>使用预定义编码类  
 下面的编码类型预定义的 Microsoft.NET Framework，并可用于构造解析程序：  
  
-   ASCII  
  
-   UTF7  
  
-   UTF8  
  
-   Unicode (UTF16)  
  
```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.UTF8));  
```  
  
## <a name="using-supported-code-pages"></a>使用受支持的代码页  
 使用以下代码来支持 SHIFT-JIS （代码页 932）。  
  

```  
XmlReader xr = docspec.Parse(new DataReader(System.Text.Encoding.GetEncoding(932)));  
```  
  
## <a name="using-a-private-encoding-class"></a>使用私有编码类  
 可以创建自己的编码类派生自**System.Text.Encoding**抽象类，并执行你自己编码和解码。  
  
```  
class MyEncoding : System.Text.Encoding  
{  
   // overriding methods omitted  
}  
  
XmlReader xr = docspec.Parser(new DataReader(new MyEncoding()));  
```  
  
## <a name="using-a-private-datareader-class"></a>使用私有 DataReader 类  

 可以创建你自己[DataReader](https://msdn.microsoft.com/library/microsoft.biztalk.parsingengine.datareader.aspx)类，该类实现`IDataReader`接口，并执行读取不创建任何编码类。  
  
```  
class MyDataReader : IDataReader  
{  
   // Implement data reader functions  
   // ...  
}  
  
XmlReader xr = docspec.Parse(new MyDataReader());  
```  
  
## <a name="see-also"></a>请参阅  
 [使用解析和序列化引擎](../core/using-the-parsing-and-serializing-engines.md)