---
title: 错误提取程序示例类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26375519e77de07161e20d9e373f2382cdbf0aac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378009"
---
# <a name="error-extractor-sample-class"></a>错误提取程序示例类
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]拆装器序列化将错误记录到 XML 对象，并将 XML 对象附加到多部分消息的错误部分。 拆装器就像一样是有效的消息，然后将失败的消息发布到 MessageBox 数据库。 因此，失败消息携带错误详细信息到 MessageBox 数据库。 可以使用错误提取程序示例类从失败的消息，提取错误详细信息，并生成一个文件包含错误详细信息，并具有原始消息的另一个文件。  
  
> [!IMPORTANT]
>  错误提取程序示例类是在 SDK 中的示例代码。 它不适合在生产中使用。  
  
 若要使用错误提取程序示例类，必须创建业务流程来处理失败的消息。 此业务流程包括失败消息的正文提取、 提取失败消息的错误部分，然后编写的正文和错误部分以单独的 XML 文件的步骤。 该业务流程表示每个步骤中的表达式阶段错误提取程序示例类中调用一个或多个以下方法：  
  
## <a name="getbodypartasstring-method"></a>GetBodyPartAsString 方法  
 此方法返回一个字符串，包含的 XML 在 XLANG 消息 xm 的正文部分中找到。 该方法需要包含一个正文部分 XLANG 消息 xm 调用"BodySegment。" 因此，您必须声明 xm 在调用业务流程中使用此正文部分名称。 如果"BodySegment"不存在 xm 的一部分**GetBodyPartAsString**将引发异常。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a>GetErrorPartAsString 方法  
 此方法返回 XLANG 消息 xm 的错误部分中找到包含的 XML 字符串。 该方法需要包含一个错误部分 XLANG 消息 xm 调用"ErrorSegment。" 因此，您必须声明 xm 在调用业务流程中使用此错误部分名称。 如果"ErrorSegment"不存在 xm 的一部分**GetErrorPartAsString**将引发异常。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a>WriteToFile 方法  
 此方法将从字符串写入*消息*参数指定的文件*filePath*参数。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 A4SWIFT 安装程序安装错误提取程序示例类 (SWIFTErrorExtractor.dll) 在 A4SWIFT SDK 的一部分\<*驱动器*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor。 此文件夹还包括示例类 (ErrorExtractor.cs) 的源代码。  
  
 若要从业务流程调用 SWIFTErrorExtractor.dll，必须将.dll 文件发布到全局程序集缓存中。  
  
## <a name="see-also"></a>请参阅  
 [工具](../../adapters-and-accelerators/accelerator-swift/tools.md)