---
title: "错误提取程序示例类 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Error Extractor Sample class
- errors, Error Extractor Sample class
ms.assetid: d0d59b21-d80a-4466-a77a-1d3b7df1bc2a
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0389f2fdb3f9ccb07bcc8ec9e4cdb1ec510927a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="error-extractor-sample-class"></a>错误提取程序示例类
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]反汇编程序序列化将错误记录到 XML 对象，并将 XML 对象附加到多部分消息的错误部分。 反汇编程序随后会在失败的消息发布到 MessageBox 数据库就像将有效的消息。 因此，到 MessageBox 数据库失败消息包含错误详细信息。 可以使用错误提取程序示例类从失败的消息，提取错误详细信息，并生成一个文件具有错误详细信息，并具有原始消息的另一个文件。  
  
> [!IMPORTANT]
>  错误提取程序示例类是 SDK 中的示例代码。 它不用于在生产中使用。  
  
 若要使用错误提取程序示例类，必须创建业务流程来处理失败的消息。 此业务流程包括步骤以提取失败消息的正文，提取的错误部分的失败的消息，然后编写正文和错误部分以单独的 XML 文件。 业务流程将表示每个步骤中调用错误提取程序示例类中的一个或多个以下方法的表达式阶段：  
  
## <a name="getbodypartasstring-method"></a>GetBodyPartAsString 方法  
 此方法返回一个字符串，包含的 XML 在 XLANG 消息 xm 的正文部分中找到。 方法需要包含正文部分的 XLANG 消息 xm 调用"BodySegment。" 因此，您必须声明 xm 中具有同名正文一部分调用的业务流程。 如果"BodySegment"不存在 xm 的一部分**GetBodyPartAsString**引发异常。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetBodyPartAsString(XLANGMessage xm);  
```  
  
## <a name="geterrorpartasstring-method"></a>GetErrorPartAsString 方法  
 此方法返回一个字符串，包含的 XML 在 XLANG 消息 xm 的错误部分中找到。 方法需要包含一个错误部分的 XLANG 消息 xm 调用"ErrorSegment。" 因此，您必须声明 xm 中具有同名错误一部分调用的业务流程。 如果"ErrorSegment"不存在 xm 的一部分**GetErrorPartAsString**引发异常。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.GetErrorPartAsString(XLANGMessage xm);  
```  
  
## <a name="writetofile-method"></a>WriteToFile 方法  
 此方法将写入从字符串*消息*参数指定的文件*filePath*参数。  
  
```  
SWIFTErrorExtractor.ErrorExtractor.WriteToFile(string filePath, string message);  
```  
  
 A4SWIFT 安装程序安装错误提取程序示例类 (SWIFTErrorExtractor.dll) 作为中 A4SWIFT SDK 的一部分\<*驱动器*>: files\microsoft BizTalk Accelerator for SWIFT\SDK\Tutorial\SWIFTErrorExtractor。 此文件夹还包括示例类 (ErrorExtractor.cs) 的源代码。  
  
 若要从业务流程调用 SWIFTErrorExtractor.dll，必须将.dll 文件发布到全局程序集缓存中。  
  
## <a name="see-also"></a>另请参阅  
 [工具](../../adapters-and-accelerators/accelerator-swift/tools.md)